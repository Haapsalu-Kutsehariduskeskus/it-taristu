## Sessioon 1: IT-infrastruktuuri ülevaade

### 1.1 Mis on IT-infrastruktuur?

**Määratlus**: IT-infrastruktuur viitab füüsiliste ja virtuaalsete ressursside kogumile, mis toetavad andmete voogu, salvestamist, töötlemist ja analüüsi organisatsioonis. Mõtle sellele kui selgroole, mis hoiab kogu tehnoloogia organisatsioonis sujuvalt töös, sarnaselt närvisüsteemile inimese kehas. Ilma hästi organiseeritud ja korralikult töötava IT-infrastruktuurita oleks ettevõtetel raske tõhusalt toimida, kuna kõik kriitilised teenused, nagu võrgustik, andmete salvestamine ja rakenduste majutamine, ei töötaks efektiivselt.

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

## Sessioon 2: Virtualiseerimise kontseptsioonid

### 2.1 Virtualiseerimise tutvustus

**Määratlus**:  
Virtualiseerimine on tehnoloogia, mis võimaldab käitada ühte füüsilist serverit mitme **virtuaalse masinaga (VM)**. Need virtuaalsed masinad käituvad nagu sõltumatud arvutid oma operatsioonisüsteemide ja rakendustega. Sisuliselt on see nagu mitme "arvuti" omamine ühe füüsilise masina sees, kus kõik töötavad samaaegselt ilma eraldi riistvarata.

#### **Eelised**:

1. **Kulude kokkuhoid**:  
   Virtualiseerimine vähendab vajadust mitme füüsilise serveri järele. Selle asemel, et osta ja hooldada mitut serverit, saab ettevõte käitada mitut virtuaalset masinat ühe serveri peal. See säästab raha riistvara, elektri ja hoolduskulude pealt. Näiteks selle asemel, et osta viis füüsilist serverit, saab ettevõte kasutada ühte võimsat serverit, et majutada viis virtuaalset keskkonda.

2. **Ressursside tõhus kasutamine**:  
   Füüsilised serverid on tihti alakoormatud, kuna nende peal töötavad rakendused ei kasuta kõiki olemasolevaid protsessori, mälu või salvestusruumi ressursse. Virtualiseerimine võimaldab ettevõtetel kasutada serveri ressursse tõhusamalt, jagades serveri erinevatele virtuaalmasinatele. See tagab, et kogu serveri võimsus on kasutusel, maksimeerides jõudlust ja vähendades raiskamist.

3. **Skaleeritavus**:  
   Virtualiseerimine muudab ettevõtete IT-infrastruktuuri skaleerimise lihtsaks. Kui ettevõttel on vaja lisada uusi teenuseid või rakendusi, saab nad kiiresti luua uusi virtuaalmasinaid olemasolevatel serveritel. See paindlikkus võimaldab ettevõttel kasvada ilma vajaduseta kohe investeerida uude riistvarasse. Näiteks, kui on vaja rohkem salvestusruumi või töötlemisvõimsust, saab luua uue virtuaalmasina minutite jooksul.

4. **Isoleeritus**:  
   Iga virtuaalne masin töötab isoleeritult teistest. See tähendab, et kui üks virtuaalmasin jookseb kokku või tekib turvarikkumine, ei mõjuta see teisi. See isoleeritus muudab probleemide tuvastamise lihtsamaks, kuna probleemid ühes virtuaalses keskkonnas ei kandu üle teistesse. Näiteks, kui üks VM haldab veebiserverit ja teine andmebaasi, siis veebiserveri kokkujooksmine ei mõjuta andmebaasi VM-i, hoides süsteemid turvalisemad ja stabiilsemad.

Kokkuvõttes võimaldab virtualiseerimine ettevõtetel teha rohkem vähemate füüsiliste ressurssidega, vähendab kulusid ja annab paindlikkust kasvu jaoks, hoides süsteemid isoleeritud ja turvalised.

> ![Füüsiline server, mille peal töötab mitu virtuaalset masinat](/lectures/images/vm.png)
*Füüsiline server VM'idega*

---

### 2.2 Virtuaalmasinad (VM) vs konteinerid

IT-infrastruktuuris rakenduste ja teenuste haldamisel on nii virtuaalmasinad (VM) kui ka konteinerid populaarsed valikud, kuid neil on erinevad eesmärgid ja omadused.

#### 1. **Virtuaalmasinad (VM)**:
- **Emuleerivad tervet operatsioonisüsteemi**:  
  VM-id töötavad täisväärtusliku operatsioonisüsteemiga, mis jookseb host-süsteemi peal. Iga VM käitub nagu eraldi arvuti, täis oma operatsioonisüsteemi, olgu see siis Windows, Linux või mõni teine süsteem. See võimaldab VM-del töötada täielikult isoleeritud keskkondades, isegi kui neil on erinevad OS-versioonid.
  
- **Pühendatud ressursid**:  
  Iga VM saab oma osa hosti ressurssidest (CPU, RAM, salvestusruum). See garanteerib, et VM-l on oma pühendatud ressursid, mis lisab turvalisust ja isoleeritust teistest samal füüsilisel masinal töötavatest VM-idest.

