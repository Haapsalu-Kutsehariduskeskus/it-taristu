## Sessioon 1: IT-infrastruktuuri ülevaade

### 1.1 Mis on IT-infrastruktuur?

**Kirjeldus**: IT-infrastruktuur viitab füüsiliste ja virtuaalsete ressursside kogumile, mis toetavad andmete voogu, salvestamist, töötlemist ja analüüsi organisatsioonis. Mõtle sellele kui selgroole, mis hoiab kogu tehnoloogia organisatsioonis sujuvalt töös, sarnaselt närvisüsteemile inimese kehas. Ilma hästi organiseeritud ja korralikult töötava IT-infrastruktuurita oleks ettevõtetel raske tõhusalt toimida, kuna kõik kriitilised teenused, nagu võrgustik, andmete salvestamine ja rakenduste majutamine, ei töötaks efektiivselt.

IT-infrastruktuur võib paikneda **kohapealsetes süsteemides** (seadmed, mis asuvad organisatsiooni rajatistes) ja **pilvepõhistes süsteemides** (ressursid, mis asuvad kaugserverites, mida haldab kolmas osapool). Kaasaegsetes IT-keskkondades on infrastruktuurid sageli nende kahe kombinatsioon.

#### Põhikomponendid:

- **Riistvara**: Füüsilised seadmed, mis moodustavad IT-infrastruktuuri aluse. Nende hulka kuuluvad:
  - **Serverid**: Arvutid, mis on pühendatud võrguresursside haldamisele, andmete salvestamisele, rakenduste majutamisele või kasutajate päringute töötlemisele.
  - **Salvestusseadmed**: Riistvara, mis salvestab andmeid, näiteks kõvakettad, SSD-d ja võrguga ühendatud salvestussüsteemid (NAS).
  - **Võrguseadmed**: Seadmed, nagu ruuterid, kommutaatorid ja tulemüürid, mis võimaldavad arvutite vahelist suhtlust ja kaitsevad võrku.
  - **Kliendiseadmed**: Lõppkasutajate seadmed, nagu arvutid, sülearvutid, mobiiltelefonid ja tahvelarvutid, mida kasutatakse võrgu ja ressursside kasutamiseks.

- **Tarkvara**: Programmid ja süsteemid, mis võimaldavad riistvaral töötada ja hallata. Põhitarkvara sisaldab:
  - **Operatsioonisüsteemid**: Tarkvara, mis haldab riist- ja tarkvararesursse (nt Windows Server, Linux).
  - **Rakendused**: Programmid, mis töötavad operatsioonisüsteemis kindlate funktsioonide täitmiseks (nt e-postisüsteemid, ettevõtte ressursside planeerimise tarkvara).
  - **Andmebaasid**: Tarkvara, mida kasutatakse andmete tõhusaks salvestamiseks, haldamiseks ja päringute esitamiseks (nt MySQL, PostgreSQL).
  - **Haldussüsteemid**: Tööriistad, mida kasutatakse IT-infrastruktuuri jälgimiseks ja haldamiseks, nagu võrguhaldus ja virtualiseerimise platvormid.

- **Andmekeskused**: Need on spetsiaalsed rajatised, mis on loodud suure hulga serverite, salvestussüsteemide ja võrguriistvara majutamiseks. Nad pakuvad olulist keskkonda suure hulga andmete salvestamiseks ja töötlemiseks, sisaldades sageli varutoitesüsteeme, varundatud võrke ja jahutussüsteeme. Mõned organisatsioonid haldavad oma andmekeskusi, teised aga kasutavad kolmandate osapoolte pakkujaid, nagu pilveteenuse pakkujad (CSP-d), näiteks AWS, Google Cloud või Azure. Andmekeskused on olulised teenuste kõrge kättesaadavuse tagamiseks.

- **Võrgud**: Võrgud ühendavad IT-infrastruktuuri erinevaid seadmeid, võimaldades andmete jagamist ja töötlemist. Nad tagavad suhtluse riistvara, tarkvara ja kasutajate vahel:
  - **Lokal Area Networks (LAN)**: Ühendab seadmeid piiratud alal, näiteks hoones või ülikoolilinnakus.
  - **Wide Area Networks (WAN)**: Ulatuvad üle suurte geograafiliste alade, ühendades mitu LAN-i. Internet ise on tohutu WAN.
  - **Virtuaalsed võrgud**: Tarkvaraliselt määratletud võrgud (SDN-d) ja virtuaalsed privaatvõrgud (VPN-d) võimaldavad turvalist, paindlikku võrku füüsilistes ja pilvekeskkondades.
  - **Pilvevõrgud**: Pakuvad virtualiseeritud võrgutaristut, mida haldavad kolmandate osapoolte teenused, võimaldades organisatsioonidel oma võrku ja ressursse lihtsalt skaleerida.

