# 🖥️ Sissejuhatus Serveritesse ja Andmekeskustesse

Selles loengus õpime tundma serverite ja andmekeskuste põhialuseid. Server ei ole lihtsalt võimas arvuti - see on spetsiaalselt disainitud süsteem, mis on mõeldud teenuste pakkumiseks teistele seadmetele ja kasutajatele.

## 🤖 Serverite Rollid ja Tüübid

Serverid täidavad mitmeid kriitilisi funktsioone IT-ökosüsteemis. Igal serveritüübil on oma spetsiifiline ülesanne:

1. 📁 **Failiserver**: <span style="color: #FFC107;">Tsentraliseeritud failihaldus ja -jagamine</span>
   - Toimib kui keskne failihoidla
   - Võimaldab failide jagamist ja varundamist
   - Näide: Ettevõtte ühine dokumendihoidla

2. 🌐 **Veebiserver**: <span style="color: #2196F3;">Veebisaitide ja -rakenduste majutamine</span>
   - Serveerib veebilehti kasutajatele
   - Töötleb HTTP päringuid
   - Populaarsed tarkvarad: Apache, Nginx, IIS

3. 🗄️ **Andmebaasiserver**: <span style="color: #9C27B0;">Struktureeritud andmete haldamine</span>
   - Säilitab ja haldab andmeid
   - Võimaldab kiiret andmete otsimist
   - Näited: MySQL, PostgreSQL, Oracle

4. 🚀 **Rakendusserver**: <span style="color: #FF5722;">Äriloogika ja rakenduste käitamine</span>
   - Jooksutab ettevõtte rakendusi
   - Töötleb äriloogikat
   - Näited: Tomcat, JBoss

5. 🔐 **Domeenikontroller**: <span style="color: #607D8B;">Võrgu autentimine ja õiguste haldus</span>
   - Haldab kasutajaõigusi
   - Kontrollib ligipääsu ressurssidele
   - Tavaliselt Windows Server keskkonnas

