# Labor 3: Veebiserveri seadistamine Azure'is

## 1. Sissejuhatus: Mis on veebiserver?

### 1.1 Veebiserveri põhimõte lihtsas keeles
Kujutage ette, et veebiserver on nagu digitaalne ettekandja:
- **Külastaja (brauser)** küsib midagi (näiteks veebilehte)
- **Veebiserver** toob küsitud info (HTML-faili) külastajale
- **Veebileht** jõuab külastaja brauserisse

### 1.2 Miks me Apache veebiserveri paneme?
- Apache on nagu "programm, mis serveerib veebilehti"
- See on tasuta ja väga populaarne
- Töötab hästi Windowsi ja Linuxi arvutites
- Lihtne seadistada ja kasutada

## 2. Kuidas oma serverisse siseneda?

### 2.1 Sisselogimise võimalused Windowsi VM-ile
Sul on kolm võimalust oma serverisse siseneda:

1. **Läbi Remote Desktop (RDP) - Traditsiooniline meetod**
   - Plussid:
     * Tuttav Windowsi kasutajatele
     * Täisfunktsionaalne töölaud
     * Kiire töötamine
   - Miinused:
     * Vajab programmi installimist
     * Võib olla blokeeritud mõnes võrgus
   
   Kuidas kasutada:
   1. Ava Start menüü
   2. Kirjuta "Remote Desktop Connection"
   3. Sisesta oma VM-i IP-aadress
   4. Sisesta kasutajanimi ja parool

2. **Läbi Azure portaali "Connect" nupu - Lihtne meetod**
   - Plussid:
     * Ei vaja midagi installida
     * Töötab igas arvutis
     * Väga lihtne kasutada
   - Miinused:
     * Vajab head internetiühendust
     * Võib olla aeglasem kui RDP
   
   Kuidas kasutada:
   1. Mine portal.azure.com
   2. Leia oma VM
   3. Vajuta "Connect"
   4. Vali "Native RDP"
   5. Laadi alla RDP fail ja ava see

3. **Läbi brauseri (Bastion) - Modernne meetod**
   - Plussid:
     * Töötab otse brauseris
     * Ei vaja avalikku IP-d
     * Väga turvaline
   - Miinused:
     * Võib olla aeglasem
     * Vajab Bastioni seadistamist
   
   Kuidas kasutada:
   1. Mine Azure portaali
   2. Vali oma VM
   3. Vajuta "Connect"
   4. Vali "Bastion"
   5. Sisesta kasutajanimi/parool

### 2.2 Vali endale sobiv meetod
- Kui oled algaja: Kasuta Azure portaali "Connect" nuppu
- Kui tahad kiiremat ühendust: Kasuta Remote Desktop
- Kui oled koolis/tööl (kus on piirangud): Kasuta Bastioni

## 3. Veebiserveri seadistamine

### 3.1 Apache veebiserveri failisüsteem
Kui Apache on installitud, tekivad järgmised olulised kaustad:

1. **/var/www/html/** - SINU VEEBILEHTEDE KAUST
   - Siia käivad kõik sinu veebilehed
   - index.html on pealeht
   - Pildid ja muud failid võivad olla alamkaustades

2. **/etc/apache2/** - SEADISTUSTE KAUST
   - Siin on Apache seaded
   - Tavaliselt ei pea siin midagi muutma

3. **/var/log/apache2/** - LOGIDE KAUST
   - Siia kirjutatakse kõik, mis serveris toimub
   - Kasulik, kui midagi ei tööta

### 3.2 Kuidas veebileht töötab?
1. Keegi kirjutab brauserisse sinu serveri IP-aadressi
2. Apache saab päringu
3. Apache otsib /var/www/html/ kaustast index.html faili
4. Apache saadab selle faili brauserisse
5. Brauser näitab lehte külastajale

## 4. Apache installimine

### 4.1 Miks me kindlaid käske kasutame?
```bash
sudo apt update
```
- `sudo` - "super-user do" - annab õigused programmi installida
- `apt` - programm, mis oskab teisi programme installida
- `update` - uuenda nimekirja saadaval olevatest programmidest

```bash
sudo apt install apache2
```
- `install` - installi uus programm
- `apache2` - veebiserveri programmi nimi

### 4.2 Pordid ja tulemüür
- **Port 80** - HTTP jaoks (tavalised veebilehed)
  * Nagu ukseava, kust veebilehed läbi käivad
  * Peab olema avatud, et teised saaksid sinu lehte näha

- **Port 443** - HTTPS jaoks (turvalised veebilehed)
  * Sama mis port 80, aga krüpteeritud
  * Vajalik, kui tahad kunagi turvalist ühendust
## 5. Oma veebilehe loomine

### 5.1 HTML - Mis see on ja kuidas töötab?
HTML on nagu ehitusklotsid sinu veebilehe jaoks:
- See on keel, mida brauser mõistab
- Iga `<tag>` ütleb brauserile, mida näidata
- Näiteks:
  * `<h1>` - suur pealkiri
  * `<p>` - tekstilõik
  * `<img>` - pilt

### 5.2 Veebilehe struktuur selgitustega
```html
<html>
    <head>
        <!-- See osa pole nähtav, aga väga oluline -->
        <meta charset="UTF-8">  <!-- Et täpitähed töötaks -->
        <title>Minu leht</title>  <!-- Brauseri sakil nähtav nimi -->
        
        <style>
            /* See osa määrab, kuidas leht välja näeb */
            body {
                font-family: Arial;  /* Teksti font */
                padding: 20px;       /* Vahe lehe äärtest */
            }
        </style>
    </head>

    <body>
        <!-- See osa on nähtav külastajatele -->
        <h1>Pealkiri</h1>
        <p>Tavaline tekst</p>
    </body>