---

### 1.2 IT-infrastruktuuri võtmekomponendid

#### 1. **Serverid**:
Serverid on võimsad arvutid, mis on mõeldud konkreetsete ülesannete täitmiseks, näiteks veebilehtede majutamiseks, andmebaaside haldamiseks või failide salvestamiseks. Näiteks võib server majutada teie lemmikveebilehte või salvestada teie kooli andmeid.

#### 2. **Salvestussüsteemid**:
- **Kohalik salvestus**: Kõvakettad või SSD-d, mis on ühendatud individuaalsete arvutite või serveritega, kuhu salvestatakse kõik isiklikud failid.
- **Võrgusalvestus**: NAS (Network-Attached Storage) ja SAN (Storage Area Network) süsteemid võimaldavad andmeid salvestada ja neid jagada mitmete seadmete vahel võrgu kaudu.

#### 3. **Võrguseadmed**:
- **Ruuterid**: Need juhivad andmevoogu seadmete ja Interneti vahel, tagades, et e-kirjad, veebilehed ja muud andmed jõuavad õigesse kohta.
- **Kommutaatorid**: Need võimaldavad erinevate seadmete (nt arvutid, printerid jne) ühendamist ühe võrgu kaudu.
- **Tulemüürid**: Seadmed, mis aitavad kaitsta võrku, blokeerides soovimatuid andmeid, nagu turvamees, kes kaitseb hoonet.

#### 4. **Virtualiseerimine**:
Virtualiseerimine võimaldab ühel füüsilisel riistvarasüsteemil töötada mitmes virtuaalses keskkonnas. See tähendab, et üks arvuti võib toimida nagu mitu arvutit, säästes raha ja ruumi.

> ![Väikese kontori IT-seadistuse skeem serverite, võrgu ja pilve varundamisega](/lectures/images/office.webp)
*Väike kontor*
---

### 1.3 Case Study: IT-infrastruktuur väike- ja keskmise suurusega ettevõtetes (SME-d)

Kujutame ette väikest turundusagentuuri, kus töötab 50 inimest. Nad peavad haldama erinevaid oma äritegevuse aspekte, sealhulgas kliendiandmete salvestamist, veebimajutust ja tagama, et töötajad saaksid töötada igalt poolt. Siin on ülevaade sellest, kuidas nad saaksid oma IT-infrastruktuuri üles seada:

#### **Skeem**:

- **Riistvara**: Agentuuril on kaks füüsilist serverit:
  - **Server 1**: Pühendatud oma veebisaidi majutamiseks, mis on oluline kliendisuhtluse ja teenuste tutvustamiseks.
  - **Server 2**: Kasutatakse kriitiliste kliendiandmete salvestamiseks, tagades, et kõik andmed on kontoris kättesaadavad, kuid kaitstud väliste ohtude eest.
  
- **Võrgu seadistus**: Kõik kontori töötajad on ühendatud kohaliku võrgu (LAN) kaudu. Seda võrku kaitseb tulemüür, mis toimib barjäärina nende sisemiste süsteemide ja välise interneti vahel, kaitstes neid volitamata juurdepääsu ja küberohtude eest.

- **Virtualiseerimine**: Et maksimeerida oma riistvara, kasutab agentuur esimesel serveril virtualiseerimist. See tähendab, et server töötab mitme **virtuaalse masinaga (VM)**, millest igaüks on pühendatud kindlale ülesandele. Näiteks:
  - Üks VM haldab **veebimajutust**.
  - Teine VM vastutab **andmebaaside haldamise** eest.
  - Veel üks VM võib hallata agentuuri sisemisi tööriistu, tagades, et iga ülesanne on isoleeritud ja turvaline.

- **Pilveteenuste kasutamine**: Lisaks oma füüsilisele infrastruktuurile kasutab agentuur **pilveteenuseid**, et varundada olulisi andmeid ja hoida neid turvalisena juhuks, kui riistvara rikke korral. Nad kasutavad ka selliseid rakendusi nagu **Google Workspace** (e-post, dokumendid ja kalender) pilves, mis võimaldab töötajatel lihtsalt teha koostööd, jagada dokumente ja töötada eemalt, kas kodus või reisil olles.

Selline hübriidne lähenemine, mis ühendab kohapealse riistvara ja pilveteenused, võimaldab turundusagentuuril jääda paindlikuks, kaitsta oma andmeid ja anda töötajatele vajalikud tööriistad tõhusaks tööks.

> ![Väikese kontori IT-seadistuse skeem serverite, võrgu ja pilve varundamisega](/lectures/images/sme_infra_setup.png)

*Väikese kontori IT-seadistuse skeem serverite, võrgu ja pilve varundamisega*


---