- **Aeglasem käivitamine**:  
  Kuna VM-id emuleerivad kogu operatsioonisüsteemi ja haldavad oma ressursse, on nad raskemad ja võtavad rohkem aega käivitamiseks ja väljalülitamiseks kui konteinerid. VM-i käivitamine on sarnane füüsilise arvuti käivitamisele.

- **Kasutus**:  
  VM-e kasutatakse sageli siis, kui on vaja käitada erinevaid operatsioonisüsteeme või kui süsteemide vahel on vajalik range isoleeritus, näiteks kui üks VM majutab andmebaasiserverit ja teine veebiserverit.

#### 2. **Konteinerid**:
- **Jagavad sama OS-tuumat**:  
  Erinevalt VM-idest, konteinerid ei tööta oma operatsioonisüsteemiga. Selle asemel jagavad nad host-süsteemi OS-tuumat, mis tähendab, et neil ei ole vaja eraldi operatsioonisüsteemi. Konteinerid pakendavad rakendused koos kõigi nende sõltuvustega, kuid kasutavad sama baas-operatsioonisüsteemi.

- **Kerged ja kiired**:  
  Konteinerid on palju kergemad kui VM-id, sest nad ei vaja kogu OS-i emuleerimist. See teeb nende käivitamise ja seiskamise palju kiiremaks — sageli vaid mõne sekundi jooksul. See tõhusus muudab konteinerid ideaalseks olukordades, kus on oluline kiire juurutamine ja skaleerimine.

- **Ideaalne mikroteenuste jaoks**:  
  Konteinerid on eriti kasulikud kaasaegsetes rakendusearhitektuurides, nagu **mikroteenused**. Mikroteenuste arhitektuuris töötab iga teenus (näiteks kasutaja sisselogimisteenus, makseteenus jne) oma konteineris. See võimaldab suuremat paindlikkust, kuna teenuseid saab juurutada, uuendada ja skaleerida sõltumatult.

- **Kasutus**:  
  Konteinereid kasutatakse sageli rakenduste arendamisel ja juurutamisel, eriti keskkondades, kus kiirus, skaleeritavus ja ressursside tõhusus on olulised. Tööriistad nagu **Docker** on populaarsed konteinerite haldamiseks.

#### **Peamised erinevused**:
- **Isoleeritus**: VM-id pakuvad tugevamat isoleeritust, kuna nad töötavad täisväärtusliku OS-iga, samas kui konteinerid pakuvad kergemat isoleeritust sama OS-i sees.
- **Jõudlus**: Konteinerid käivituvad kiiremini ja kasutavad vähem ressursse, kuid VM-id pakuvad terviklikumat isoleeritust ja sobivad paremini erinevate OS-keskkondade käitamiseks.

> ![Virtuaalmasinate ja konteinerite võrdlus](/lectures/images/virt_vs_kont.png)
*Virtuaalmasinate ja konteinerite võrdlus*

---

### 2.3 Virtualiseerimistarkvara

Virtualiseerimist võimaldavaid tarkvarasid on mitut tüüpi, millest igaüks täidab erinevaid eesmärke, sõltuvalt ettevõtete ja arendajate vajadustest. Üldiselt võib need jagada kaheks: **hüperviisorid** ja **konteineriplatvormid**.

#### 1. **Hüperviisorid**:
Hüperviisorid on tarkvara tüüp, mida kasutatakse virtuaalmasinate loomiseks ja käitamiseks. Need võimaldavad mitmel operatsioonisüsteemil töötada ühel füüsilisel masinal, abstraktsema ja jaotades riistvara ressursid.

- **Tüüp 1 (Bare-metal)**:  
  Tüüp 1 hüperviisorid installitakse otse masina füüsilisele riistvarale, ilma et oleks vaja host-operatsioonisüsteemi. Need hüperviisorid pakuvad otsest juurdepääsu riistvarale, mis muudab need tõhusamaks ja ideaalseks suurtel ettevõtte kasutusaladel, eriti andmekeskustes. Tüüp 1 hüperviisorite näited:
  - **VMware ESXi**: Laialt kasutatav bare-metal hüperviisor, eriti suurtes andmekeskustes ja pilvekeskkondades, tuntud oma töökindluse ja jõudluse poolest.
  - **Microsoft Hyper-V**: Teine populaarne Tüüp 1 hüperviisor, mida sageli kasutatakse Microsofti-põhistes infrastruktuurides tuginevates ettevõtetes.

  **Kasutus**: Tüüp 1 hüperviisoreid kasutatakse peamiselt suurtes andmekeskustes, kus jõudlus ja ressursside haldamine on üliolulised. Need võimaldavad ettevõtetel käitada mitut virtuaalserverit samal füüsilisel riistvaral.

- **Tüüp 2 (Hosted)**:  
  Tüüp 2 hüperviisorid, tuntud ka kui "hostitud" hüperviisorid, töötavad olemasoleva operatsioonisüsteemi peal (nt Windows, macOS või Linux). Kuna need tuginevad host-OS-ile, ei ole nad nii tõhusad kui Tüüp 1 hüperviisorid, kuid nad on kergemini ligipääsetavad ja lihtsamini seadistatavad. Tüüp 2 hüperviisorite näited:
  - **VirtualBox**: Avatud lähtekoodiga hüperviisor, mis on populaarne isiklikuks kasutamiseks, testimiseks ja arenduseks. Toetab mitut operatsioonisüsteemi ja on lihtne installida.
  - **VMware Workstation**: Võimas töölaua hüperviisor, mida sageli kasutavad arendajad ja IT-spetsialistid testimiseks, silumiseks ja mitme operatsioonisüsteemi samaaegseks käitamiseks personaalarvutis.

  **Kasutus**: Tüüp 2 hüperviisoreid kasutavad üksikisikud või väikesed meeskonnad arenduseks, testimiseks ja erinevate keskkondade simulatsiooniks ühel masinal.

