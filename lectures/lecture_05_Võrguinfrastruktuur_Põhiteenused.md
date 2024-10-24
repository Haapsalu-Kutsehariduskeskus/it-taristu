# Võrguinfrastruktuur, DHCP ja DNS

## 1. Õppematerjali eesmärgid 🎯

Pärast selle materjali läbitöötamist:
- Mõistate erinevaid võrgutüüpe ja nende kasutuskohti
- Saate aru DHCP tööpõhimõtetest ja konfigureerimisest
- Oskate seadistada ja hallata DNS serverit
- Suudate tuvastada ja lahendada tavalisi võrguprobleeme

## 2. Võrgutüübid ja Infrastruktuur 🌐

### 2.1 Võrgutüüpide ülevaade

```mermaid
graph TB
    subgraph WAN[Wide Area Network]
        direction TB
        
        subgraph LK[" Kontor Londonis "]
            direction LR
            L_LAN[LAN]
            L_WLAN[WLAN/WiFi]
            subgraph L_VLAN[VLAN-id]
                L_V1[VLAN 10<br>Admin]
                L_V2[VLAN 20<br>Töötajad]
                L_V3[VLAN 30<br>Külalised]
            end
        end

        subgraph TK[" Kontor Tallinnas "]
            direction LR
            T_LAN[LAN]
            T_WLAN[WLAN/WiFi]
            subgraph T_VLAN[VLAN-id]
                T_V1[VLAN 10<br>Admin]
                T_V2[VLAN 20<br>Töötajad]
                T_V3[VLAN 30<br>Külalised]
            end
        end
        
        TK ---|Internet/VPN| LK
    end

    classDef lanStyle fill:#a8d5ff,stroke:#2196F3,stroke-width:2px
    classDef wlanStyle fill:#ffcca8,stroke:#FF9800,stroke-width:2px
    classDef vlanStyle fill:#d5a8ff,stroke:#9C27B0,stroke-width:2px
    classDef officeStyle fill:#f5f5f5,stroke:#333,stroke-width:2px
    classDef wanStyle fill:#f0f8ff,stroke:#2196F3,stroke-width:4px
    
    class L_LAN,T_LAN lanStyle
    class L_WLAN,T_WLAN wlanStyle
    class L_VLAN,T_VLAN,L_V1,L_V2,L_V3,T_V1,T_V2,T_V3 vlanStyle
    class LK,TK officeStyle
    class WAN wanStyle
```

### 2.2 Võrgutüüpide detailne kirjeldus

#### 2.2.1 LAN (Local Area Network)
- **Definitsioon**: Piiratud geograafilise ala võrk
- **Omadused**:
  - Kiirus: 10 Mbps kuni 10 Gbps
  - Madal latentsus: < 1ms
  - Kõrge turvalisus: füüsiliselt piiratud
- **Kasutuskohad**:
  - Kontorivõrgud
  - Koolivõrgud
  - Koduvõrgud
- **Eelised**:
  - Kiire andmeedastus
  - Lihtne hallata
  - Madal kulu

#### 2.2.2 WAN (Wide Area Network)
- **Definitsioon**: Geograafiliselt hajutatud võrkude ühendus
- **Tehnoloogiad**:
  - MPLS (Multiprotocol Label Switching)
  - SD-WAN (Software-Defined WAN)
  - VPN (Virtual Private Network)
- **Kasutuskohad**:
  - Rahvusvahelised ettevõtted
  - Pankade võrgud
  - Riigiasutuste võrgud
- **Väljakutsed**:
  - Kõrgem latentsus
  - Keerulisem haldamine
  - Suuremad kulud

#### 2.2.3 VLAN (Virtual LAN)
- **Definitsioon**: Loogiline võrgu segmenteerimine
- **Omadused**:
  - IEEE 802.1Q standard
  - VLAN ID: 1-4094
  - Paindlik konfiguratsioon
- **Kasutamise põhjused**:
  - Turvalisuse tõstmine
  - Liikluse eraldamine
  - Ressursside optimeerimine
- **Näited**:
  ```
  VLAN 10: Administratsioon (kõrge turvalisus)
  VLAN 20: Töötajad (tavaline turvalisus)
  VLAN 30: Külalised (piiratud ligipääs)
  ```

#### 2.2.4 WLAN (Wireless LAN)
- **Definitsioon**: Traadita kohtvõrk
- **Standardid**:
  - IEEE 802.11a/b/g/n/ac/ax
- **Turvameetmed**:
  - WPA3 krüpteering
  - MAC filtreerimine
  - 802.1X autentimine
