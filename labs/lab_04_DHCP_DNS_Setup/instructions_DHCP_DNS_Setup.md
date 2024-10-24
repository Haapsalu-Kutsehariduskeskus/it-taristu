# DHCP ja DNS Laboriharjutused

## A. Azure Laboriharjutused
*Sobib algajatele - Ajakulu: 2-3 tundi*

## 1. SISSEJUHATUS

### 1.1 Mida Me Täna Õpime?
Me loome väikese ettevõtte võrgu Azure's, kus õpime:
- Kuidas arvutid saavad automaatselt IP aadresse (DHCP)
- Kuidas arvutid leiavad üksteist nime järgi (DNS)

### 1.2 Miks See On Kasulik?
- See on põhiline oskus IT-s
- Nii töötavad kõik ettevõtete võrgud

### 1.3 Mida Me Ehitame?
- 4 virtuaalarvutit (2 Windowsit, 2 Linuxit)
- Üks võrk nende ühendamiseks
- Oma nimeserver (DNS)

### 1.4 Seadmete Ülevaade
| Seade | Operatsioonisüsteem | IP-aadress | DNS nimi |
|-------|---------------------|------------|-----------|
| VM1-Windows-[ÕpilaseNimi] | Windows Server 2019 | 10.0.1.4 | vm1-windows-[ÕpilaseNimi].labdns-[ÕpilaseNimi].local |
| VM2-Windows-[ÕpilaseNimi] | Windows 10 | 10.0.1.5 | vm2-windows-[ÕpilaseNimi].labdns-[ÕpilaseNimi].local |
| VM3-Linux-[ÕpilaseNimi] | Ubuntu 20.04 LTS | 10.0.1.6 | vm3-linux-[ÕpilaseNimi].labdns-[ÕpilaseNimi].local |
| VM4-Linux-[ÕpilaseNimi] | CentOS 8 | 10.0.1.7 | vm4-linux-[ÕpilaseNimi].labdns-[ÕpilaseNimi].local |

*Näiteks kui õpilase nimi on Maria:*
*VM1-Windows-Maria | Windows Server 2019 | 10.0.1.4 | vm1-windows-Maria.labdns-Maria.local*

## 2. ETTEVALMISTUS

### 2.1 Mida Vajad?
- Azure konto (sobib ka õppekonto)
- Ligipääs lehele portal.azure.com
- Märkmik parooli jaoks
- ~2 tundi aega

## 3. SAMM-SAMMULT JUHEND

### 3.1 Resource Group Loomine
1. Mine portal.azure.com
2. Otsi ülevalt "Resource groups"
3. Vajuta "+ Create"
4. Täida:
   - Subscription: [Sinu subscription]
   - Resource group: "NetworkLab-RG-[ÕpilaseNimi]"
   - Region: (North Europe)
5. Vajuta "Review + create" ja siis "Create"

*Näiteks kui õpilase nimi on Maria:*
*Resource group: NetworkLab-RG-Maria*

### 3.2 Võrgu Loomine
1. Otsi ülevalt "Virtual networks"
2. Vajuta "+ Create"
3. Põhiandmed:
   - Subscription: [Sama mis enne]
   - Resource group: NetworkLab-RG-[ÕpilaseNimi]
   - Name: VNet-Lab-[ÕpilaseNimi]
   - Region: [Sama mis enne]
4. IP Andmed:
   - IPv4 address space: 10.0.0.0/16
   - Subnet name: Subnet-1-[ÕpilaseNimi]
   - Subnet range: 10.0.1.0/24
5. Vajuta "Review + create" ja siis "Create"

*Näiteks kui õpilase nimi on Maria:*
*Resource group: NetworkLab-RG-Maria*
*Network name: VNet-Lab-Maria*
*Subnet name: Subnet-1-Maria*

### 3.3 Virtuaalmasinate Loomine

