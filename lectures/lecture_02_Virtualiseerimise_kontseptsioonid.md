
## Sessioon 2: Virtualiseerimise kontseptsioonid

### 2.1 Virtualiseerimise tutvustus

**Kirjeldus**:  
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