![Serverite rollid](https://www.zenarmor.com/docs/assets/images/types-of-servers-507a1970e9401e3fc59727d0fd7dde95.png)

*Allikas: [Zenarmor - Types of Servers](https://www.zenarmor.com/docs/assets/images/types-of-servers-507a1970e9401e3fc59727d0fd7dde95.png)*

### Serverite Füüsilised Vormid:

Servereid toodetakse erinevates füüsilistes vormides, sõltuvalt kasutuskohast ja -vajadusest:

1. **Rack serverid**: 
   - Standardsesse 19-tollisesse raami paigaldatavad seadmed
   - Ideaalsed andmekeskustesse
   - Lihtne hooldada ja vahetada

2. **Blade serverid**: 
   - Kõrge tihedusega, energiatõhusad seadmed ühises šassiis
   - Sobivad suurte andmekeskuste jaoks
   - Jagavad toite- ja jahutussüsteeme

3. **Tower serverid**: 
   - Vertikaalsed, iseseisvad seadmed väiksematele kontorikeskkondadele
   - Sarnased tavaliste lauaarvutitega
   - Lihtne seadistada ja hallata

![Erinevad serveritüübid](https://assets.serverwatch.com/uploads/2021/08/SW.TypesofServerFF.png)

*Allikas: ServerWatch - Types of Servers*

## 🧠 Serveri Riistvara Komponendid

Serveri riistvara erineb oluliselt tavalise arvuti omast. Peamised erinevused on:

1. **Protsessor (CPU)**: <span style="color: #FF9800;">Serveri arvutusjõud</span>
   - Mitme protsessori tugi
   - ECC mälu tugi
   - Optimeeritud 24/7 töötamiseks

2. **Mälu (RAM)**: <span style="color: #03A9F4;">Kiire ajutine andmesalvestus</span>
   - ECC (Error Correcting Code) mälu
   - Suurem maht kui tavaarvutitel
   - Kiirem ja töökindlam

3. **Salvestusruum**: <span style="color: #4CAF50;">Püsiv andmesalvestus</span>
   - Hot-swap ketaste tugi
   - RAID-süsteemid
   - SSD ja HDD kombinatsioonid

4. **Võrgukaart (NIC)**: <span style="color: #9C27B0;">Võrguühenduvus</span>
   - Mitu võrgukaarti
   - 10Gb/s või kiirem ühendus
   - Toetab võrgu teekide jagamist

5. **Jahutussüsteemid**: <span style="color: #00BCD4;">Temperatuuri reguleerimine</span>
   - Redundantsed ventilaatorid
   - Temperatuuri monitooring
   - Automaatne kiiruse reguleerimine

6. **Toiteallikas**: <span style="color: #FFC107;">Usaldusväärne energiavarustus</span>
   - Redundantsed toiteplokid
   - Hot-swap võimalus
   - Kõrge efektiivsus

![Server Chassis with NVMe SSD Components](https://avinton.com/wp-content/uploads/2021/04/NVME-SSD-Server-Chassis.jpg)  
*Allikas: [Avinton](https://avinton.com)*

## 🏙️ Andmekeskused: IT-Infrastruktuuri Tuumik

Andmekeskus on spetsiaalselt ehitatud hoone või ruum, mis majutab servereid ja nende tugiinfrastruktuuri. Andmekeskused koosnevad mitmest kriitilisest komponendist:

1. **Arvutusinfrastruktuur**: <span style="color: #2196F3;">Serverid ja nende klastrid</span>
   - Serverite riistvara
   - Virtualiseerimisplatvormid
   - Arvutusvõimsuse haldus

2. **Salvestusinfrastruktuur**: <span style="color: #FF5722;">Andmete hoiustamine ja haldamine</span>
   - SAN (Storage Area Network)
   - NAS (Network Attached Storage)
   - Varundussüsteemid

3. **Võrguinfrastruktuur**: <span style="color: #9C27B0;">Kiire ja usaldusväärne ühenduvus</span>
   - Kiudoptilised ühendused
   - Võrguseadmed (switchid, ruuterid)
   - Võrgu turvalisus

![Andmekeskuse komponentide skeem](https://cdn.educba.com/academy/wp-content/uploads/2023/11/Data-Centers.jpg.webp)  
*Allikas: [EDUCBA](https://www.educba.com/data-center/)*

### Andmekeskuse Toetav Infrastruktuur:

Andmekeskuse töökindluse tagamiseks on vajalik:

- **Varutoitesüsteemid**: 
  - UPS-id katkematu töö tagamiseks
  - Diiselgeneraatorid pikemateks elektrikatkestusteks
  - Automaatne ümberlülitus

- **Jahutussüsteemid**: 
  - Täppisjahutus optimaalse temperatuuri hoidmiseks
  - Kuumade/külmade koridoride haldus energia säästmiseks
  - Õhuniiskuse kontroll

- **Füüsiline turvalisus**: 
  - Biomeetriline juurdepääsukontroll
  - 24/7 videovalve
  - Tulekustutussüsteemid

## 🎓 Kokkuvõte

Serverid ja andmekeskused moodustavad kaasaegse IT-infrastruktuuri selgroo, võimaldades usaldusväärseid, skaleeritavaid ja turvalisi teenuseid. Nende efektiivne haldamine nõuab sügavaid teadmisi nii riistvarast kui ka tarkvarast ning pidevat kohanemist uute tehnoloogiatega.

**Arutelu küsimus:** Kuidas mõjutab edge computing traditsiooniliste andmekeskuste rolli ja milliseid uusi väljakutseid see tekitab IT-infrastruktuuri haldamisel?

## Lisalugemist

- [AWS Data Center Explanation](https://aws.amazon.com/what-is/data-center/#seo-faq-pairs#what-is-a-data-center)
- [Windows Server Roles](https://openclassrooms.com/en/courses/7710301-manage-windows-server/7803261-understand-roles-and-features)

## [Lab 3: Serveri seadistamine](../labs/lab_03_Server_Configuration/lab_03_Server_Configuration.md)
*See labor hõlmab serveri seadistamist ja põhiliste teenuste konfigureerimist.*
