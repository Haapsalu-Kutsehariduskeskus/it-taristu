# IT Infrastruktuuri Kursuse Täielik Õppekava

## Kursuse Informatsioon
- **Kursuse Pealkiri**: IT Infrastruktuuri Alused
- **Õppejõud**: Maria Talvik
- **E-post**: maria.talvik@hkhk.edu.ee
- **Vastuvõtuaeg**: Neljapäeviti, 08:00 – 16:00 (või kokkuleppel)
- **Tunniplaan**: Neljapäeviti, 08:30 – 16:00
- **Asukoht**: Ruum 301 (või Google'i link veebikoosolekuteks)

## Kursuse Kirjeldus
See kursus pakub põhjaliku sissejuhatuse IT-infrastruktuuri, keskendudes virtualiseerimisele, pilvandmetöötlusele, võrgundusele, serverihaldusele ja IT-turvalisusele. Praktiliste laborite ja reaaleluliste juhtumiuuringute kaudu omandavad õpilased põhioskused IT-infrastruktuuri komponentide haldamiseks ja konfigureerimiseks reaalses keskkonnas.

## Iganädalane Plaan

### Nädal 7 (07.10.2024) - 12 Tundi
**Põhjalik sissejuhatus IT-infrastruktuuri**
- IT-infrastruktuuri ülevaade
  - Infrastruktuuri põhikomponendid ja nende funktsioonid
  - Infrastruktuuri arhitektuuri ja disaini põhimõtted
- Virtualiseerimise kontseptsioonid
  - Virtualiseerimise tüübid: serveri, võrgu, salvestuse virtualiseerimine
  - Hüperviisorid: tüüp 1 ja tüüp 2
- Pilvandmetöötluse ülevaade
  - Pilveteenuste mudelid: IaaS, PaaS, SaaS
  - Avaliku, privaatse ja hübriidpilve võrdlus
- Sissejuhatus serveritesse
  - Serverite rollid ja tüübid
  - Serveri riistvara komponendid
- **Laborid**: 
  - Lab 1: Virtuaalmasina seadistamine VirtualBox'is
  - Lab 2: AWS EC2 instantsi loomine ja konfigureerimine
  - Lab 3: Põhiline veebiserveri seadistamine

### Nädal 8 (14.10.2024) - 4 Tundi
**Võrguinfrastruktuur ja Põhiteenused**
- Võrgutüübid: LAN, WAN, VLAN, WLAN
  - Võrgutopoloogiad ja nende eelised/puudused
  - IPv4 ja IPv6 adresseerimine
- Võrguseadmed: Ruuterid, kommutaatorid, tulemüürid
  - OSI mudel ja TCP/IP protokollistik
- DHCP (Dünaamiline hostikonfiguratsiooni protokoll)
  - DHCP tööpõhimõtted ja komponendid
  - DHCP skoobi ja valikute konfigureerimine
  - DHCP relay agendid
- DNS (Domeeninimede süsteem)
  - DNS hierarhia ja päringute töötlemine
  - Tsoonifailid ja kirjetüübid (A, AAAA, MX, CNAME, TXT)
  - Päringute ja vastupäringute tsoonid
- **Labor**: 
  - DHCP serveri seadistamine ja klientide konfigureerimine
  - DNS serveri ülesseadmine, tsoonide loomine ja kirjete haldamine
  - Võrguteenuste integreerimine Packet Tracer'is

### Nädal 9 (21.10.2024) - 2 Tundi
**Serverid, Salvestus ja Veebiteenused**
- Sissejuhatus serveritesse: Veebi-, andmebaasi-, failiserverid
  - Veebiserveri arhitektuur ja komponendid
  - Veebiserveri tarkvara: Apache, Nginx
    - Moodulid ja laiendused
    - Jõudluse optimeerimine
  - Virtuaalhostide konfigureerimine
  - Veebirakenduste juurutamine (PHP, Python, Node.js)
  - Veebiserveri turvalisus
    - SSL/TLS sertifikaatide seadistamine
    - Põhilised turvareeglid ja parimad praktikad
- Andmebaasiserveri põhimõtted: MySQL, PostgreSQL
- Salvestuslahendused: Lokaalne salvestus, NAS, SAN, pilvesalvestus
  - RAID tasemed ja nende kasutusalad
  - Pilvesalvestuse teenused: S3, Azure Blob Storage
- **Labor**: 
  - Apache või Nginx veebiserveri paigaldamine ja konfigureerimine
  - Virtuaalhostide seadistamine
  - SSL/TLS sertifikaadi paigaldamine

### Nädal 10 (28.10.2024) - 4 Tundi
**Operatsioonisüsteemid ja Serverihaldus**
- Sissejuhatus operatsioonisüsteemidesse: Windows Server, Linux
  - Windows Server rollid ja funktsioonid
  - Linux distributsioonid serverikasutuseks
- Põhiline serverihaldus: Kasutajad, teenused, õigused
  - Active Directory põhimõtted
  - Linux kasutajate ja gruppide haldamine
- **Labor**: Põhiline Linuxi serveri konfigureerimine
  - SSH seadistamine ja turvamine
  - Veebiserveri (Apache või Nginx) paigaldamine ja seadistamine

### Nädal 11 (04.11.2024) - 4 Tundi
**Turvalisus IT-infrastruktuuris**
- IT-turvalisuse alused: Tulemüürid, VPN-id, turvapoliitikad
  - Tulemüüri reeglite loomine ja haldamine
  - VPN protokollid ja nende kasutusalad
- Võrguturve: Ohud ja leevendamine
  - Levinud võrguründed ja nende tuvastamine
  - Turvalise võrgu disainipõhimõtted
- **Labor**: Põhiline tulemüüri seadistamine Packet Tracer'is
  - Tulemüüri reeglite määramine
  - DMZ (demilitariseeritud tsooni) konfigureerimine

### Nädal 12 (11.11.2024) - 4 Tundi
**Pilvandmetöötlus**
- Sissejuhatus pilveteenustesse: SaaS, PaaS, IaaS
  - Pilveteenuste eelised ja väljakutsed
  - Pilve migreerimise strateegiad
- Pilveteenuste pakkujad: AWS, Azure, Google Cloud
  - Põhilised teenused igalt pakkujalt
  - Pilveressursside haldamise tööriistad
- Hübriidpilve lahendused
  - Hübriidpilve arhitektuur
  - Juhtumiuuring: Hübriidpilve rakendamine ettevõttes

### Nädal 13 (18.11.2024) - 4 Tundi
**Monitooring ja Hooldus**
- Monitooringutööriistad: Zabbix, Prometheus
  - Monitooringusüsteemi arhitektuur
  - Häirete ja teavituste seadistamine
- Hooldusplaanid: Varukoopiad, paikamine
  - Varundusstrateegiate väljatöötamine
  - Tarkvara uuendamise ja paikamise parimad praktikad
- **Labor**: Põhiline Zabbix'i seadistamine
  - Zabbix'i serveri ja agendi paigaldamine
  - Põhiliste monitooringuparameetrite seadistamine

### Nädal 14 (25.11.2024) - 4 Tundi
**Automatiseerimine IT-infrastruktuuris**
- Automatiseerimistööriistad: Ansible, Puppet
  - Konfiguratsioonihalduse põhimõtted
  - Infrastruktuur kui kood (IaC) kontseptsioon
- Serveri konfiguratsiooni automatiseerimine
  - Ansible playbook'ide struktuur
  - Idempotentsuse põhimõte automatiseerimisel
- **Labor**: Lihtsad automatiseerimisülesanded Ansible'iga
  - Ansible'i paigaldamine ja seadistamine
  - Põhilise playbook'i loomine ja käivitamine

### Nädal 15 (02.12.2024) - 4 Tundi
**Katastroofi Taastamine, Varundamine ja E-posti Teenused**
- Varundusstrateegiad: Täielik, inkrementaalne, diferentsiaalne
  - Varundusmetoodikate võrdlus
  - Varunduse testimise olulisus
- Katastroofi taastamise planeerimine ja testimine
  - Äri mõju analüüs (BIA)
  - Taastamisaja eesmärk (RTO) ja taastamispunkti eesmärk (RPO)
- E-posti teenused
  - E-posti protokollid: SMTP, POP3, IMAP
  - E-posti serveri tarkvara: Postfix, Exchange
  - E-posti turvalisus:
    - SPF (Sender Policy Framework)
    - DKIM (DomainKeys Identified Mail)
    - DMARC (Domain-based Message Authentication, Reporting and Conformance)
  - E-posti klientide seadistamine
  - Listiserverid ja automaatvastused
- **Laborid**: 
  - Katastroofi taastamise stsenaariumi simuleerimine
    - Varunduse loomine ja taastamine
    - Taastamisplaani testimine ja dokumenteerimine
  - E-posti serveri paigaldamine ja konfigureerimine (nt Postfix)
    - Põhiliste turvameetmete rakendamine (SPF, DKIM)
    - E-posti kliendi seadistamine ja testimine

### Nädal 16 (09.12.2024) - 4 Tundi
**Virtualiseerimine ja Konteineriseerimine**
- Edasijõudnud virtualiseerimise teemad: Hyper-V, VMware
  - Virtuaalmasinate migreerimine
  - Ressursside optimeerimine virtuaalkeskkonnas
- Konteineriseerimine Docker'iga
  - Konteinerite vs virtuaalmasinate võrdlus
  - Docker'i arhitektuur ja põhikomponendid
- **Labor**: Docker'i konteinerite loomine ja haldamine
  - Docker'i paigaldamine ja seadistamine
  - Lihtsa rakenduse konteineriseerimine

### Nädal 17 (16.12.2024) - 4 Tundi
**Edasijõudnud Pilveinfrastruktuur**
- Pilvevõrgundus: VPC-d, alamvõrgud, koormusjaoturid
  - VPC disaini põhimõtted
  - Turvagruppide ja võrgu ACL-ide kasutamine
- Pilveinfrastruktuuri skaleerimine: Autoskaleerimine, koormusjaotus
  - Horisontaalne vs vertikaalne skaleerimine
  - Koormusjaotuse algoritmid ja strateegiad
- **Labor**: Pilvevõrgu seadistamine simulatsioonitööriistadega
  - VPC ja alamvõrkude loomine
  - Koormusjaotuse seadistamine pilveressurssidele

### Nädal 20 (06.01.2025) - 2 Tundi
**Kursuse Ülevaade ja Lõpuprojekti Esitlus**
- Põhikontseptsioonide ülevaade
  - Kursuse jooksul õpitu kordamine
  - Parimad praktikad IT-infrastruktuuri haldamisel
- Lõpuprojektide esitlused
  - Õpilaste projektide tutvustus ja tagasiside
  - Arutelu reaalmaailma rakenduste üle

## Lõpuprojekt
- Õpilased viivad läbi reaalelu projekti, mis simuleerib IT-infrastruktuuri loomist ja haldamist.
- Projekt peab hõlmama:
  1. Virtualiseeritud keskkonna loomist
  2. Pilveteenuste integreerimist
  3. Võrgu ja turvalisuse konfiguratsiooni
  4. Automatiseeritud haldust ja monitooringut
  5. Varundus- ja taastestrateegia väljatöötamist
- Lõpuprojekt esitatakse 20. nädalal, kus õpilased jagavad oma õpitulemusi ja kogemusi klassiga.

## Hindamine ja Hindamiskriteeriumid
- **Laborid**: 40%
- **Osalemine**: 10%
- **Testid**: 10%
- **Lõpuprojekt**: 30%
- **Lõpueksam**: 10%

### Hindamisskaala
- A: 90-100%
- B: 80-89%
- C: 70-79%
- D: 60-69%
- F: <60%

## Kursuse Kogumaht: 52 Tundi