#### A. Esimene Windows Server (VM1)
1. Otsi "Virtual machines"
2. "+ Create" > "Azure virtual machine"
3. Põhiandmed:
   - Resource group: NetworkLab-RG-[ÕpilaseNimi]
   - Name: VM1-Windows-[ÕpilaseNimi]
   - Region: [Sama mis enne]
   - Image: Windows Server 2019
   - Size: Standard_B2s
   - Username: azureuser
   - Password: [Vali tugev parool - KIRJUTA ÜLES!]
4. Võrguseaded:
   - Virtual network: VNet-Lab-[ÕpilaseNimi]
   - Subnet: Subnet-1-[ÕpilaseNimi]
   - Public IP: (Create new)
5. Vajuta "Review + create" ja siis "Create"

*Näiteks kui õpilase nimi on Maria:*
*Resource group: NetworkLab-RG-Maria*
*Name: VM1-Windows-Maria*
*Virtual network: VNet-Lab-Maria*
*Subnet: Subnet-1-Maria*

#### B. Teine Windows (VM2)
Korda samu samme, aga muuda:
- Name: VM2-Windows-[ÕpilaseNimi]
- Image: Windows 10 Pro

*Näiteks kui õpilase nimi on Maria:*
*Name: VM2-Windows-Maria*

#### C. Ubuntu Linux (VM3)
Korda samu samme, aga muuda:
- Name: VM3-Linux-[ÕpilaseNimi]
- Image: Ubuntu 20.04 LTS

*Näiteks kui õpilase nimi on Maria:*
*Name: VM3-Linux-Maria*

#### D. CentOS Linux (VM4)
Korda samu samme, aga muuda:
- Name: VM4-Linux-[ÕpilaseNimi]
- Image: CentOS 8

*Näiteks kui õpilase nimi on Maria:*
*Name: VM4-Linux-Maria*

### 3.4 DNS Seadistamine

#### Mis on DNS tsoon ja DNS kirjed?

DNS tsoon (Zone) on nagu telefoniraamat või aadressiraamat võrgus olevatele arvutitele:
- Tsoon on konkreetse domeeni (näiteks labdns-[ÕpilaseNimi].local) andmebaas
- See sisaldab seoseid arvutite nimede ja IP-aadresside vahel
- Meie labori puhul on see privaatne tsoon, mis töötab ainult meie Azure võrgus

DNS kirjed (Records) on üksiksisestused selles "telefoniraamatus":
- A-kirje seob arvuti nime (näiteks vm1-windows-[ÕpilaseNimi]) konkreetse IP-aadressiga (10.0.1.4)
- Kui arvuti küsib "Kus asub vm1-windows-[ÕpilaseNimi]?", siis DNS server vaatab tsooni kirjetest ja vastab "See on aadressil 10.0.1.4"

*Näiteks kui õpilase nimi on Maria:*
*- Tsoon: labdns-Maria.local*
*- Kirje: vm1-windows-Maria = 10.0.1.4*
*Kui keegi küsib "Kus asub vm1-windows-Maria?", DNS vastab "10.0.1.4"*

#### A. DNS Tsooni Loomine
1. Otsi "Private DNS zones"
2. Vajuta "+ Create"
3. Täida:
   - Resource group: NetworkLab-RG-[ÕpilaseNimi]
   - Name: labdns-[ÕpilaseNimi].local
4. Vajuta "Review + create" ja "Create"

*Näiteks kui õpilase nimi on Maria:*
*Resource group: NetworkLab-RG-Maria*
*Name: labdns-Maria.local*

#### B. DNS Tsooni Sidumine Võrguga
1. Mine loodud DNS tsooni
2. Vali vasakult "Virtual network links"
3. Vajuta "+ Add"
4. Täida:
   - Name: VNet-Lab-Link-[ÕpilaseNimi]
   - Virtual network: VNet-Lab-[ÕpilaseNimi]
   - Enable auto registration: Jah
5. Vajuta "OK"

*Näiteks kui õpilase nimi on Maria:*
*Name: VNet-Lab-Link-Maria*
*Virtual network: VNet-Lab-Maria*

#### C. DNS Kirjete Lisamine
1. Mine DNS tsooni
2. Vali vasakult "Record sets"
3. Lisa kirjed:

