# Lab 1.3: Põhiserveri seadistamine

**Eesmärk**:  
Selles laboris seadistad ja konfigureerid põhiserveri keskkonna, haldad kasutajaid ja faililubasid, paigaldad veebiserveri, konfigureerid tulemüüri reeglid veebiliikluse lubamiseks ja juurutad lihtsa veebilehe, et kontrollida oma seadistust.

---

**Tööriistad**:  
- Kasuta virtuaalmasinat **Lab 1**-st (VirtualBox) selle labori jaoks.

> **Märkus**: Soovi korral võid kasutada ka pilve virtuaalmasinat **Lab 2**-st (Azure Virtual Machine). Järgi samu juhiseid mõlemas keskkonnas.

---

### Juhised

1. **Linuxi serveri keskkonna seadistamine**:

   #### VirtualBox võrgu seadistamine:
   - Ava VirtualBox ja vali oma virtuaalmasin.
   - Klõpsa **Settings** > **Network**.
   - **Adapter 1** vahekaardil muuda **Attached to** valik **Bridged Adapter**-iks. See võimaldab sinu virtuaalmasinal pääseda otse võrku, muutes selle nähtavaks nagu iga teine seade sinu kohaliku võrgu sees.
   - Vali rippmenüüst **Name** oma host-masina võrguliides (Wi-Fi või Ethernet).
   - Klõpsa **OK**, et muudatused salvestada.

   #### Käivita oma virtuaalmasin:
   - Kui kasutad virtuaalmasinat Lab 1-st, veendu, et sinu **Linuxi server** (nt Ubuntu Server) on töötamas.
   - Pärast käivitamist uuenda pakettide haldurit, et sul oleks saadaval uusim tarkvara:
     ```bash
     sudo apt update
     ```

#### **Kuidas logida sisse VSCode'i või PuTTY kaudu**

> **Märkus**: Kui PuTTY või VSCode ei ole paigaldatud, tuleb need installida enne jätkamist.

##### **Sisselogimine kasutades VSCode'i**:
1. **Paigalda VSCode Remote-SSH laiendus**:
   - Ava VSCode ja mine Extensions vaatesse, klõpsates külgribal asuval Extensions ikoonil.
   - Otsi **Remote - SSH** ja paigalda see.

2. **Leia oma virtuaalmasina IP**:
   - VirtualBoxis käivita oma masinas järgmine käsk:
     ```bash
     ip a
     ```
   - Märgi üles oma virtuaalmasina **IP-aadress** (tavaliselt `eth0` või `enp0s3` all).

3. **Ühendu oma VirtualBoxi masinaga**:
   - Ava VSCode Command Palette (`Ctrl + Shift + P`), trüki `Remote-SSH: Connect to Host...` ja vajuta Enter.
   - Sisesta SSH ühenduse string järgmises vormingus:
     ```bash
     ssh kasutajanimi@virtuaalmasina-ip-aadress
     ```
   - Asenda `kasutajanimi` oma virtuaalmasina kasutajanimega (nt `ubuntu`) ja `virtuaalmasina-ip-aadress` oma masina IP-aadressiga.
   - Nõustu sõrmejälje hoiatusega ja sisesta parool, kui küsitakse. Nüüd peaksid olema ühendatud virtuaalmasinaga VSCode'i kaudu.

