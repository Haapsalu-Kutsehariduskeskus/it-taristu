# DHCP ja DNS Laboriharjutused

## A. Azure Laboriharjutused

### Eesmärk:
Seadistada DHCP ja DNS Azure virtuaalvõrgus nelja virtuaalmasina jaoks.

### Seadmed:
- 1 virtuaalvõrk
- 4 virtuaalmasinat (VM)

### Sammud:

1. Loo uus virtuaalvõrk Azure'is:
   - Nimi: VNet-Lab
   - Aadressiruum: 10.0.0.0/16
   - Alamvõrk: Subnet-1 (10.0.1.0/24)

2. Loo neli virtuaalmasinat:
   - VM1-Windows-[SinuEesnimi] (Windows Server 2019)
   - VM2-Windows-[SinuEesnimi] (Windows 10)
   - VM3-Linux-[SinuEesnimi] (Ubuntu 20.04 LTS)
   - VM4-Linux-[SinuEesnimi] (CentOS 8)

   Iga VM jaoks:
   - Suurus: Standard_B2s (2 vCPUs, 4 GB RAM)
   - Virtuaalvõrk: VNet-Lab
   - Alamvõrk: Subnet-1
   - Avalik IP: Jah (dünaamiline)

3. Kontrolli DHCP tööd:
   - Ühendu iga VM-iga kasutades Azure Bastion või RDP/SSH
   - Kontrolli IP-aadressi seadistust:
     - Windows: Ava PowerShell, sisesta `ipconfig /all`
     - Linux: Ava terminal, sisesta `ip addr show` ja `cat /etc/resolv.conf`

4. Loo privaatne DNS tsoon:
   - Mine Azure portaalis
   - Otsi "Private DNS zones" ja vali see
   - Klõpsa "Add" või "+ Create"
   - Resource group: Vali sama resource group, mida kasutasid VM-ide loomisel
   - Nimi: labdns.local
   - Klõpsa "Review + Create" ja seejärel "Create"

5. Ühenda DNS tsoon virtuaalvõrguga:
   - Ava loodud DNS tsoon
   - Vasakul menüüs vali "Virtual network links"
   - Klõpsa "+ Add"
   - Link name: VNet-Lab-Link
   - Virtual network: Vali VNet-Lab
   - Enable auto registration: Vali "Enabled"
   - Klõpsa "OK"

6. Lisa DNS kirjed:
   - Ava loodud DNS tsoon
   - Vasakul menüüs vali "Record sets"
   - Klõpsa "+ Add record set"
   - Iga VM jaoks lisa A-kirje:
     - Name: vm1, vm2, vm3, vm4 (vastavalt)
     - Type: A
     - IP address: Sisesta vastava VM privaatne IP-aadress
   - Klõpsa "OK" iga kirje lisamise järel

7. Testi DNS lahendamist:
   - Ühendu VM2-Windows'iga
   - Ava PowerShell, sisesta:
     ```
     nslookup vm1.labdns.local
     nslookup vm3.labdns.local
     ```
   - Ühendu VM3-Linux'iga
   - Ava terminal, sisesta:
     ```
     dig vm2.labdns.local
     dig vm4.labdns.local
     ```

8. Ressursside peatamine:
   - Peale labori lõpetamist peata kõik VM-id Azure portaalis

### IP-tabel:

| Seade                  | Operatsioonisüsteem | IP-aadress | DNS nimi           |
|------------------------|---------------------|------------|---------------------|
| VM1-Windows-[SinuEesnimi] | Windows Server 2019 | 10.0.1.4   | vm1.labdns.local    |
| VM2-Windows-[SinuEesnimi] | Windows 10          | 10.0.1.5   | vm2.labdns.local    |
| VM3-Linux-[SinuEesnimi]   | Ubuntu 20.04 LTS    | 10.0.1.6   | vm3.labdns.local    |
| VM4-Linux-[SinuEesnimi]   | CentOS 8            | 10.0.1.7   | vm4.labdns.local    |

## B. Cisco Packet Tracer Laboriharjutused

### Eesmärk:
Seadistada DHCP server ja DNS server Packet Traceris nelja kliendi jaoks.

### Seadmed:
- 1 ruuter (Cisco 2911)
- 1 kommutaator (Cisco 2960)
- 1 server (Generic Server)
- 4 PC-klienti (Generic PC)

### Sammud:

1. Loo võrgutopoloogia:
   - Nimeta seadmed:
     - Ruuter: R1-[SinuEesnimi]
     - Kommutaator: SW1-[SinuEesnimi]
     - Server: SRV1-[SinuEesnimi]
     - PC-d: PC1-[SinuEesnimi], PC2-[SinuEesnimi], PC3-[SinuEesnimi], PC4-[SinuEesnimi]

