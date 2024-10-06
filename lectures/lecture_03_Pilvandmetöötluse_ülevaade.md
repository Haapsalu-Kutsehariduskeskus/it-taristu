
## Sessioon 3: Pilvandmetöötluse ülevaade

### 3.1 Pilvetaristu põhialused

**Kirjeldus**:  
Pilvandmetöötlus viitab IT-ressursside, nagu salvestusruumi, töötlemisvõimsuse ja rakenduste, pakkumisele üle interneti nõudmisel. Selle asemel, et omada ja hooldada füüsilist riistvara, saavad ettevõtted rentida neid ressursse pilveteenuse pakkujatelt. See mudel võimaldab ettevõtetel maksta ainult kasutatud teenuste eest, vähendades oma IT-infrastruktuuri haldamise kulusid ja keerukust. Mõtle sellele kui võimsa arvuti rentimisele pilves, millele pääsed ligi kõikjal maailmas, kui sul on internetiühendus.

---

#### **Pilveteenuste mudelid**:
Pilvandmetöötluse teenused jagunevad tavaliselt kolmeks peamiseks mudeliks: IaaS, PaaS ja SaaS. Iga mudel pakub erineval tasemel kontrolli ja abstraktsiooni, vastates erinevatele vajadustele ärikeskkondades ja arenduskeskkondades.