Vajuta "+ Add record set" ja lisa järgmised:
```
VM1:
- Name: vm1-windows-[ÕpilaseNimi]
- Type: A
- IP: 10.0.1.4

VM2:
- Name: vm2-windows-[ÕpilaseNimi]
- Type: A
- IP: 10.0.1.5

VM3:
- Name: vm3-linux-[ÕpilaseNimi]
- Type: A
- IP: 10.0.1.6

VM4:
- Name: vm4-linux-[ÕpilaseNimi]
- Type: A
- IP: 10.0.1.7
```

*Näiteks kui õpilase nimi on Maria:*
*Name: vm1-windows-Maria*
*Name: vm2-windows-Maria*
*Name: vm3-linux-Maria*
*Name: vm4-linux-Maria*

### 3.5 Testimine

#### A. Windows Masinas
1. Ühendu VM2 külge (vajuta "Connect" > "Bastion")
2. Ava PowerShell
3. Sisesta:
```powershell
ipconfig /all
nslookup vm1-windows-[ÕpilaseNimi].labdns-[ÕpilaseNimi].local
nslookup vm3-linux-[ÕpilaseNimi].labdns-[ÕpilaseNimi].local
```

*Näiteks kui õpilase nimi on Maria:*
*`nslookup vm1-windows-Maria.labdns-Maria.local`*
*`nslookup vm3-linux-Maria.labdns-Maria.local`*

#### B. Linux Masinas
1. Ühendu VM3 külge (Bastion)
2. Sisesta:
```bash
ip addr show
dig vm2-windows-[ÕpilaseNimi].labdns-[ÕpilaseNimi].local
dig vm4-linux-[ÕpilaseNimi].labdns-[ÕpilaseNimi].local
```

*Näiteks kui õpilase nimi on Maria:*
*`dig vm2-windows-Maria.labdns-Maria.local`*
*`dig vm4-linux-Maria.labdns-Maria.local`*


## 4. LABORI LÕPETAMINE

### 4.1 Dokumenteerimine
Enne ressursside peatamist on vaja teha ja salvestada kaks kuvatõmmist:

1. DNS tsooni kuvatõmmis:
   - Mine Azure portaalis "Private DNS zones"
   - Ava oma tsoon labdns-[ÕpilaseNimi].local
   - Vali "Record sets"
   - Tee kuvatõmmis, kus on näha kõik DNS kirjed (A-records)

*Näiteks kui õpilase nimi on Maria:*
*Kuvatõmmis DNS tsoonist labdns-Maria.local*

2. Virtuaalmasinate kuvatõmmis:
   - Mine Azure portaalis "Virtual machines"
   - Veendu, et kõik 4 masinat on nähtavad
   - Tee kuvatõmmis, kus on näha kõik sinu loodud masinad ja nende olek

*Näiteks kui õpilase nimi on Maria:*
*Kuvatõmmis, kus on näha:*
*- VM1-Windows-Maria*
*- VM2-Windows-Maria*
*- VM3-Linux-Maria*
*- VM4-Linux-Maria*

### 4.2 Masinate Peatamine
1. Mine "Virtual machines"
2. Vali iga masin
3. Vajuta "Stop"

### 4.3 Kui Enam Ei Vaja
1. Mine "Resource groups"
2. Leia "NetworkLab-RG-[ÕpilaseNimi]"
3. Vajuta "Delete"
4. Kirjuta grupi nimi kinnituseks
5. Vajuta "Delete"

*Näiteks kui õpilase nimi on Maria:*
*Resource group: NetworkLab-RG-Maria*

## 5. KUI MISKI EI TÖÖTA

### 5.1 VM Ei Käivitu
- Kontrolli, kas sul on piisavalt õigusi
- Proovi teises regioonis
- Kontrolli, kas nimi on unikaalne

### 5.2 DNS Ei Tööta
- Kontrolli, kas kirjutasid nime õigesti (vm1-windows-[ÕpilaseNimi].labdns-[ÕpilaseNimi].local)
- Kontrolli, kas VM-id töötavad
- Oota 5 minutit (DNS võib võtta aega)