2. Ühenda seadmed:
   - R1 GigabitEthernet0/0 <--> SW1 GigabitEthernet0/1
   - SW1 GigabitEthernet0/2 <--> SRV1 FastEthernet0
   - SW1 GigabitEthernet0/3 <--> PC1 FastEthernet0
   - SW1 GigabitEthernet0/4 <--> PC2 FastEthernet0
   - SW1 GigabitEthernet0/5 <--> PC3 FastEthernet0
   - SW1 GigabitEthernet0/6 <--> PC4 FastEthernet0

3. Konfigureeri ruuter R1 DHCP serveriks:
   - Klõpsa R1 ja vali CLI
   - Sisesta järgmised käsud:
     ```
     enable
     configure terminal
     interface GigabitEthernet0/0
     ip address 192.168.1.1 255.255.255.0
     no shutdown
     exit
     ip dhcp pool LAN-POOL
     network 192.168.1.0 255.255.255.0
     default-router 192.168.1.1
     dns-server 192.168.1.2
     exit
     ip dhcp excluded-address 192.168.1.1 192.168.1.10
     ```

4. Konfigureeri SRV1 DNS serveriks:
   - Klõpsa SRV1 ja vali Services > DNS
   - Lisa järgmised DNS kirjed:
     - server.labdns.local - 192.168.1.2
     - pc1.labdns.local - 192.168.1.11
     - pc2.labdns.local - 192.168.1.12
     - pc3.labdns.local - 192.168.1.13
     - pc4.labdns.local - 192.168.1.14

5. Konfigureeri kõik PC-d DHCP klientideks:
   - Klõpsa igal PC-l
   - Ava Desktop > IP Configuration
   - Vali "DHCP" IP konfiguratsiooni juures

6. Kontrolli tulemust:
   - Ava iga PC käsurida (Command Prompt)
   - Sisesta käsk `ipconfig /all`
   - Kontrolli DNS lahendamist käsuga `nslookup pc2.labdns.local`

### IP-tabel:

| Seade            | IP-aadress   | DNS nimi           |
|------------------|--------------|---------------------|
| R1-[SinuEesnimi] | 192.168.1.1  | -                   |
| SRV1-[SinuEesnimi] | 192.168.1.2  | server.labdns.local |
| PC1-[SinuEesnimi] | 192.168.1.11 | pc1.labdns.local    |
| PC2-[SinuEesnimi] | 192.168.1.12 | pc2.labdns.local    |
| PC3-[SinuEesnimi] | 192.168.1.13 | pc3.labdns.local    |
| PC4-[SinuEesnimi] | 192.168.1.14 | pc4.labdns.local    |

## Submission Vorm

### Azure Lab

1. Tee ekraanitõmmised:
   - Azure portaali ressursside lehest, kus on näha kõik loodud VM-id koos nimedega
   - Iga VM ülevaate lehest, kus on näha VM nimi ja staatus
   - PowerShell'i või terminali aknast, kus on näha `nslookup` või `dig` käsu väljund (veendu, et ekraanitõmmisel on näha ka VM nimi)
   - VM-ide lehest, kus on näha, et kõik VM-id on peatatud olekus
   - Privaatse DNS tsooni ülevaatest, kus on näha tsooni nimi ja seotud virtuaalvõrk
   - DNS kirjete lehest, kus on näha kõik lisatud A-kirjed

2. Koosta dokument:
   - Loo Word või PDF dokument pealkirjaga "[SinuNimi]_Azure_DHCP_DNS_Lab"
   - Lisa kõik ekraanitõmmised dokumenti koos lühikeste selgitustega

### Packet Tracer Lab

1. Tee ekraanitõmmised:
   - Kogu võrgutopoloogiast, kus on näha kõik seadmed koos nimedega
   - Ruuteri konfiguratsiooni lehest, kus on näha DHCP seadistused
   - Serveri DNS seadistuste lehest
   - Ühe PC käsurea aknast, kus on näha `ipconfig /all` ja `nslookup pc2.labdns.local` käskude tulemused

2. Koosta dokument:
   - Loo Word või PDF dokument pealkirjaga "[SinuNimi]_PacketTracer_DHCP_DNS_Lab"
   - Lisa kõik ekraanitõmmised dokumenti koos lühikeste selgitustega
   - Salvesta Packet Tracer fail nimega "[SinuNimi]_PacketTracer_DHCP_DNS_Lab.pkt"


Märkus: Veendu, et oled peatanud kõik Azure'i ressursid peale labori lõpetamist, et vältida lisakulusid.