##### **Sisselogimine kasutades PuTTYt**:
1. **Paigalda PuTTY** (kui see pole juba installitud):
   - Laadi alla ja paigalda **PuTTY** [ametlikult kodulehelt](https://www.putty.org/).

2. **Leia oma virtuaalmasina IP**:
   - VirtualBoxis käivita oma masinas järgmine käsk:
     ```bash
     ip a
     ```
   - Märgi üles oma virtuaalmasina **IP-aadress** (tavaliselt `eth0` või `enp0s3` all).

3. **Ühendu oma VirtualBoxi masinaga**:
   - Ava **PuTTY**.
   - **Host Name (or IP address)** väljale sisesta oma virtuaalmasina IP-aadress.
   - Veendu, et **Port** on määratud väärtusele `22` ja **Connection type** on **SSH**.
   - Klõpsa **Open**, et alustada ühendust.
   - Sisesta oma kasutajanimi ja parool, kui küsitakse. Nüüd peaksid olema ühendatud virtuaalmasinaga PuTTY kaudu.

---

2. **Uue kasutaja loomine ja faililubade haldamine**:
   - Lisa süsteemi uus kasutaja:
     ```bash
     sudo adduser newuser
     ```
   - Järgi juhiseid, et määrata parool ja luua kasutaja.
   - **Halda faililubasid** uue kasutaja jaoks, luues kausta ja määrates omandiõiguse:
     - Loo kaust `/home` kausta:
       ```bash
       sudo mkdir /home/newuser/newdirectory
       ```
     - Muuda kausta omanikuks uus kasutaja:
       ```bash
       sudo chown newuser:newuser /home/newuser/newdirectory
       ```
     - Sea õiged õigused kaustale:
       ```bash
       sudo chmod 755 /home/newuser/newdirectory
       ```

3. **Paigalda ja konfigureeri veebiserver (Apache)**:
   - Paigalda ja konfigureeri veebiserver **Apache**:
     ```bash
     sudo apt install apache2
     sudo systemctl start apache2
     ```
   - Veendu, et veebiserver töötab, kontrollides selle olekut:
     ```bash
     sudo systemctl status apache2
     ```

4. **Tulemüüri reeglite seadistamine veebiliikluse lubamiseks**:
   - Veendumaks, et veebiliiklus jõuaks sinu serverisse, konfigureeri tulemüür lubama **HTTP** (port 80) ja **HTTPS** (port 443) liiklust:
     - Kasuta **UFW** (Uncomplicated Firewall), et lubada liiklust veebiserverile:
       ```bash
       sudo ufw allow 'Apache'
       ```
   - Luba tulemüür:
     ```bash
     sudo ufw enable
     ```
   - Kinnita, et tulemüüri reeglid on aktiivsed:
     ```bash
     sudo ufw status
     ```

5. **Loo lihtne veebileht**:

   - Nüüd loo lihtne HTML-leht ja teeninda see Apache veebiserveriga:
     - Mine veebiserveri vaikeveebikausta:
       ```bash
       cd /var/www/html
       ```
     - Loo lihtne HTML-fail:
       ```bash
       sudo nano index.html
       ```
     - Lisa järgnev HTML-kood, et luua lihtne ühe leheküljeline veebileht. Kindlasti lisa **oma nimi** sisu sisse:
       ```html
       <!DOCTYPE html>
       <html>
       <head>
         <title>Welcome to My Server</title>
       </head>
       <body>
         <h1>Hello, World!</h1>
         <p>Tere tulemast oma Apache serverisse, mille haldaja on [Sinu Nimi]!</p>
       </body>
       </html>
       ```
     - Asenda `[Sinu Nimi]` oma nimega.
     - Salvesta fail (`Ctrl + X`, seejärel `Y` ja vajuta Enter).

6. **Seadistuse kontrollimine**:

   - Leia oma virtuaalmasina IP-aadress, käivitades järgmise käsu masinas:
     ```bash
     ip a
     ```
   - Otsi IP-aadressi võrguliidese alt, mis on seotud **Bridged Adapter**-iga (tavaliselt `eth0` või `enp0s3`).
   - Ava oma host-masinas veebibrauser ja sisesta virtuaalmasina IP-aadress. Sa peaksid nägema loodud veebilehte, kus kuvatakse sõnum "Hello, World!" ja sinu nimi, mis kinnitab, et sinu Apache server teenindab edukalt sinu veebilehte.

---

Selle labori lõpuks oled seadistanud põhiserveri keskkonna Linuxis, loonud uue kasutaja, paigaldanud veebiserveri, konfigureerinud tulemüüri reeglid, juurutanud lihtsa veebilehe oma nimega ning õppinud, kuidas logida oma virtuaalmasinasse kasutades VSCode'i või PuTTYt.