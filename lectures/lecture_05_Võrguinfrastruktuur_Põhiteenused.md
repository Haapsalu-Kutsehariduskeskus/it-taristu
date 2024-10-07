# 🌐 Võrguinfrastruktuur, DHCP ja DNS

Tere tulemast meie tehnilisele teekonnale läbi võrgumaailma! Täna sukeldume **DHCP** ja **DNS** protokollidesse, aga enne seda teeme ülevaate võrgutüüpidest.

## 🏙️ Võrgutüübid: Digitaalse Infrastruktuuri Alused

Kujutage ette, et võrgud on nagu erinevad linnaosad ja teed meie digitaalses maailmas:

- **LAN** (Local Area Network) on nagu <span style="color: #4CAF50;">**piiratud geograafiline ala**</span>, tavaliselt ühe organisatsiooni piires.
  - Kiirus: 10 Mbps kuni 10 Gbps
  - Protokollid: Ethernet (IEEE 802.3), Wi-Fi (IEEE 802.11)

- **WAN** (Wide Area Network) on kui <span style="color: #2196F3;">**geograafiliselt hajutatud võrkude ühendus**</span>.
  - Tehnoloogiad: MPLS, SD-WAN
  - Rakendused: Ettevõtete harukontorite ühendamine üle suurte vahemaade

- **VLAN** (Virtual LAN) on justkui <span style="color: #9C27B0;">**loogiline võrgu segmenteerimine**</span> füüsilise infrastruktuuri piires.
  - Standard: IEEE 802.1Q
  - Eelised: Parem turvalisus, liikluse optimeerimine, paindlik haldamine

- **WLAN** (Wireless LAN) on nagu <span style="color: #FF9800;">**traadita kohtvõrk**</span>, tavaliselt Wi-Fi põhine.
  - Standardid: IEEE 802.11 (a/b/g/n/ac/ax)
  - Turvalisus: WPA3, 802.1X autentimine

## 🎟️ DHCP: Võrgu Automaatne Konfiguraator

DHCP (Dynamic Host Configuration Protocol) on nagu <span style="color: #E91E63;">**automaatne süsteem, mis jagab seadmetele võrgukonfiguratsiooni**</span>.

### DHCP tööprotsess:

1. 🗣️ **DHCP Discover**: Klient saadab võrku laialipakettsõnumi (broadcast) UDP pordil 67.
2. 👋 **DHCP Offer**: Server vastab unicast-sõnumiga UDP pordil 68, pakkudes IP-aadressi ja konfiguratsiooni.
3. 🙏 **DHCP Request**: Klient kinnitab soovi pakutud konfiguratsiooni kasutada.
4. 🎉 **DHCP Acknowledge**: Server kinnitab konfiguratsiooni ja määrab liisinguperioodi.

**Miks see on oluline?** <span style="color: #4CAF50;">**DHCP automatiseerib võrgukonfiguratsiooni, vähendades käsitsi seadistamise vajadust ja vigu.**</span>

### DHCP olulised komponendid:

- 🕒 **Liisingute süsteem**: IP-aadresside ajutine määramine, tüüpiliselt 24 tundi kuni 7 päeva.
- 🌉 **DHCP relay**: Võimaldab DHCP-päringute edastamist eri võrgusegmentide vahel.
- 🛡️ **Turvalisus**: 
  - DHCP snooping: Kaitseb võlts-DHCP serverite vastu.
  - IP Source Guard: Takistab IP-aadresside võltsimist.

## 🗺️ DNS: Domeeninimede Süsteem

DNS (Domain Name System) on <span style="color: #FFC107;">**hajutatud hierarhiline süsteem domeeninimede ja IP-aadresside vastendamiseks**</span>.

### DNS tööpõhimõte:

1. 🕵️ Rekursiivne päring kliendilt kohalikule DNS-serverile.
2. 🗃️ Iteratiivne päring juurserveritele, TLD-serveritele ja autoritatiivsetele nimeserveritele.
3. 🔍 Vastuse tagastamine kliendile ja vahemällu salvestamine.
4. 🎯 Klient saab teada täpse IP-aadressi domeeninime jaoks.

### DNS-i olulised komponendid:

- 📚 **Kirjetüübid**:
  - **A**: IPv4 aadress
  - **AAAA**: IPv6 aadress
  - **CNAME**: Kanoonilise nime kirje (alias)
  - **MX**: Meiliserverite kirjed
  - **TXT**: Tekstikirjed (kasutatakse SPF, DKIM jaoks)

- 🔄 **Tsoonid**: 
  - Päringute tsoon: Domeeninimedest IP-aadressideks
  - Vastupäringute tsoon: IP-aadressidest domeeninimedeks

- 🔒 **Turvalisus**:
  - **DNSSEC**: Digitaalselt allkirjastatud DNS-kirjed turvalisuse tagamiseks.
  - **DoH (DNS üle HTTPS)**: Krüpteeritud DNS-päringud privaatsuse suurendamiseks.

## 🤝 DHCP ja DNS: Võrgu Dünaamiline Duo

DHCP ja DNS töötavad koos nagu <span style="color: #673AB7;">**sünkroniseeritud süsteem**</span>. DHCP annab seadmetele IP-aadressid ja DNS aitab neid aadresse domeeninimede kaudu tuvastada. See kombinatsioon tagab efektiivse ja kasutajasõbraliku võrgukogemuse.

## 🎓 Kokkuvõte

DHCP ja DNS on <span style="color: #FF5722;">**kriitilised protokollid, mis muudavad keerulise võrguarhitektuuri lihtsalt hallatavaks ja kasutatavaks**</span>. Nende tõhus toimimine on aluseks paljudele tänapäevastele võrgupõhistele teenustele ja rakendustele.

**Tehniline küsimus:** Kuidas mõjutaks DNSSEC rakendamine teie organisatsiooni DNS-infrastruktuuri ja millised oleksid peamised väljakutsed selle juurutamisel?