#### 2. **Konteineriplatvormid**:
Konteineriplatvormid pakuvad hüperviisoritele kerget alternatiivi. Täisväärtuslike operatsioonisüsteemide käitamise asemel võimaldavad konteineriplatvormid luua ja hallata isoleeritud keskkondi, mis jagavad hosti OS-i tuuma, muutes need kiiremateks ja ressursitõhusamaks.

- **Docker**:  
  Docker on kõige populaarsem platvorm konteinerite loomiseks, juurutamiseks ja haldamiseks. See võimaldab arendajatel pakendada rakendusi koos kõigi nende sõltuvustega isoleeritud konteineritesse. See tagab, et rakendus töötab ühtlaselt erinevates keskkondades, alates arendusest kuni tootmiseni.
  
  **Kasutus*: Dockerit kasutatakse laialdaselt arenduses ja tootmiskeskkondades rakenduste kiireks loomiseks, testimiseks ja juurutamiseks. Selle kerge loomus muudab selle ideaalseks mikroteenuste arhitektuuride jaoks, kus iga teenus saab töötada oma konteineris.

- **Kubernetes**:  
  Kubernetes on avatud lähtekoodiga platvorm, mis on loodud suurte konteinerite koguste haldamiseks. See automatiseerib konteineriseeritud rakenduste juurutamise, skaleerimise ja haldamise. Kubernetes aitab ettevõtetel hallata keerukaid konteineriseeritud keskkondi tõhusalt, orkestreerides konteinerite töö erinevatel masinatel.

  **Kasutus**: Kubernetesit kasutatakse tavaliselt suurtel tootmiskeskkondadel, kus on vaja juurutada, skaleerida ja hallata sadu või isegi tuhandeid konteinereid automaatselt. See on ideaalne pilvepõhiste rakenduste jaoks, mis vajavad suurt skaleeritavust ja töökindlust.

Kokkuvõttes pakuvad **hüperviisorid** võimalust käitada mitut virtuaalmasinat ühel füüsilisel serveril, samas kui **konteineriplatvormid** pakuvad kergemat ja skaleeritavamat viisi rakenduste käitamiseks isoleeritud keskkondades.

![Dockeri ja Kubernetese ikoonid](/lectures/images/kube_dok.png)
*Dockeri ja Kubernetes*

---


# [Lab 1.1: Virtuaalmasina seadistamine](./labs/lab_01_VM_Setup/lab_01.1_Setting_Up_a_VM.md)

> ![VirtualBoxi ja virtuaalmasina seadistamise protsessi ekraanipilt](/lectures/images/lab1.1.png)
*VirtualBoxi ja virtuaalmasin*

---

## Sessioon 3: Pilvandmetöötluse ülevaade

### 3.1 Pilvetaristu põhialused

**Määratlus**:  
Pilvandmetöötlus viitab IT-ressursside, nagu salvestusruumi, töötlemisvõimsuse ja rakenduste, pakkumisele üle interneti nõudmisel. Selle asemel, et omada ja hooldada füüsilist riistvara, saavad ettevõtted rentida neid ressursse pilveteenuse pakkujatelt. See mudel võimaldab ettevõtetel maksta ainult kasutatud teenuste eest, vähendades oma IT-infrastruktuuri haldamise kulusid ja keerukust. Mõtle sellele kui võimsa arvuti rentimisele pilves, millele pääsed ligi kõikjal maailmas, kui sul on internetiühendus.

---

#### **Pilveteenuste mudelid**:
Pilvandmetöötluse teenused jagunevad tavaliselt kolmeks peamiseks mudeliks: IaaS, PaaS ja SaaS. Iga mudel pakub erineval tasemel kontrolli ja abstraktsiooni, vastates erinevatele vajadustele ärikeskkondades ja arenduskeskkondades.

