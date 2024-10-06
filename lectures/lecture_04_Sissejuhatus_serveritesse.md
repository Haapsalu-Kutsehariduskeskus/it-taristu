# Sissejuhatus serveritesse ja andmekeskustesse

Serverid on IT-süsteemide lahutamatu osa, mis pakuvad arvutusressursse, töötlevad andmeid ja majutavad rakendusi. Ükskõik kas server on füüsiline seade või pilves asuv virtuaalne masin, mängivad nad kriitilist rolli igapäevases IT-töös.

---

## **Serverite rollid ja tüübid**

### **Serverite rollid**

Serverid täidavad erinevaid ülesandeid, sõltuvalt sellest, mida kasutajad ja organisatsioonid vajavad. Siin on mõned peamised rollid:

1. **Failiserver**: Hoiustab ja haldab faile, pakkudes ligipääsu kasutajatele.
2. **Veebiserver**: Majutab veebisaite ja veebirakendusi.
3. **Andmebaasiserver**: Haldab ja säilitab andmebaase, pakkudes andmete päringuid ja töötlemist.
4. **Rakendusserver**: Pakub rakenduste jooksutamise ja majutamise funktsioone, sageli pilves või lokaalsetes keskkondades.
5. **Domeenikontroller**: Haldab kasutajate autentimist ja ligipääsu võrgule.

![Serverite rollid](https://www.zenarmor.com/docs/assets/images/types-of-servers-507a1970e9401e3fc59727d0fd7dde95.png)

*Allikas: [Zenarmor - Types of Servers](https://www.zenarmor.com/docs/assets/images/types-of-servers-507a1970e9401e3fc59727d0fd7dde95.png)*


# Sissejuhatus serveritesse ja andmekeskustesse

### **Serverite tüübid**

Serverid võib jagada ka füüsilise ja virtuaalse vormi järgi:

1. **Rack serverid**: Need serverid paigaldatakse tihedalt serveriruumidesse riiulitesse. Need pakuvad tõhusat ruumikasutust ja lihtsat haldust.
2. **Blade serverid**: Kompaktsemad serverid, mis võtavad vähem ruumi, kuid pakuvad suuremat töötlemiskiirust ja väiksemat energiatarbimist.
3. **Virtuaalsed serverid**: Pilves asuvad serverid, mis jooksevad füüsilises riistvaras, kuid mida saab paindlikult hallata, skaleerida ja jaotada ressursse vastavalt vajadusele.

![Erinevad serveritüübid](https://assets.serverwatch.com/uploads/2021/08/SW.TypesofServerFF.png)

*Allikas: ServerWatch - Types of Servers*

---

## **Serveri riistvara komponendid**

Iga serveri töökindlus ja võimekus sõltub tema riistvarakomponentidest. Siin on olulisemad komponendid:

1. **Protsessor (CPU)**: See on serveri "aju", mis tegeleb kõikide arvutusülesannetega. Serverites kasutatakse sageli mitmetuumalisi protsessoreid, mis võimaldavad samaaegselt mitut tööprotsessi läbi viia.
2. **Mälu (RAM)**: Ajutine andmesalvestus, mis võimaldab serveril kiiresti ligi pääseda aktiivsetele andmetele ja rakendustele. Suurema töökoormusega serverid vajavad rohkem RAM-i.
3. **Salvestusruum**: Serverid kasutavad plokk- ja failipõhiseid salvestusseadmeid. Kõvakettad (HDD) ja SSD-d tagavad suured salvestusmahud ja kiire andmete ligipääsu.
4. **Võrgukaart (NIC)**: Võimaldab serveril suhelda teiste seadmete ja võrkudega, tagades kiire andmeedastuse.
5. **Jahutussüsteemid**: Kuna serverid töötavad pidevalt, toodavad nad palju soojust, mis vajab tõhusat jahutamist, et vältida ülekuumenemist. Selleks kasutatakse ventilaatorite ja vedelikjahutussüsteeme.
6. **Toiteallikas**: Tavaliselt on serveritel topeltvõimsusega toiteplokid, et vältida katkestusi elektrikatkestuste ajal.

![Server Chassis with NVMe SSD Components](https://avinton.com/wp-content/uploads/2021/04/NVME-SSD-Server-Chassis.jpg)  
*Source: [Avinton](https://avinton.com)*

---

## **Andmekeskused ja nende komponendid**

Andmekeskused on rajatised, kus serverid ja muud infrastruktuuri elemendid majutatakse. Need võimaldavad keskset ja turvalist ressursside majutamist ning andmete töötlemist ja salvestamist. Siin on mõned andmekeskuste olulisemad komponendid:

1. **Arvutusseadmed (Compute infrastructure)**: Sisaldavad servereid, millel on erinev mälu ja töötlemisvõimsus.
2. **Salvestus (Storage)**: Plokk- ja failisalvestusseadmed, mis tagavad suure andmemahu töötlemise ja salvestamise.
3. **Võrguseadmed**: Lülitid, ruuterid ja tulemüürid tagavad kiire ja turvalise andmete liikumise.

![Andmekeskuse komponentide skeem](https://cdn.educba.com/academy/wp-content/uploads/2023/11/Data-Centers.jpg.webp)  
*Allikas: [EDUCBA](https://www.educba.com/data-center/)*


Andmekeskuste toetav infrastruktuur sisaldab ka:
- **Varutoitesüsteemid**: UPS-id ja generaatorid.
- **Jahutussüsteemid**: Tõhusad ventilatsioonisüsteemid ülekuumenemise vältimiseks.
- **Füüsiline turvalisus**: Andmekeskustes kasutatakse perimeetrikaitset, kaamerate jälgimist ja ligipääsupiiranguid, et vältida loata juurdepääsu.

---

## [Lab 3: Serveri seadistamine](../labs/lab_03_Server_Configuration/lab_03_Server_Configuration.md)
*See labor hõlmab serveri seadistamist ja põhiliste teenuste konfigureerimist.*

---
### **Viited**

AWS pakub laialdast ülevaadet oma andmekeskustest ja globaalsetest infrastruktuuridest [AWS Data Center Explanation](https://aws.amazon.com/about-aws/global-infrastructure/data-centers/).

Windows Serveri rollide kohta saate lisateavet [Spiceworks Windows Server Roles](https://community.spiceworks.com/windows-server).