</html>
```

### 5.3 Kuidas veebilehte muuta?

1. **Leia õige fail**
   ```bash
   cd /var/www/html    # Mine veebilehe kausta
   ls                  # Vaata, mis failid seal on
   ```

2. **Muuda faili**
   ```bash
   sudo nano index.html   # Ava teksti redaktor
   ```
   
   Klaviatuuri käsud nano's:
   - `Ctrl + X` - Välju
   - `Y` - Salvesta
   - `Enter` - Kinnita

### 5.4 Proovi ise!
Kopeeri see kood ja muuda [SINU NIMI] enda omaks:

```html
<html>
<head>
    <meta charset="UTF-8">
    <title>Minu Azure leht</title>
    <style>
        /* Siin on lehe disain - võid värve muuta! */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f0f2f5;  /* Helelilla taust */
        }
        .konteiner {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        h1 {
            color: #0066cc;  /* Sinine pealkiri */
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="konteiner">
        <h1>Tere tulemast!</h1>
        
        <!-- Sinu info kast -->
        <div style="border: 1px solid #ddd; padding: 15px; margin: 10px 0; border-radius: 5px;">
            <h2>Minu info:</h2>
            <p><strong>Nimi:</strong> [SINU NIMI]</p>
            <p><strong>Kuupäev:</strong> [TÄNANE KUUPÄEV]</p>
            <p><strong>Kursus:</strong> [KURSUSE NIMI]</p>
        </div>

        <!-- Serveri info kast -->
        <div style="border: 1px solid #ddd; padding: 15px; margin: 10px 0; border-radius: 5px;">
            <h2>Minu serveri info:</h2>
            <ul>
                <li>Operatsioonisüsteem: Windows Server</li>
                <li>Veebiserver: Apache2</li>
                <li>Platvorm: Microsoft Azure</li>
                <li>IP-aadress: [SINU-VM-IP]</li>
            </ul>
        </div>
    </div>
</body>
</html>
```

## 6. Mida teha, kui midagi ei tööta?

### 6.1 Levinud probleemid ja lahendused

1. **"Lehte ei saa avada"**
   - Kontrolli:
     * Kas VM töötab? (Azure portaalis peaks olema "Running")
     * Kas IP-aadress on õige?
     * Kas port 80 on avatud? (Vaata Azure turvalisuse seadeid)

2. **"Permission denied"**
   - Lahendus:
     ```bash
     sudo chmod 755 /var/www/html/index.html
     ```
   - See käsk annab õigused faili muuta

3. **"Täpitähed ei tööta"**
   - Kontrolli, kas failis on rida:
     ```html
     <meta charset="UTF-8">
     ```

### 6.2 Kuidas kontrollida, kas Apache töötab?
```bash
sudo systemctl status apache2
```
- Kui näed "active (running)" - kõik on korras
- Kui näed "failed" - midagi on valesti

## 7. Labori lõpetamine

### 7.1 Kontrollnimekiri
- [ ] VM töötab
- [ ] Apache on installitud
- [ ] Port 80 on avatud
- [ ] Veebileht on muudetud
- [ ] Leht avaneb brauseris

### 7.2 Mida õppisime?
1. Kuidas serverisse siseneda (RDP, Bastion)
2. Mis on veebiserver ja kuidas see töötab
3. Kuidas luua ja muuta veebilehte
4. Kuidas lahendada levinud probleeme

### 7.3 Nõuanded ekraanipiltide tegemiseks
1. **VM ühenduse pilt**
   - Näita tervet RDP või Bastioni akent
   - Veendu, et ühendus on aktiivne

2. **Veebilehe pilt**
   - Näita kogu brauseri akent (peab olema sinu nimi nähtav)
   - IP-aadress peaks olema nähtav aadressiribal

3. **Azure seadete pilt**
   - Näita võrguseadeid, kus port 80 on avatud
   - VM peaks olema "Running" olekus

## 8. Lisa materjalid

- [HTML kiirjuhend (W3Schools)](https://www.w3schools.com/html/)
- [Apache dokumentatsioon](https://httpd.apache.org/docs/)
- [Azure õpikeskus](https://docs.microsoft.com/learn/)