> ![Pizza(https://www.optimizely.com/contentassets/dc07499e97874038afcea97b4c89b785/3-pizza-as-a-service.png)
*Pizza teenusena" analoogia: On Prem, IaaS, PaaS ja SaaS*  
Source: [Optimizely Blog](https://www.optimizely.com/insights/blog/pizza-as-a-service/)

1. **IaaS (Infrastruktuur kui Teenus)**:  
   IaaS pakub virtualiseeritud arvutusressursse interneti kaudu, nagu virtuaalmasinad, salvestusruum ja võrguteenused. Kasutajatel on täielik kontroll operatsioonisüsteemide, rakenduste ja konfiguratsioonide üle, kuid nad ei pea haldama füüsilist riistvara. See mudel on väga paindlik ja seda kasutatakse sageli ettevõtetes virtuaalserverite, salvestuslahenduste või andmebaaside käitamiseks.
   - **Näide**: 
     - **AWS EC2 (Elastic Compute Cloud)**: Pakub virtuaalservereid, mida saab vastavalt nõudlusele suurendada või vähendada.
     - **Microsoft Azure VMs**: Azure pakub virtuaalmasinaid, mida kasutatakse rakenduste ja teenuste käitamiseks virtualiseeritud keskkonnas.
   - **Kasutus**: IaaS on ideaalne ettevõtetele, kes vajavad kiiret infrastruktuuri laiendamist või kes eelistavad täielikku kontrolli oma virtuaalmasinate ja salvestusruumi konfiguratsiooni üle.

2. **PaaS (Platvorm kui Teenus)**:  
   PaaS pakub platvormi, mis võimaldab arendajatel ehitada, testida ja juurutada rakendusi, ilma et nad peaksid muretsema infrastruktuuri, nagu serverite, salvestusruumi või võrkude haldamise pärast. Platvorm haldab infrastruktuuri, vabastades arendajad keskenduma koodi kirjutamisele ja rakenduste haldamisele.
   - **Näide**: 
     - **Google App Engine**: Täielikult hallatav platvorm, mis võimaldab arendajatel veebirakendusi juurutada ilma serveri haldamise muredeta.
     - **Heroku**: Platvorm, mis võimaldab arendajatel ehitada ja juurutada rakendusi erinevates programmeerimiskeeltes, abstraktides serveri haldamise.
   - **Kasutus**: PaaS sobib arendajatele ja meeskondadele, kes soovivad keskenduda rakenduste arendamisele ilma infrastruktuuri haldamise koormata. See lihtsustab juurutamist, skaleerimist ja hooldust.

3. **SaaS (Tarkvara kui Teenus)**:  
   SaaS pakub tarkvararakendusi interneti kaudu tellimusteenusena. Kasutajad saavad tarkvarale ligi pääseda igast seadmest, millel on internetiühendus, ilma et peaksid seda oma seadmetele installima või hooldama. Pilveteenuse pakkuja haldab kõike, sealhulgas infrastruktuuri, andmete turvalisust ja uuendusi.
   - **Näide**: 
     - **Office 365**: Pakub pilvepõhist juurdepääsu Microsofti tootlikkustööriistadele, nagu Word, Excel ja PowerPoint.
     - **Google Workspace**: Pilvepõhiste tootlikkustööriistade komplekt (nt Gmail, Docs, Drive), millele pääseb ligi igast seadmest.
   - **Kasutus**: SaaS on ideaalne ettevõtetele ja üksikisikutele, kes vajavad tarkvarale juurdepääsu ilma installimise, uuenduste või hooldusega seotud muredeta. See on kuluefektiivne ja lihtne kasutada, nõudes ainult internetiühendust.

---

Kokkuvõttes pakub pilvandmetöötlus paindlikke, skaleeritavaid ja kulutõhusaid viise IT-ressurssidele juurdepääsuks, kus erinevad teenuse mudelid (IaaS, PaaS, SaaS) rahuldavad erinevaid vajadusi, alates täielikust infrastruktuuri juhtimisest kuni lihtsa tarkvarakasutuseni.

> ![IaaS, PaaS ja SaaS mudelite skeem koos näidetega](/lectures/images/pilv_mud.png)
*Pilveteenuste mudelid*

---

### 3.2 Avalik vs privaatpilv

Pilvetaristut saab jagada vastavalt sellele, kes seda haldab ja kasutab. Avaliku, privaatse ja hübriidpilve erinevuste mõistmine on oluline, et ettevõtted saaksid valida oma vajadustele kõige sobivama lahenduse.

#### 1. **Avalik pilv**:
- **Määratlus**:  
  Avalikus pilves pakuvad teenuseid kolmandate osapoolte pilveteenuse pakkujad interneti kaudu. Need teenused võivad hõlmata salvestusruumi, töötlemisvõimsust, andmebaase ja rakendusi. Avaliku pilve ressursid jagatakse mitme kasutaja (või "rentniku") vahel, muutes selle kuluefektiivseks lahenduseks, kuna ettevõtted maksavad ainult nende ressursside eest, mida nad kasutavad.
  
- **Näited**:  
  - **AWS (Amazon Web Services)**: Üks suurimaid avaliku pilve pakkujaid, pakkudes laia valikut pilveteenuseid, sealhulgas arvutusvõimsust, salvestusruumi ja masinõpet.
  - **Microsoft Azure**: Avaliku pilve teenus, mis pakub virtuaalmasinaid, andmebaase ja võrgu teenuseid, muu hulgas.
  - **Google Cloud**: Veel üks suur pakkuja, kes pakub pilvesalvestust, arvutusvõimsust ja andmeanalüüsiteenuseid.

- **Kasutus**:  
  Avalik pilv on ideaalne väike- ja keskmise suurusega ettevõtetele ning idufirmadele, kes otsivad skaleeritavat ja kuluefektiivset lahendust ilma suurte alginvesteeringuteta infrastruktuuri. Avalik pilv on eriti kasulik, kui töökoormused on kõikuvad või kui ettevõtted vajavad oma teenuste kiiret skaleerimist.

---

#### 2. **Privaatpilv**:
- **Määratlus**:  
  Privaatpilv on pilvetaristu, mida kasutab ainult üks organisatsioon. Seda saab majutada ettevõtte enda andmekeskuses kohapeal või haldab seda kolmas osapool, kuid see pakub ettevõttele täielikku kontrolli ressursside, turvalisuse ja infrastruktuuri üle. Privaatpilved pakuvad kõrgemat privaatsust, muutes need ideaalseks tööstusharudes, kus kehtivad ranged regulatiivsed nõuded, näiteks tervishoius ja finantssektoris.

- **Näited**:  
  - **On-Premise privaatpilv**: Ettevõte võib oma andmekeskusesse ehitada oma privaatpilve, haldades riistvara, tarkvara ja turvalisust.
  - **Hostitud privaatpilv**: Mõned teenusepakkujad, nagu IBM Cloud või VMware, pakuvad privaatpilve keskkondi, mis on pühendatud ühele organisatsioonile, kuid majutatud väljaspool ettevõtte ruume.

- **Kasutus**:  
  Privaatpilve kasutatakse enamasti suurettevõtetes või organisatsioonides, kus on ranged turva- ja vastavusnõuded. See sobib ideaalselt ettevõtetele, kes vajavad suuremat kontrolli oma andmete üle, näiteks finantsasutustele, tervishoiuorganisatsioonidele või valitsusasutustele.

---

#### 3. **Hübriidpilv**:
- **Määratlus**:  
  Hübriidpilv on nii avaliku kui ka privaatpilve kombinatsioon, mis võimaldab ettevõtetel ära kasutada mõlemat. See võimaldab ettevõtetel hoida tundlikke andmeid ja kriitilisi rakendusi privaatpilves, samas kui avaliku pilve skaleeritavust ja paindlikkust kasutatakse vähem tundlike töökoormuste jaoks või täiendavate ressursside vajadusel.

- **Näited**:  
  - Ettevõte võib hoida oma kliendiandmeid privaatses pilves turvakaalutlustel, kasutades samal ajal avalikku pilve, nagu AWS või Google Cloud, veebimajutuseks või suurte andmeanalüüside käitamiseks.
  - **Microsoft Azure Stack**: Võimaldab ettevõtetel laiendada oma kohapealseid andmekeskusi Azure'i avalikku pilve, pakkudes sujuvat hübriidkogemust.

- **Kasutus**:  
  Hübriidpilv on ideaalne organisatsioonidele, kes peavad tasakaalustama turvalisust, kulusid ja skaleeritavust. See võimaldab ettevõtetel hoida teatud toiminguid oma privaatinfrastruktuuris, kasutades samal ajal avalikku pilve vähem tundlike töökoormuste jaoks või täiendava mahutavuse jaoks, kui nõudlus suureneb. Näiteks kõrge liiklusega perioodidel, nagu Black Friday, saavad ettevõtted kasutada avalikku pilve skaleerimiseks, säilitades samal ajal igapäevased toimingud privaatpilves.

---

Kokkuvõttes sõltub avaliku, privaatse ja hübriidpilve valik ettevõtte konkreetsetest vajadustest:
- **Avalik pilv** pakub paindlikkust ja kulude kokkuhoidu.
- **Privaatpilv** pakub suuremat kontrolli ja turvalisust.
- **Hübriidpilv** ühendab mõlema eelised, pakkudes paindlikkust ja kontrolli tundlike andmete üle.

![Avaliku, privaatse ja hübriidpilve võrdlusdiagramm](https://www.compatibl.com/wp-content/uploads/2020/01/Choosing-public-private-and-hybrid-cloud-1536x812.png)
*Avaliku, privaatse ja hübriidpilve võrdlusdiagramm*  
Source: [Compatibl](https://www.compatibl.com/wp-content/uploads/2020/01/Choosing-public-private-and-hybrid-cloud-1536x812.png)


---

### 3.3 Populaarsed pilveplatvormid

Pilveplatvormid on olulised ettevõtetele, kes otsivad oma infrastruktuuri skaleerimist, andmete salvestamist ja rakenduste tõhusat käitamist. Siin on kolm kõige populaarsemat pilveplatvormi, millest igaühel on oma tugevused ja unikaalsed omadused.

#### 1. **Amazon Web Services (AWS)**:
- **Ülevaade**:  
  AWS on suurim ja enimkasutatud pilveplatvorm maailmas. See pakub laia teenuste valikut, alates arvutusvõimsusest (virtuaalmasinad) kuni salvestuslahenduste, andmebaaside, masinõppe, võrgu- ja paljude muude teenusteni. AWS on tuntud oma skaleeritavuse ja paindlikkuse poolest, mis muudab selle sobivaks ettevõtetele igas suuruses, alates idufirmadest kuni suurte ettevõteteni.
  
- **Põhiteenused**:  
  - **EC2 (Elastic Compute Cloud)**: Pakub skaleeritavaid virtuaalmasinaid, mida saab hõlpsalt kohandada ja seadistada.
  - **S3 (Simple Storage Service)**: Väga skaleeritav ja turvaline pilvesalvestuslahendus andmete varundamiseks ja arhiveerimiseks.
  - **RDS (Relational Database Service)**: Hallatav relatsiooniline andmebaasiteenus, sealhulgas MySQL, PostgreSQL ja Oracle, ilma infrastruktuuri haldamise vaevata.

- **Kasutusjuht**:  
  AWS sobib ideaalselt organisatsioonidele, kes vajavad suurt paindlikkust, skaleeritavust ja laia tööriistade valikut. Seda kasutatakse laialdaselt tööstusharudes, alates e-kaubandusest (Amazoni enda infrastruktuur) kuni idufirmade ja globaalsete ettevõteteni, kes haldavad keerulisi IT-keskkondi.

---

#### 2. **Microsoft Azure**:
- **Ülevaade**:  
  Azure on Microsofti pilveplatvorm ja on tihedalt integreeritud olemasolevate Microsofti teenustega, nagu Office 365, Windows Server ja Active Directory. See teeb selle eriti populaarseks ettevõtete seas, kes juba tuginevad Microsofti-põhisele infrastruktuurile. Azure pakub laia teenuste komplekti, sealhulgas virtuaalmasinaid, andmebaase, tehisintellekti tööriistu ja palju muud, muutes selle sobivaks igas suuruses ettevõtetele.

- **Põhiteenused**:  
  - **Azure Virtual Machines**: Skaleeritavad virtuaalmasinad, mis integreeruvad sujuvalt Windowsi ja Linuxi keskkondadega.
  - **Azure Active Directory**: Pilvepõhine identiteedi ja juurdepääsu haldamise teenus, mis võimaldab ettevõtetel hallata rakenduste ja andmete juurdepääsu.
  - **Azure Blob Storage**: Kulutõhus ja skaleeritav pilvesalvestusteenus, mis on optimeeritud suurte struktureerimata andmekoguste salvestamiseks.

- **Kasutusjuht**:  
  Azure'i valivad sageli ettevõtted, kes on juba tugevalt investeerinud Microsofti toodetesse ja teenustesse. Selle tihe integreeritus selliste tööriistadega nagu **Office 365**, **SQL Server** ja **Azure Active Directory** teeb sellest tugeva valiku ettevõtetele, kes otsivad sujuvat üleminekut oma olemasolevate Microsofti keskkondade ja pilvetaristu vahel.

---

#### 3. **Google Cloud Platform (GCP)**:
- **Ülevaade**:  
  Google Cloud Platform on tuntud oma tugeva fookuse tõttu suurandmetele, masinõppele ja tehisintellektile. See pakub mitmesuguseid pilveteenuseid, kuid eriti paistab silma andmeanalüüsi ja tehisintellekti seotud teenuste poolest, muutes selle tipptasemel valikuks andmemahukate keskkondade või innovatiivsete tehnoloogiate, nagu masinõppe, jaoks.

- **Põhiteenused**:  
  - **BigQuery**: Täis-hallatav serveriteta andmeladu, mis võimaldab ettevõtetel teha kiireid SQL-päringuid suurtele andmekogumitele.
  - **Google Kubernetes Engine (GKE)**: Hallatav teenus konteineriseeritud rakenduste juurutamiseks, haldamiseks ja skaleerimiseks Kubernetese abil.
  - **Cloud AI ja masinõppeteenused**: AI tööriistade komplekt, sealhulgas ettevalmistatud mudelid ja kohandatud mudelite treenimine, mis aitavad ettevõtetel arendada masinõppe rakendusi.

- **Kasutusjuht**:  
  GCP on populaarne ettevõtetes, mis keskenduvad andmeanalüütikale, tehisintellektile ja masinõppele. Seda kasutatakse sageli sellistes valdkondades nagu rahandus, tervishoid ja tehnoloogia, kus on vaja võimsaid tööriistu suurte andmekogumite analüüsimiseks või AI mudelite loomiseks.

---

Kokkuvõttes pakuvad kolm suurt pilveplatvormi eristuvaid eeliseid:
- **AWS** on esimene valik ettevõtetele, kes vajavad suurt skaleeritavust ja laia valikut pilveteenuseid.
- **Microsoft Azure** on ideaalne ettevõtetele, kes soovivad integreeruda olemasolevate Microsofti tööriistade ja teenustega.
- **Google Cloud Platform** on eelistatud ettevõtetele, kes keskenduvad andmeanalüütikale, masinõppele ja AI innovatsioonidele.

> ![AWS, Azure ja Google Cloudi logod](https://alleo.tech/wp-content/uploads/2019/09/cropped-amazon-aws-microsoft-azure-google-cloud-1-768x431.png)
*AWS, Azure ja Google Cloudi logod*  
Source: [Alleo Tech](https://alleo.tech/2019/09/03/why-we-prefer-amazon-aws-to-microsoft-azure-and-google-cloud/)

---

## [Lab 1.2: Pilvekeskkonna seadistamine](./labs/lab_01_VM_Setup/lab_01.2_Cloud_Env_Setup.md)

> ![AWS või Azure VM seadistamise protsess](/lectures/images/Cloud_Env_Setup.png)
*AWS või Azure VM seadistamise protsess* 

---

### Sessie 4: Sissejuhatus serveritesse

### 4.1 Serverite tüübid

Serverid on IT-infrastruktuuri olulised osad, pakkudes erinevaid teenuseid klientidele ja kasutajatele. Siin on mõned levinumad serverite tüübid ja nende funktsioonid.

#### 1. **Veebiserverid**:
- **Ülevaade**:  
  Veebiserverid vastutavad veebisaitide majutamise eest ja veebilehtede edastamise eest kasutajate brauseritesse, kui nad külastavad veebisaiti. Kui pääsed veebisaidile, näiteks Google’isse, saadab sinu arvuti päringu veebiserverile, mis vastab, saates veebilehed tagasi sinu brauserisse.
  
- **Tuntud tarkvara**:  
  - **Apache**: Üks enimkasutatud veebiserveri tarkvara maailmas, tuntud oma paindlikkuse ja laia kogukonna toe poolest.
  - **Nginx**: Kõrge jõudlusega veebiserver, mida sageli kasutatakse staatilise sisu teenindamiseks, pöördproksina ja koormuse tasakaalustamiseks.
  
- **Kasutusjuht**:  
  Veebiserverid on interneti selgroog. Neid kasutavad ettevõtted, organisatsioonid ja eraisikud veebisaitide, blogide, veebirakenduste ja mistahes internetis kättesaadavate teenuste majutamiseks.

---

#### 2. **Andmebaasiserverid**:
- **Ülevaade**:  
  Andmebaasiserverid on pühendatud andmebaaside salvestamisele, haldamisele ja neile juurdepääsu pakkumisele. Need võimaldavad teistel rakendustel või kasutajatel teha toiminguid, nagu päringud, uuendused ja andmete kustutamine. Andmebaasiserverid on olulised igas rakenduses, mis vajab püsivat andmete salvestamist, näiteks e-kaubanduse veebisaidid, sotsiaalmeediaplatvormid ja ettevõtete süsteemid.
  
- **Tuntud tarkvara**:  
  - **MySQL**: Avatud lähtekoodiga relatsiooniline andmebaasi haldussüsteem (RDBMS), mida kasutatakse laialdaselt veebirakendustes ja andmete salvestamiseks. MySQL on tihti seotud LAMP-i stäkkiga (Linux, Apache, MySQL, PHP).
  - **PostgreSQL**: Teine populaarne avatud lähtekoodiga RDBMS, tuntud oma arenenud funktsioonide ja tugeva SQL-standardite järgimise poolest, sageli kasutatud keerukamates ja suure nõudlusega rakendustes.
  
- **Kasutusjuht**:  
  Andmebaasiservereid kasutatakse igasuguste andmete, näiteks kasutajainfo, tootekataloogide, tehinguandmete ja muu haldamiseks. Nad on lahutamatu osa veebirakendustest, ettevõtte tarkvarast ja äriluure süsteemidest.

---

#### 3. **Failiserverid**:
- **Ülevaade**:  
  Failiserverid pakuvad tsentraliseeritud asukohta, kus kasutajad saavad faile üles laadida, salvestada, alla laadida ja jagada. Neid kasutatakse sageli organisatsioonides, et võimaldada töötajatel juurdepääsu jagatud ressurssidele ja andmetele erinevatest asukohtadest või seadmetest. Failiserverid on loodud failide haldamiseks, turvamiseks ja jagamiseks võrgu kaudu.
  
- **Tuntud tarkvara**:  
  - **Samba**: Avatud lähtekoodiga tarkvara, mis võimaldab failide jagamist Linuxi ja Windowsi süsteemide vahel, rakendades SMB (Server Message Block) protokolli.
  - **FTP serverid**: File Transfer Protocol (FTP) serverid võimaldavad kasutajatel faile üles ja alla laadida interneti või kohaliku võrgu kaudu. Levinud FTP serveri tarkvara hõlmab **vsftpd** ja **ProFTPD**.

- **Kasutusjuht**:  
  Failiservereid kasutatakse nii väikestes kui ka suurtes organisatsioonides dokumentide haldamiseks, varunduslahendusteks ja jagatud failide kättesaadavuseks. Need on eriti kasulikud koostöökeskkondades, kus mitu kasutajat vajavad juurdepääsu samadele failidele ja kaustadele.

---

Kokkuvõttes täidavad erinevad serveritüübid IT-keskkondades erinevaid rolle teenuste haldamisel ja pakkumisel:
- **Veebiserverid** haldavad veebisaitide edastamist.
- **Andmebaasiserverid** haldavad andmete salvestamist ja neile juurdepääsu.
- **Failiserverid** hõlbustavad failide jagamist ja salvestamist.

> ![Serverid](https://pbs.twimg.com/media/GRoCR_OX0AAMHQU?format=jpg&name=large)
*Veebiserver, andmebaasiserver ja failiserver*  
Source: [SysXplore Tweet](https://pbs.twimg.com/media/GRoCR_OX0AAMHQU?format=jpg&name=large)


---

### 4.2 Põhiline serveri seadistamine

Serveri seadistamine on kriitiline osa serveri kasutuselevõtuks erinevates keskkondades. Kõige levinumad serverisüsteemid on **Windows Server** ja **Linux Server**, kummalgi on oma tugevused ja haldusviisid.

---

#### 1. **Windows Server**:
- **Ülevaade**:  
  Windows Server on Microsofti poolt välja töötatud populaarne serveri operatsioonisüsteem. Sellel on **graafiline kasutajaliides (GUI)**, mis teeb selle juurdepääsetavamaks ja lihtsamini kasutatavaks, eriti algajatele, kes ei pruugi olla tuttavad käsurealiidestega. Windows Server integreerub sujuvalt teiste Microsofti toodetega, nagu **Active Directory**, **SQL Server** ja **Exchange**, tehes sellest paljude Microsofti teenuseid kasutavate ettevõtete eelistatud valiku.

- **Peamised omadused**:  
  - **Graafiline haldus**: Graafiline liides võimaldab kasutajatel serverit seadistada ja hallata klõpsamismeetoditega, muutes sellised toimingud nagu kasutajakontode seadistamine, salvestuse haldamine ja turvasätete seadistamine intuitiivsemaks.
  - **Active Directory integreerimine**: Windows Serverit kasutatakse laialdaselt kasutajate autentimise, õiguste ja võrguturvalisuse haldamiseks ettevõttekeskkondades **Active Directory** kaudu.
  - **Microsofti ökosüsteemi ühilduvus**: Kui sinu organisatsioon kasutab selliseid tooteid nagu Office 365, Microsoft SQL Server või Exchange, pakub Windows Server sujuvat integratsiooni.

- **Kasutusjuht**:  
  Windows Serverit kasutatakse sageli keskmise suurusega ja suurtes ettevõtetes, mis toetuvad **Microsoft-põhisele infrastruktuurile**. Seda leidub sageli kontorikeskkondades, kus sellised rakendused nagu **SharePoint**, **Exchange** või **Active Directory** on vajalikud koostööks, e-posti teenusteks ja kasutajahalduseks.

- **Eelised**:  
  - Kasutajasõbralik neile, kes on tuttavad Microsofti toodetega.
  - Tugev integratsioon Microsofti ökosüsteemiga.
  - GUI muudab serveri haldamise lihtsamaks algajatele.

---

#### 2. **Linux Server**:
- **Ülevaade**:  
  Linux Server on avatud lähtekoodiga, väga kohandatav operatsioonisüsteem, mida kasutatakse paljudes keskkondades, eriti veebimajutuses ja avatud lähtekoodiga projektides. Erinevalt Windows Serverist hallatakse Linuxit peamiselt **käsurea liidese (CLI)** kaudu, mis nõuab suuremat tehnilist ekspertiisi, kuid pakub enneolematut paindlikkust ja kontrolli. Populaarsed Linuxi serveri distributsioonid hõlmavad **Ubuntu Server**, **CentOS** ja **Debian**.

- **Peamised omadused**:  
  - **Käsureapõhine haldamine**: Linuxi servereid hallatakse tavaliselt CLI kaudu, mis võimaldab administraatoritel serverit konfigureerida ja juhtida teksti põhiste käskudega. See lähenemine pakub sügavamaid kohandamisvõimalusi ja võib olla efektiivsem, kui see on hästi omandatud.
  - **Avatud lähtekoodiga paindlikkus**: Kuna Linux on avatud lähtekoodiga, saab seda vabalt muuta ja kohandada vastavalt konkreetsetele vajadustele. See teeb selle populaarseks arenduskeskkondades ja veebiserverite puhul.
  - **Turvalisus ja stabiilsus**: Linuxi serverid on tuntud oma stabiilsuse ja turvalisuse poolest. Avatud lähtekoodiga kogukond vaatab pidevalt süsteemi üle ja uuendab seda, muutes selle usaldusväärseks valikuks kriitiliste rakenduste jaoks.

- **Kasutusjuht**:  
  Linuxi serverid on **interneti selgroog** ja neid kasutatakse laialdaselt **veebimajutuses**, **pilve infrastruktuuris** ja **tarkvaraarenduses**. Seda eelistavad organisatsioonid, mis kasutavad avatud lähtekoodiga tarkvara, samuti arendajad, kes vajavad oma süsteemide üle suurt paindlikkust ja kontrolli.

- **Eelised**:  
  - Väga kohandatav ja paindlik.
  - Tasuta ja avatud lähtekoodiga, vähendades litsentsitasusid.
  - Äärmiselt stabiilne ja turvaline, eriti veebiserverite ja rakendusserverite jaoks.

---

**Peamised erinevused**:
- **Kasutusmugavus**:  
  - Windows Server pakub kasutajasõbralikku graafilist liidest lihtsamaks haldamiseks.
  - Linux Server, kuigi võimas, nõuab käsurea oskusi ja on järsema õppimiskõveraga.
  
- **Maksumus**:  
  - Windows Server vajab tasulist litsentsi.
  - Linux Server on avatud lähtekoodiga ja üldjuhul tasuta kasutamiseks, kuigi mõned distributsioonid võivad pakkuda tasulist tuge.

- **Sobivus kasutusjuhtumitele**:  
  - Windows Server sobib ideaalselt ettevõtetele, mis on seotud Microsofti toodetega.
  - Linux Serverit kasutatakse sageli veebiserverite, arenduskeskkondade ja avatud lähtekoodiga projektide puhul.

---

Kokkuvõttes sobib **Windows Server** ettevõtetele, kes otsivad kasutusmugavust ja tugevat Microsofti integratsiooni, samal ajal kui **Linux Server** pakub ületamatut paindlikkust ja turvalisust ning on eelistatud valik veebimajutuse ja arenduskeskkondade jaoks.

![Windows Server ja Linux Server](https://www.milesweb.in/blog/wp-content/uploads/2022/03/linux-vs-windows-server-the-ultimate-comparison.png)
*Windows Server ja Linux Server*  
Source: [MilesWeb Blog](https://www.milesweb.in/blog/hosting/server/linux-server-vs-windows-server/)


---

## [Lab 1.3: Põhiline serveri seadistamine](./labs/lab_01_VM_Setup/lab_01.3_Basic_Server_Setup.md)

> ![Linuxil veebiserveri seadistamine](/lectures/images/lab1.3.png)
*Põhiline serveri seadistamine*

---