# 🖥️ IT-infrastruktuuri Ülevaade

## 1.1 Mis on IT-infrastruktuur?

IT-infrastruktuur on nagu <span style="color: #4CAF50;">**organisatsiooni tehnoloogiline selgroog**</span>. See hõlmab kõiki füüsilisi ja virtuaalseid ressursse, mis toetavad andmete liikumist, salvestamist ja töötlemist.

### Põhikomponendid:

1. 🖧 **Riistvara**:
   - Serverid: <span style="color: #FFC107;">Võimsad arvutid, mis töötlevad andmeid ja majutavad rakendusi.</span>
   - Salvestusseadmed: <span style="color: #2196F3;">Hoiavad andmeid (nt. kõvakettad, SSD-d).</span>
   - Võrguseadmed: <span style="color: #9C27B0;">Ühendavad seadmeid (nt. ruuterid, kommutaatorid).</span>
   - Kliendiseadmed: <span style="color: #FF5722;">Lõppkasutajate seadmed (nt. arvutid, tahvelarvutid).</span>

2. 💻 **Tarkvara**:
   - Operatsioonisüsteemid: <span style="color: #4CAF50;">Haldavad riistvara (nt. Windows Server, Linux).</span>
   - Rakendused: <span style="color: #2196F3;">Täidavad spetsiifilisi ülesandeid.</span>
   - Andmebaasid: <span style="color: #9C27B0;">Salvestavad ja haldavad andmeid (nt. MySQL).</span>
   - Haldussüsteemid: <span style="color: #FF5722;">Jälgivad ja haldavad infrastruktuuri.</span>

3. 🏢 **Andmekeskused**:
   - <span style="color: #4CAF50;">Spetsiaalsed rajatised serverite ja muu riistvara majutamiseks.</span>
   - Sisaldavad jahutussüsteeme, varutoiteallikaid ja turvameetmeid.

4. 🌐 **Võrgud**:
   - LAN (Local Area Network): <span style="color: #FFC107;">Ühendab seadmeid piiratud alal.</span>
   - WAN (Wide Area Network): <span style="color: #2196F3;">Ühendab erinevaid asukohti.</span>
   - Virtuaalsed võrgud: <span style="color: #9C27B0;">Tarkvarapõhised võrgulahendused.</span>

## 1.2 IT-infrastruktuuri võtmekomponendid

1. 🖥️ **Serverid**:
   - <span style="color: #4CAF50;">Võimsad arvutid spetsiifiliste ülesannete täitmiseks.</span>
   - Näide: Veebiserverid, mis majutavad veebilehti.

2. 💾 **Salvestussüsteemid**:
   - Kohalik salvestus: <span style="color: #FFC107;">Individuaalsete seadmete kõvakettad.</span>
   - Võrgusalvestus: <span style="color: #2196F3;">NAS ja SAN süsteemid andmete jagamiseks.</span>

3. 🌐 **Võrguseadmed**:
   - Ruuterid: <span style="color: #9C27B0;">Juhivad andmevoogu seadmete vahel.</span>
   - Kommutaatorid: <span style="color: #FF5722;">Ühendavad seadmeid võrgus.</span>
   - Tulemüürid: <span style="color: #4CAF50;">Kaitsevad võrku ohtude eest.</span>

4. 🔄 **Virtualiseerimine**:
   - <span style="color: #2196F3;">Võimaldab ühel füüsilisel seadmel töötada mitme virtuaalse keskkonnana.</span>

![Väikese kontori IT-seadistuse skeem serverite, võrgu ja pilve varundamisega](/lectures/images/office.webp)
*Väike kontor*

## 1.3 Case Study: IT-infrastruktuur väike- ja keskmise suurusega ettevõtetes (SME-d)

Kujutame ette 50 töötajaga turundusagentuuri:

1. 🖥️ **Riistvara**:
   - Server 1: <span style="color: #FFC107;">Veebisaidi majutamiseks</span>
   - Server 2: <span style="color: #2196F3;">Kliendiandmete salvestamiseks</span>

2. 🌐 **Võrgu seadistus**:
   - LAN ühendab kõiki kontori töötajaid
   - Tulemüür kaitseb sisemist võrku

3. 🔄 **Virtualiseerimine**:
   - Server 1 kasutab virtuaalseid masinaid (VM) erinevate ülesannete jaoks:
     - VM1: <span style="color: #9C27B0;">Veebimajutus</span>
     - VM2: <span style="color: #FF5722;">Andmebaaside haldamine</span>
     - VM3: <span style="color: #4CAF50;">Sisemised tööriistad</span>

4. ☁️ **Pilveteenuste kasutamine**:
   - Andmete varundamine pilves
   - Google Workspace koostöö ja kaugöö jaoks

![Väikese kontori IT-seadistuse skeem serverite, võrgu ja pilve varundamisega](/lectures/images/sme_infra_setup.png)
*Väikese kontori IT-seadistuse skeem serverite, võrgu ja pilve varundamisega*

## 🤔 Arutelu küsimused
1. Kuidas mõjutab virtualiseerimine IT-infrastruktuuri efektiivsust ja kulude kokkuhoidu?
2. Millised on peamised erinevused kohapealsete ja pilvepõhiste IT-lahenduste vahel?
3. Kuidas saaks väike ettevõte optimeerida oma IT-infrastruktuuri, arvestades piiratud ressursse?