- **Planeerimise aspektid**:
  - Leviala
  - Interferents
  - Kasutajate arv

## 3. DHCP (Dynamic Host Configuration Protocol) 🎟️

### 3.1 DHCP protsessi skeem

```mermaid
sequenceDiagram
    participant K as Klient
    participant D as DHCP Server
    
    note over K,D: Lab 4: DHCP Protsess
    
    K->>D: 1. DISCOVER
    Note right of K: UDP Broadcast<br/>Port 67
    
    D->>K: 2. OFFER
    Note left of D: IP: 192.168.1.100<br/>Mask: 255.255.255.0<br/>Gateway: 192.168.1.1
    
    K->>D: 3. REQUEST
    Note right of K: "Tahan seda IP-d!"
    
    D->>K: 4. ACK
    Note left of D: Liisingu kestvus<br/>+ võrguseaded
```

### 3.2 DHCP komponendid ja funktsioonid

#### 3.2.1 DHCP Server
- **Põhifunktsioonid**:
  - IP-aadresside haldamine
  - Võrguseadete jagamine
  - Liisingu haldamine
- **Konfigureeritavad parameetrid**:
  ```
  Scope: 192.168.1.0/24
  Range: 192.168.1.100 - 192.168.1.200
  Lease Time: 24h
  Exclusions: 192.168.1.1-192.168.1.10
  ```

#### 3.2.2 DHCP Klient
- **Põhifunktsioonid**:
  - DHCP avastamine
  - IP-aadressi taotlemine
  - Liisingu uuendamine
- **Olulised käsud**:
  ```
  ipconfig /release    # Vabasta IP
  ipconfig /renew      # Uuenda IP
  ipconfig /all        # Vaata seadeid
  ```

## 4. DNS (Domain Name System) 🗺️

### 4.1 DNS päringu protsess

```mermaid
sequenceDiagram
    participant K as Klient
    participant L as Lokaalne DNS
    participant A as Autoritatiivne DNS
    
    note over K,A: Lab 4: DNS Päringud
    
    K->>L: 1. Päring: www.example.com
    
    L->>A: 2. Rekursiivne päring
    A->>L: 3. Vastus: IP 93.184.216.34
    
    L->>K: 4. IP tagastamine
    Note right of K: Cache salvestamine
    
    note over K,A: Olulised DNS kirjed:
    note over K,A: A - IPv4 (nt: example.com = 192.168.1.10)
    note over K,A: CNAME - Alias (nt: www = example.com)
    note over K,A: MX - Meiliserver
```

### 4.2 DNS kirjete tüübid

| Kirje tüüp | Kasutus | Näide |
|------------|---------|--------|
| A | IPv4 aadress | example.com = 192.168.1.10 |
| AAAA | IPv6 aadress | example.com = 2001:db8::1 |
| CNAME | Alias | www = example.com |
| MX | Meiliserver | mail.example.com |
| TXT | Tekst | SPF, DKIM info |
| PTR | Reverse lookup | 192.168.1.10 = example.com |

### 4.3 DNS server tüübid
1. **Rekursiivne server**
   - Teeb päringuid teistele serveritele
   - Salvestab vastused vahemällu
   - Näide: ISP DNS server

2. **Autoritatiivne server**
   - Hoiab originaal DNS kirjeid
   - Vastab ainult oma tsooni päringutele
   - Näide: example.com nimeserver

## 5. Laborid ja Praktika 🔬

### 5.1 Lab 4: DHCP & DNS seadistamine
- DHCP serveri installimine
- IP-aadresside vahemiku määramine
- DNS kirjete loomine
- Testimine ja tõrkeotsing

### 5.2 Tavalised probleemid ja lahendused

#### 5.2.1 DHCP probleemid
- **Sümptom**: "Ei saa IP-aadressi"
  ```
  Kontroll: ipconfig /all
  Lahendus: ipconfig /release && ipconfig /renew
  ```

#### 5.2.2 DNS probleemid
- **Sümptom**: "Ei lahenda domeeninimesid"
  ```
  Kontroll: nslookup example.com
  Lahendus: ipconfig /flushdns
  ```

## 6. Kokkuvõte 📝

Selles peatükis õppisime:
1. Erinevaid võrgutüüpe ja nende kasutamist
2. DHCP tööpõhimõtteid ja seadistamist
3. DNS süsteemi struktuuri ja haldamist
4. Praktilisi oskusi läbi laboritöö

## 7. Lisamaterjalid 📚

- RFC 2131 (DHCP)
- RFC 1034, 1035 (DNS)
- Cisco CCNA materjalid
- Microsoft TechNet artiklid
