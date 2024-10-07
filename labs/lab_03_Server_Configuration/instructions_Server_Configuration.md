# Lab 3: Põhiline veebiserveri seadistamine Azure'is

## Eesmärk

Selles laboris õpite seadistama põhilise veebiserveri Azure'i platvormil. Te omandatee praktilisi kogemusi serverite põhikomponentide ja teenuste haldamisest pilves. Labor hõlmab veebiserveri installimist, portide avamist ja lihtsa HTML-lehe lisamist.

## Eeltingimused

- Azure'i konto (soovitavalt Azure for Students)
- Eelmistes laboritest loodud virtuaalmasin
- Baasteadmised käsureast ja HTML-ist

## Ülesanded

### 1. Azure'i konto ja virtuaalmasina ülevaatus

1. Avage veebibrauser ja minge [Azure'i portaali](https://portal.azure.com/).
2. Logige sisse oma Azure'i kontoga.
3. Otsige üles oma eelmises labis loodud virtuaalmasin.
   - Kui te ei leia oma VM-i, kontrollige, kas olete õiges tellimuses (subscription) ja ressursigrupis.

### 2. Ühenduse loomine virtuaalmasinaga

#### 2.1 SSH ühenduse loomine (Linux VM jaoks)

1. Leidke oma VM-i avalik IP-aadress Azure'i portaalist.
2. Avage terminal (Linux/macOS) või PowerShell (Windows).
3. Sisestage järgmine käsk, asendades `<your-username>` ja `<your-vm-ip>` oma andmetega:
   ```
   ssh <your-username>@<your-vm-ip>
   ```
4. Kui küsitakse, sisestage oma SSH-võtme parool (kui see on seadistatud).

#### 2.2 RDP ühenduse loomine (Windows VM jaoks)

RDP (Remote Desktop Protocol) on Microsofti loodud protokoll, mis võimaldab kasutajatel ühenduda teise arvutiga üle võrgu graafilise liidesega.

1. Azure'i portaalis valige oma VM.
2. Klõpsake "Connect" ja valige "RDP".
3. Laadige alla RDP-fail.
4. Avage allalaaditud RDP-fail.
5. Kui küsitakse, sisestage oma VM-i kasutajanimi ja parool.

### 3. Apache veebiserveri installimine

Apache on populaarne avatud lähtekoodiga veebiserver, mida kasutatakse laialdaselt veebilehtede hostimiseks.

1. Pärast VM-iga ühenduse loomist, sisestage järgmised käsud:
   ```bash
   sudo apt update
   sudo apt install apache2 -y
   ```
2. Pärast installimist käivitage Apache ja seadistage see automaatselt käivituma süsteemi käivitamisel:
   ```bash
   sudo systemctl start apache2
   sudo systemctl enable apache2
   ```
3. Kontrollige, kas Apache töötab:
   ```bash
   sudo systemctl status apache2
   ```

### 4. Portide avamine veebiserveri jaoks

**NB! Turvalisus on oluline:** Avage ainult vajalikud pordid ja piirake ligipääsu võimalusel kindlate IP-aadressidega.

1. Minge Azure'i portaalis oma VM-i lehele.
2. Valige vasakmenüüst "Networking".
3. Klõpsake "Add inbound port rule".
4. Lisage järgmised reeglid:
   - HTTP jaoks:
     - Protokoll: TCP
     - Pordi vahemik: 80
     - Tegevus: Allow
     - Prioriteet: 1000
     - Nimi: Allow_HTTP
   - HTTPS jaoks:
     - Protokoll: TCP
     - Pordi vahemik: 443
     - Tegevus: Allow
     - Prioriteet: 1001
     - Nimi: Allow_HTTPS

### 5. Veebiserveri testimine

1. Kopeerige oma VM-i avalik IP-aadress Azure'i portaalist.
2. Avage uus veebibrauseri aken ja sisestage aadressiribale: `http://<your-vm-ip>`
3. Te peaksite nägema Apache2 vaikimisi veebilehte.

### 6. Veebiserveri põhifunktsioonide konfigureerimine

1. Ühenduge uuesti oma VM-iga SSH kaudu.
2. Avage vaikimisi HTML-fail:
   ```bash
   sudo nano /var/www/html/index.html
   ```
3. Kustutage olemasolev sisu ja asendage see järgmise HTML-koodiga (asendage `[SINU TÄISNIMI]` ja `[TÄNANE KUUPÄEV]` oma andmetega):
   ```html
   <html>
   <head>
     <title>Minu Azure Veebileht</title>
     <style>
       body { font-family: Arial, sans-serif; line-height: 1.6; padding: 20px; }
       h1 { color: #0066cc; }
     </style>
   </head>
   <body>
     <h1>Tere tulemast minu Azure veebiserverisse!</h1>
     <p>See leht on hostitud Azure virtuaalmasinas.</p>
     <p><strong>Loodud:</strong> [SINU TÄISNIMI]</p>
     <p><strong>Kuupäev:</strong> [TÄNANE KUUPÄEV]</p>
   </body>
   </html>
   ```
4. Salvestage fail vajutades `Ctrl + X`, seejärel `Y` ja `Enter`.
5. Värskendage veebilehte oma brauseris, et näha muudatusi.

### 7. Tõrkeotsing

Kui teil tekib probleeme, proovige järgmist:

1. Kontrollige Apache staatust:
   ```bash
   sudo systemctl status apache2
   ```
2. Vaadake üle Apache logifailid:
   ```bash
   sudo tail -n 50 /var/log/apache2/error.log
   ```
3. Veenduge, et pordid on avatud Azure'i tulemüüris (vt punkt 4).
4. Kontrollige oma võrguühendust.

### 8. Azure'i ressursi lõpetamine

Kui olete lõpetanud:

1. Minge tagasi Azure'i portaali.
2. Valige oma VM.
3. Klõpsake "Stop" nuppu, et peatada VM (see hoiab kokku kulusid).
   - **NB!** Ärge kustutage VM-i, kui plaanite seda hiljem veel kasutada.

### 9. Ekraanipiltide tegemine ja esitamine

Enne labori lõpetamist tehke kaks ekraanipilti:

1. Teie kohandatud veebilehest brauseris.
2. Azure'i portaalist, mis näitab teie VM-i ülevaadet.

Esitage need kaks ekraanipilti submission vormis, et tõendada labori edukat läbimist.