> ![Pizza as a Service analogy](https://www.optimizely.com/contentassets/dc07499e97874038afcea97b4c89b785/3-pizza-as-a-service.png)
*"Pizza teenusena" analoogia: On Prem, IaaS, PaaS ja SaaS*  
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
- **Kirjeldus**:  
  Avalikus pilves pakuvad teenuseid kolmandate osapoolte pilveteenuse pakkujad interneti kaudu. Need teenused võivad hõlmata salvestusruumi, töötlemisvõimsust, andmebaase ja rakendusi. Avaliku pilve ressursid jagatakse mitme kasutaja (või "rentniku") vahel, muutes selle kuluefektiivseks lahenduseks, kuna ettevõtted maksavad ainult nende ressursside eest, mida nad kasutavad.
  
- **Näited**:  
  - **AWS (Amazon Web Services)**: Üks suurimaid avaliku pilve pakkujaid, pakkudes laia valikut pilveteenuseid, sealhulgas arvutusvõimsust, salvestusruumi ja masinõpet.
  - **Microsoft Azure**: Avaliku pilve teenus, mis pakub virtuaalmasinaid, andmebaase ja võrgu teenuseid, muu hulgas.
  - **Google Cloud**: Veel üks suur pakkuja, kes pakub pilvesalvestust, arvutusvõimsust ja andmeanalüüsiteenuseid.

- **Kasutus**:  
  Avalik pilv on ideaalne väike- ja keskmise suurusega ettevõtetele ning idufirmadele, kes otsivad skaleeritavat ja kuluefektiivset lahendust ilma suurte alginvesteeringuteta infrastruktuuri. Avalik pilv on eriti kasulik, kui töökoormused on kõikuvad või kui ettevõtted vajavad oma teenuste kiiret skaleerimist.

---

#### 2. **Privaatpilv**:
- **Kirjeldus**:  
  Privaatpilv on pilvetaristu, mida kasutab ainult üks organisatsioon. Seda saab majutada ettevõtte enda andmekeskuses kohapeal või haldab seda kolmas osapool, kuid see pakub ettevõttele täielikku kontrolli ressursside, turvalisuse ja infrastruktuuri üle. Privaatpilved pakuvad kõrgemat privaatsust, muutes need ideaalseks tööstusharudes, kus kehtivad ranged regulatiivsed nõuded, näiteks tervishoius ja finantssektoris.

- **Näited**:  
  - **On-Premise privaatpilv**: Ettevõte võib oma andmekeskusesse ehitada oma privaatpilve, haldades riistvara, tarkvara ja turvalisust.
  - **Hostitud privaatpilv**: Mõned teenusepakkujad, nagu IBM Cloud või VMware, pakuvad privaatpilve keskkondi, mis on pühendatud ühele organisatsioonile, kuid majutatud väljaspool ettevõtte ruume.

- **Kasutus**:  
  Privaatpilve kasutatakse enamasti suurettevõtetes või organisatsioonides, kus on ranged turva- ja vastavusnõuded. See sobib ideaalselt ettevõtetele, kes vajavad suuremat kontrolli oma andmete üle, näiteks finantsasutustele, tervishoiuorganisatsioonidele või valitsusasutustele.

---

#### 3. **Hübriidpilv**:
- **Kirjeldus**:  
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

- **Kasutus**:  
  AWS sobib ideaalselt organisatsioonidele, kes vajavad suurt paindlikkust, skaleeritavust ja laia tööriistade valikut. Seda kasutatakse laialdaselt tööstusharudes, alates e-kaubandusest (Amazoni enda infrastruktuur) kuni idufirmade ja globaalsete ettevõteteni, kes haldavad keerulisi IT-keskkondi.

---

#### 2. **Microsoft Azure**:
- **Ülevaade**:  
  Azure on Microsofti pilveplatvorm ja on tihedalt integreeritud olemasolevate Microsofti teenustega, nagu Office 365, Windows Server ja Active Directory. See teeb selle eriti populaarseks ettevõtete seas, kes juba tuginevad Microsofti-põhisele infrastruktuurile. Azure pakub laia teenuste komplekti, sealhulgas virtuaalmasinaid, andmebaase, tehisintellekti tööriistu ja palju muud, muutes selle sobivaks igas suuruses ettevõtetele.

- **Põhiteenused**:  
  - **Azure Virtual Machines**: Skaleeritavad virtuaalmasinad, mis integreeruvad sujuvalt Windowsi ja Linuxi keskkondadega.
  - **Azure Active Directory**: Pilvepõhine identiteedi ja juurdepääsu haldamise teenus, mis võimaldab ettevõtetel hallata rakenduste ja andmete juurdepääsu.
  - **Azure Blob Storage**: Kulutõhus ja skaleeritav pilvesalvestusteenus, mis on optimeeritud suurte struktureerimata andmekoguste salvestamiseks.

- **Kasutus**:  
  Azure'i valivad sageli ettevõtted, kes on juba tugevalt investeerinud Microsofti toodetesse ja teenustesse. Selle tihe integreeritus selliste tööriistadega nagu **Office 365**, **SQL Server** ja **Azure Active Directory** teeb sellest tugeva valiku ettevõtetele, kes otsivad sujuvat üleminekut oma olemasolevate Microsofti keskkondade ja pilvetaristu vahel.

---

#### 3. **Google Cloud Platform (GCP)**:
- **Ülevaade**:  
  Google Cloud Platform on tuntud oma tugeva fookuse tõttu suurandmetele, masinõppele ja tehisintellektile. See pakub mitmesuguseid pilveteenuseid, kuid eriti paistab silma andmeanalüüsi ja tehisintellekti seotud teenuste poolest, muutes selle tipptasemel valikuks andmemahukate keskkondade või innovatiivsete tehnoloogiate, nagu masinõppe, jaoks.

- **Põhiteenused**:  
  - **BigQuery**: Täis-hallatav serveriteta andmeladu, mis võimaldab ettevõtetel teha kiireid SQL-päringuid suurtele andmekogumitele.
  - **Google Kubernetes Engine (GKE)**: Hallatav teenus konteineriseeritud rakenduste juurutamiseks, haldamiseks ja skaleerimiseks Kubernetese abil.
  - **Cloud AI ja masinõppeteenused**: AI tööriistade komplekt, sealhulgas ettevalmistatud mudelid ja kohandatud mudelite treenimine, mis aitavad ettevõtetel arendada masinõppe rakendusi.

- **Kasutus**:  
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

## [Lab 2: Pilvekeskkonna seadistamine](../labs/lab_01_VM_Setup/lab_01.2_Cloud_Env_Setup.md)
*See labor keskendub pilvekeskkonna seadistamisele, kasutades Azure VM-i.*

> ![AWS või Azure VM seadistamise protsess](/lectures/images/Cloud_Env_Setup.png)
*AWS või Azure VM seadistamise protsess* 

---
