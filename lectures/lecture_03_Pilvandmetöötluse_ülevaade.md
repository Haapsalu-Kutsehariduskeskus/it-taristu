# 🌥️ Pilvandmetöötluse Ülevaade

## 3.1 Pilvetaristu põhialused

Pilvandmetöötlus on nagu <span style="color: #4CAF50;">**võimas arvuti, mida saad rentida üle interneti**</span>. Selle asemel, et osta ja hooldada oma servereid, saad kasutada kellegi teise omi - makstes ainult selle eest, mida kasutad.

### Pilveteenuste mudelid:

1. 🏗️ **IaaS (Infrastruktuur kui Teenus)**:
   - <span style="color: #FFC107;">Nagu tühja maja rentimine - sa saad selle sisustada just nii, nagu soovid.</span>
   - **Näide**: AWS EC2, Microsoft Azure VMs

2. 🛠️ **PaaS (Platvorm kui Teenus)**:
   - <span style="color: #2196F3;">Nagu sisustatud korteri rentimine - põhiasjad on olemas, sa lisad oma isiklikud asjad.</span>
   - **Näide**: Google App Engine, Heroku

3. 💼 **SaaS (Tarkvara kui Teenus)**:
   - <span style="color: #9C27B0;">Nagu hotellitoa broneerimine - kõik on valmis, sa lihtsalt kasutad.</span>
   - **Näide**: Office 365, Google Workspace

![Pizza as a Service analogy](https://www.optimizely.com/contentassets/dc07499e97874038afcea97b4c89b785/3-pizza-as-a-service.png)
*"Pizza teenusena" analoogia: On Prem, IaaS, PaaS ja SaaS*  
Allikas: [Optimizely Blog](https://www.optimizely.com/insights/blog/pizza-as-a-service/)

![IaaS, PaaS ja SaaS mudelite skeem koos näidetega](/lectures/images/pilv_mud.png)
*Pilveteenuste mudelid*

## 3.2 Avalik vs privaatpilv

### 1. 🌐 **Avalik pilv**:
- <span style="color: #4CAF50;">Nagu ühistransport - jagad ressursse teistega, aga see on odavam ja paindlikum.</span>
- **Näited**: AWS, Microsoft Azure, Google Cloud
- **Kasutus**: Ideaalne väikestele ja keskmise suurusega ettevõtetele, kes vajavad paindlikkust.

### 2. 🔒 **Privaatpilv**:
- <span style="color: #FF5722;">Nagu isiklik auto - täielik kontroll, aga kallim ja nõuab rohkem hooldust.</span>
- **Näited**: On-Premise privaatpilv, Hostitud privaatpilv (nt IBM Cloud)
- **Kasutus**: Sobib suurettevõtetele või organisatsioonidele rangete turvanõuetega.

### 3. 🔀 **Hübriidpilv**:
- <span style="color: #2196F3;">Nagu auto ja ühistranspordi kombineerimine - parim mõlemast maailmast.</span>
- **Näide**: Microsoft Azure Stack
- **Kasutus**: Organisatsioonidele, kes vajavad nii turvalisust kui ka paindlikkust.

![Avaliku, privaatse ja hübriidpilve võrdlusdiagramm](https://www.compatibl.com/wp-content/uploads/2020/01/Choosing-public-private-and-hybrid-cloud-1536x812.png)
*Avaliku, privaatse ja hübriidpilve võrdlusdiagramm*  
Allikas: [Compatibl](https://www.compatibl.com/wp-content/uploads/2020/01/Choosing-public-private-and-hybrid-cloud-1536x812.png)

## 3.3 Populaarsed pilveplatvormid

### 1. 🚀 **Amazon Web Services (AWS)**:
- <span style="color: #FFC107;">Nagu suur kaubamaja - kõik, mida vajad, on ühes kohas.</span>
- **Põhiteenused**: EC2 (virtuaalmasinad), S3 (salvestus), RDS (andmebaasid)
- **Kasutus**: Sobib kõigile, alates idufirmadest kuni suurettevõteteni.

### 2. 🌟 **Microsoft Azure**:
- <span style="color: #2196F3;">Nagu Microsofti toodete ja pilve abielu - ideaalne, kui kasutad juba Microsofti teenuseid.</span>
- **Põhiteenused**: Azure Virtual Machines, Azure Active Directory, Azure Blob Storage
- **Kasutus**: Eriti populaarne ettevõtete seas, kes kasutavad Microsofti tooteid.

### 3. 🧠 **Google Cloud Platform (GCP)**:
- <span style="color: #4CAF50;">Nagu teadlaste labor - eriti tugev andmeanalüüsis ja tehisintellektis.</span>
- **Põhiteenused**: BigQuery (andmeanalüüs), Google Kubernetes Engine, Cloud AI
- **Kasutus**: Ideaalne andmemahukate ja AI-põhiste projektide jaoks.

![AWS, Azure ja Google Cloudi logod](https://alleo.tech/wp-content/uploads/2019/09/cropped-amazon-aws-microsoft-azure-google-cloud-1-768x431.png)
*AWS, Azure ja Google Cloudi logod*  
Allikas: [Alleo Tech](https://alleo.tech/2019/09/03/why-we-prefer-amazon-aws-to-microsoft-azure-and-google-cloud/)

## 🔧 Praktiline osa

[Lab 2: Pilvekeskkonna seadistamine](../labs/lab_01_VM_Setup/lab_01.2_Cloud_Env_Setup.md)
*See labor keskendub pilvekeskkonna seadistamisele, kasutades Azure VM-i.*

![AWS või Azure VM seadistamise protsess](/lectures/images/Cloud_Env_Setup.png)
*AWS või Azure VM seadistamise protsess* 

## 🤔 Mõtlemiseks
- Millist pilveteenuse mudelit (IaaS, PaaS, SaaS) kasutaksid oma projekti jaoks ja miks?
- Kuidas otsustaksid avaliku ja privaatpilve vahel oma ettevõtte jaoks?
- Millised on sinu arvates suurimad eelised ja väljakutsed pilvandmetöötluse kasutamisel?