### 5.3 Ühendus Ei Tööta
- Kontrolli parooli
- Proovi VM taaskäivitada
- Kontrolli, kas VM töötab

## 6. ÕPITU
Pärast seda laborit oskad:
- Luua virtuaalvõrgu Azure's
- Seadistada virtuaalmasinaid
- Mõistad DHCP ja DNS põhitööd
- Tead, kuidas ressursse peatada ja kustutada

## B. Cisco Packet Tracer Laboriharjutused
*Sobib algajatele - Ajakulu: 1-2 tundi*

### 1. SISSEJUHATUS

#### 1.1 Mida Me Täna Õpime?
Me loome väikese ettevõtte võrgu Cisco Packet Traceris, kus õpime:
- Kuidas seadistada DHCP serverit ruuteris
- Kuidas seadistada DNS serverit
- Kuidas ühendada ja nimetada seadmeid õigesti

#### 1.2 Mida Me Ehitame?
- 1 ruuter (DHCP serveri rollis)
- 1 kommutaator (võrgu ühendamiseks)
- 1 server (DNS serveri rollis)
- 4 arvutit (klientidena)

### 2. SEADMETE ÜLEVAADE

#### 2.1 Vajalikud Seadmed
| Seade | Mudel | Roll |
|-------|-------|------|
| R1-[ÕpilaseNimi] | Cisco 2911 | DHCP Server |
| SW1-[ÕpilaseNimi] | Cisco 2960 | Kommutaator |
| SRV1-[ÕpilaseNimi] | Generic Server | DNS Server |
| PC1-[ÕpilaseNimi] | Generic PC | Klient |
| PC2-[ÕpilaseNimi] | Generic PC | Klient |
| PC3-[ÕpilaseNimi] | Generic PC | Klient |
| PC4-[ÕpilaseNimi] | Generic PC | Klient |

*Näiteks kui õpilase nimi on Maria:*
*- R1-Maria*
*- SW1-Maria*
*- SRV1-Maria*
*- PC1-Maria kuni PC4-Maria*

#### 2.2 IP-aadresside Plaan
| Seade | IP-aadress | DNS nimi |
|-------|------------|----------|
| R1-[ÕpilaseNimi] | 192.168.1.1 | - |
| SRV1-[ÕpilaseNimi] | 192.168.1.2 | server-[ÕpilaseNimi].labdns.local |
| PC1-[ÕpilaseNimi] | 192.168.1.11 | pc1-[ÕpilaseNimi].labdns.local |
| PC2-[ÕpilaseNimi] | 192.168.1.12 | pc2-[ÕpilaseNimi].labdns.local |
| PC3-[ÕpilaseNimi] | 192.168.1.13 | pc3-[ÕpilaseNimi].labdns.local |
| PC4-[ÕpilaseNimi] | 192.168.1.14 | pc4-[ÕpilaseNimi].labdns.local |

*Näiteks kui õpilase nimi on Maria:*
*- server-Maria.labdns.local*
*- pc1-Maria.labdns.local*

### 3. VÕRGU EHITAMINE

#### 3.1 Topoloogia Loomine
1. Ava Cisco Packet Tracer
2. Lisa seadmed töölauale:
   - Ruuter: Lohista Cisco 2911
   - Kommutaator: Lohista Cisco 2960
   - Server: Lohista Generic Server
   - PC-d: Lohista 4 Generic PC-d

3. Nimeta seadmed ümber:
   - Topeltklõps seadmel > muuda nimi
   - Lisa igale seadmele oma nimi, näiteks:
     *Kui õpilase nimi on Maria:*
     *- R1-Maria*
     *- SW1-Maria* jne.

#### 3.2 Seadmete Ühendamine
1. Vali õige kaabel:
   - Kasuta straight-through kaableid kõikideks ühendusteks

