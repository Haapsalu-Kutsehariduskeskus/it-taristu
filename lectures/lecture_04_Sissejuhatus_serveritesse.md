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
5. **Domeenikontroller**: Haldab kasutajate autentimist ja ligipääsu võrgule&#8203;:contentReference[oaicite:0]{index=0}.

![Placeholder pilt 1: Serverite rollid](#)

### **Serverite tüübid**

Serverid võib jagada ka füüsilise ja virtuaalse vormi järgi:

1. **Rack serverid**: Need serverid paigaldatakse tihedalt serveriruumidesse riiulitesse. Need pakuvad tõhusat ruumikasutust ja lihtsat haldust.
2. **Blade serverid**: Kompaktsemad serverid, mis võtavad vähem ruumi, kuid pakuvad suuremat töötlemiskiirust ja väiksemat energiatarbimist&#8203;:contentReference[oaicite:1]{index=1}&#8203;:contentReference[oaicite:2]{index=2}.
3. **Virtuaalsed serverid**: Pilves asuvad serverid, mis jooksevad füüsilises riistvaras, kuid mida saab paindlikult hallata, skaleerida ja jaotada ressursse vastavalt vajadusele&#8203;:contentReference[oaicite:3]{index=3}&#8203;:contentReference[oaicite:4]{index=4}.

![Placeholder pilt 2: Erinevad serveritüübid](#)

---

## **Serveri riistvara komponendid**

Iga serveri töökindlus ja võimekus sõltub tema riistvarakomponentidest. Siin on olulisemad komponendid:

1. **Protsessor (CPU)**: See on serveri "aju", mis tegeleb kõikide arvutusülesannetega. Serverites kasutatakse sageli mitmetuumalisi protsessoreid, mis võimaldavad samaaegselt mitut tööprotsessi läbi viia.
2. **Mälu (RAM)**: Ajutine andmesalvestus, mis võimaldab serveril kiiresti ligi pääseda aktiivsetele andmetele ja rakendustele. Suurema töökoormusega serverid vajavad rohkem RAM-i.
3. **Salvestusruum**: Serverid kasutavad plokk- ja failipõhiseid salvestusseadmeid. Kõvakettad (HDD) ja SSD-d tagavad suured salvestusmahud ja kiire andmete ligipääsu.
4. **Võrgukaart (NIC)**: Võimaldab serveril suhelda teiste seadmete ja võrkudega, tagades kiire andmeedastuse.
5. **Jahutussüsteemid**: Kuna serverid töötavad pidevalt, toodavad nad palju soojust, mis vajab tõhusat jahutamist, et vältida ülekuumenemist. Selleks kasutatakse ventilaatorite ja vedelikjahutussüsteeme&#8203;:contentReference[oaicite:5]{index=5}&#8203;:contentReference[oaicite:6]{index=6}.
6. **Toiteallikas**: Tavaliselt on serveritel topeltvõimsusega toiteplokid, et vältida katkestusi elektrikatkestuste ajal.

![Placeholder pilt 3: Serveri riistvara komponendid](#)

---

## **Andmekeskused ja nende komponendid**

Andmekeskused on rajatised, kus serverid ja muud infrastruktuuri elemendid majutatakse. Need võimaldavad keskset ja turvalist ressursside majutamist ning andmete töötlemist ja salvestamist. Siin on mõned andmekeskuste olulisemad komponendid:

1. **Arvutusseadmed (Compute infrastructure)**: Sisaldavad servereid, millel on erinev mälu ja töötlemisvõimsus.
2. **Salvestus (Storage)**: Plokk- ja failisalvestusseadmed, mis tagavad suure andmemahu töötlemise ja salvestamise.
3. **Võrguseadmed**: Lülitid, ruuterid ja tulemüürid tagavad kiire ja turvalise andmete liikumise&#8203;:contentReference[oaicite:7]{index=7}&#8203;:contentReference[oaicite:8]{index=8}.

![Placeholder pilt 4: Andmekeskuse komponentide skeem](#)

Andmekeskuste toetav infrastruktuur sisaldab ka:
- **Varutoitesüsteemid**: UPS-id ja generaatorid.
- **Jahutussüsteemid**: Tõhusad ventilatsioonisüsteemid ülekuumenemise vältimiseks.
- **Füüsiline turvalisus**: Andmekeskustes kasutatakse perimeetrikaitset, kaamerate jälgimist ja ligipääsupiiranguid, et vältida loata juurdepääsu&#8203;:contentReference[oaicite:9]{index=9}.

---

### **Viited**

- [AWS Data Center Explanation](https://aws.amazon.com/what-is/data-center/)&#8203;:contentReference[oaicite:10]{index=10}
- [Spiceworks Windows Server Roles](https://community.spiceworks.com/t/windows-server-roles-understanding-the-basics/970672)&#8203;:contentReference[oaicite:11]{index=11}
