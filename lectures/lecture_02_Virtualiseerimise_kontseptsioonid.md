# 🖥️ Virtualiseerimise Kontseptsioonid

## 2.1 Virtualiseerimise tutvustus

Virtualiseerimine on tehnoloogia, mis võimaldab ühe füüsilise serveri ressursside jagamist mitme virtuaalse masina (VM) vahel. See toimib abstraktsioonikihina riistvara ja tarkvara vahel.

<span style="color: #4CAF50;">**Võrdlus:** Nagu ühe suure maja jagamine mitmeks eraldi korteriks, kus igal korteril on oma "elanikud" (operatsioonisüsteemid ja rakendused).</span>

### Eelised:

1. **Kulude kokkuhoid**:
   - Vähendab füüsiliste serverite arvu ja sellega seotud kulusid (elekter, jahutus, ruum).
   - <span style="color: #FFC107;">Tehniline näide: Üks võimas server 32 tuuma ja 256GB RAM-iga võib asendada mitut väiksemat serverit.</span>

2. **Ressursside tõhus kasutamine**:
   - Dünaamiline ressursside jaotamine VM-ide vahel.
   - <span style="color: #2196F3;">Tehniline näide: VMware vSphere DRS (Distributed Resource Scheduler) optimeerib automaatselt ressursside jaotust.</span>

3. **Skaleeritavus**:
   - Kiire VM-ide lisamine või eemaldamine vastavalt vajadustele.
   - <span style="color: #9C27B0;">Tehniline näide: Pilveteenused nagu AWS EC2 võimaldavad VM-ide automaatset skaleerimist (Auto Scaling).</span>

4. **Isoleeritus**:
   - VM-id töötavad eraldatult, parandades turvalisust ja stabiilsust.
   - <span style="color: #FF5722;">Tehniline näide: Hüperviisor tagab VM-ide vahel mälu isolatsiooni, kasutades tehnikaid nagu pagineerimistabelite virtualiseerimine.</span>

![Füüsiline server VM'idega](./images/vm.png)
*Füüsiline server VM'idega*

## 2.2 Virtuaalmasinad (VM) vs konteinerid

### 1. Virtuaalmasinad (VM):
- Emuleerivad täielikku riistvara ja operatsioonisüsteemi.
- Kasutavad hüperviisori tehnoloogiat ressursside haldamiseks.
- <span style="color: #4CAF50;">Tehniline näide: VMware ESXi kasutab binaarset translatsiooni ja otsest käskude täitmist (VT-x/AMD-V) VM-ide jõudluse optimeerimiseks.</span>

### 2. Konteinerid:
- Jagavad host OS-i tuuma, kuid pakuvad isoleeritud jooksukeskkonda rakendustele.
- Kasutavad OS-i tasemel virtualiseerimist (näiteks Linux namespaces ja cgroups).
- <span style="color: #2196F3;">Tehniline näide: Docker kasutab UnionFS-i kihtidel põhinevat failisüsteemi, mis võimaldab efektiivset pildihaldusmehhanismi.</span>

![Virtuaalmasinate ja konteinerite võrdlus](./images/virt_vs_kont.png)
*Virtuaalmasinate ja konteinerite võrdlus*

## 2.3 Virtualiseerimistarkvara

### 1. Hüperviisorid:
- **Tüüp 1 (Bare-metal)**:
  - Töötavad otse riistvaral, pakkudes parimat jõudlust.
  - Näited: VMware ESXi, Microsoft Hyper-V Server
  - <span style="color: #FFC107;">Tehniline detail: Kasutavad riistvara virtualiseerimise tehnoloogiaid nagu Intel VT-x või AMD-V otseseks juurdepääsuks CPU ressurssidele.</span>

- **Tüüp 2 (Hosted)**:
  - Töötavad olemasoleva operatsioonisüsteemi peal.
  - Näited: VirtualBox, VMware Workstation
  - <span style="color: #9C27B0;">Tehniline detail: Kasutavad hosti OS-i draiverid I/O operatsioonideks, mis võib põhjustada väikest jõudluse vähenemist võrreldes Tüüp 1-ga.</span>

### 2. Konteineriplatvormid:
- **Docker**:
  - Kasutab LXC (Linux Containers) tehnoloogiat.
  - <span style="color: #4CAF50;">Tehniline detail: Docker Engine kasutab libcontainer teeki konteinerite loomiseks ja haldamiseks.</span>

- **Kubernetes**:
  - Avatud lähtekoodiga konteinerite orkestreerimisplatvorm.
  - <span style="color: #2196F3;">Tehniline detail: Kasutab etcd hajutatud võtme-väärtuse andmebaasi klastri oleku säilitamiseks.</span>

![Docker ja Kubernetes](./images/kube_dok.png)
*Docker ja Kubernetes*

## 🔧 Praktiline osa

[Lab 1: Virtuaalmasina seadistamine](../labs/lab_01_VM_Setup/lab_01_Setting_Up_a_VM.md)
*See labor keskendub virtuaalmasina seadistamisele kasutades VirtualBoxi.*

![VirtualBoxi ja virtuaalmasina seadistamise protsess](./images/lab1.1.png)
*VirtualBoxi ja virtuaalmasina seadistamise protsess*

## 🤔 Arutelu küsimused
1. Kuidas mõjutab virtualiseerimise kasutuselevõtt ettevõtte IT-infrastruktuuri haldamist ja kulusid?
2. Millised on peamised tehnilised erinevused tüüp 1 ja tüüp 2 hüperviisorite vahel ja kuidas need mõjutavad jõudlust?
3. Millistes stsenaariumides eelistaksite konteinereid virtuaalmasinatele ja vastupidi?