2. Loo ühendused:
```
R1-[ÕpilaseNimi] GigabitEthernet0/0 <--> SW1-[ÕpilaseNimi] GigabitEthernet0/1
SW1-[ÕpilaseNimi] GigabitEthernet0/2 <--> SRV1-[ÕpilaseNimi] FastEthernet0
SW1-[ÕpilaseNimi] ports 0/3-0/6 <--> PC1 kuni PC4 FastEthernet0
```

### 4. SEADISTAMINE

#### 4.1 Ruuteri DHCP Seadistamine
1. Klõpsa ruuteril R1-[ÕpilaseNimi]
2. Vali CLI
3. Sisesta käsud:
```cisco
enable
configure terminal
hostname R1-[ÕpilaseNimi]
interface GigabitEthernet0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit
ip dhcp pool LAN-POOL-[ÕpilaseNimi]
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 192.168.1.2
exit
ip dhcp excluded-address 192.168.1.1 192.168.1.10
```

*Näiteks kui õpilase nimi on Maria:*
```cisco
hostname R1-Maria
ip dhcp pool LAN-POOL-Maria
```

#### 4.2 DNS Serveri Seadistamine
1. Klõpsa serveril SRV1-[ÕpilaseNimi]
2. IP Configuration:
   - Määra staatiline IP: 192.168.1.2
   - Subnet Mask: 255.255.255.0
   - Default Gateway: 192.168.1.1

3. DNS Seadistamine:
   - Vali Services > DNS
   - Lisa kirjed:
```
server-[ÕpilaseNimi].labdns.local - 192.168.1.2
pc1-[ÕpilaseNimi].labdns.local - 192.168.1.11
pc2-[ÕpilaseNimi].labdns.local - 192.168.1.12
pc3-[ÕpilaseNimi].labdns.local - 192.168.1.13
pc4-[ÕpilaseNimi].labdns.local - 192.168.1.14
```

*Näiteks kui õpilase nimi on Maria:*
*- server-Maria.labdns.local*
*- pc1-Maria.labdns.local*

#### 4.3 Klientide Seadistamine
1. Klõpsa igal PC-l
2. Vali Desktop > IP Configuration
3. Vali "DHCP"

### 5. TESTIMINE

#### 5.1 DHCP Testimine
1. Igal PC-l:
   - Ava Command Prompt
   - Sisesta: `ipconfig /all`
   - Kontrolli, et PC sai IP aadressi

#### 5.2 DNS Testimine
1. Igal PC-l:
   - Ava Command Prompt
   - Testi DNS päringuid:
```
nslookup server-[ÕpilaseNimi].labdns.local
nslookup pc1-[ÕpilaseNimi].labdns.local
```

*Näiteks kui õpilase nimi on Maria:*
*`nslookup server-Maria.labdns.local`*

### 6. DOKUMENTEERIMINE
Enne labori lõpetamist:
1. Tee kuvatõmmis võrgu topoloogiast
2. Tee kuvatõmmis DHCP liisingute tabelist (ruuterist)
3. Tee kuvatõmmis DNS kirjetest (serverist)

### 7. VÕIMALIKUD PROBLEEMID

#### 7.1 PC Ei Saa IP-aadressi
- Kontrolli kaablite ühendusi
- Kontrolli ruuteri DHCP seadistusi
- Kontrolli, kas interface on "no shutdown" olekus

#### 7.2 DNS Ei Tööta
- Kontrolli serveri IP-aadressi
- Kontrolli DNS kirjete õigekirja
- Kontrolli, kas PC-l on õige DNS server määratud

### 8. ÕPITU
Pärast seda laborit oskad:
- Luua lihtsa võrgutopoloogia Packet Traceris
- Seadistada DHCP serverit ruuteris
- Seadistada DNS serverit
- Testida DHCP ja DNS toimimist

## Submission Vorm

### Azure Lab

Lisa ekraanitõmmised.

### Packet Tracer Lab

Lisa ekraanitõmmised.

Lisa su labi, nimega "[SinuNimi]_PacketTracer_DHCP_DNS_Lab.pkt"


Märkus: Veendu, et oled peatanud kõik Azure'i ressursid peale labori lõpetamist, et vältida lisakulusid.
