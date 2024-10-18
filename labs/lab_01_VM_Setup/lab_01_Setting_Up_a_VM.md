# Lab 1.1: Virtuaalmasina seadistamine

**Eesmärk**:  
Selle labori eesmärk on saada praktiline kogemus virtualiseerimise tehnoloogiaga, luues nullist virtuaalmasin (VM). Paigaldad ja seadistad Alma Linux operatsioonisüsteemi virtuaalmasinasse, teed lihtsaid ülesandeid virtuaalkeskkonnas ja uurid selle konfiguratsiooni.

**Tööriistad**:  
Selle labori jaoks kasutad **VirtualBoxi**. Programm on juba installitud ja valmis kasutamiseks.

---

## Samm-sammuline juhend

### 1. Loo uus virtuaalmasin
   - **Eesmärk**: Selle sammuga lood virtuaalmasina ja määrad sellele ressursse nagu mälu ja kettaruum.
   - **Juhised**:
     1. Käivita oma arvutis **VirtualBox**.
     2. Klõpsa **New** nuppu VirtualBoxi halduris.
     3. **Nimi ja operatsioonisüsteem** aknas tee järgmist:
        - **Nimi**: vali mistahes nimi (nt "Minu_Alma_Server").
        - **Tüüp**: vali rippmenüüst **Linux**.
        - **Versioon**: vali **Red Hat (64-bit)**, kuna Alma Linux põhineb Red Hat Enterprisel.
     4. Klõpsa **Next**.
     5. **Määra mälu (RAM)**:
        - Pead määrama oma virtuaalmasina jaoks kasutatava mälu. Soovitatav miinimum on **2 GB** (2048 MB), kuid kui sul on rohkem ressursse, saad määrata rohkem, et tagada parem jõudlus.
        - Lohista liugurit või kirjuta "2048 MB" mälu jaotamiseks.
     6. **Loo virtuaalne kõvaketas**:
        - Vali "Create a virtual hard disk now" ja klõpsa **Create**.
     7. **Virtuaalse kõvaketta tüüp**:
        - Vali **VDI (VirtualBox Disk Image)** kui kõvaketta failitüüp ja klõpsa **Next**.
     8. **Füüsilisel kõvakettal salvestamise meetod**:
        - Vali **Dynamically allocated**, et virtuaalmasina kõvaketas suureneks vastavalt vajadusele (see ei hõiva kohe kogu määratud ruumi).
     9. **Määra kettaruum**:
        - Määra virtuaalse kõvaketta suuruseks **10-20 GB**. Lihtsaks kasutuseks piisab 10 GB-st, aga kui plaanid paigaldada lisatarkvara, vali 20 GB.
     10. Klõpsa **Create**, et lõpetada.

### 2. Laadi alla ja paigalda Alma Linux virtuaalmasinasse
   - **Eesmärk**: Selle sammuga paigaldad operatsioonisüsteemi (OS) virtuaalmasinasse.
   - **Juhised**:
     1. Külasta Alma Linux veebilehte (https://almalinux.org/get-almalinux/) ja laadi alla uusim **Alma Linux ISO** fail. Seda faili kasutatakse operatsioonisüsteemi paigaldamiseks virtuaalmasinasse.
     2. Mine tagasi VirtualBoxi ja klõpsa oma äsja loodud virtuaalmasinal.
     3. Klõpsa **Settings** ja ava **Storage** sakk.
     4. **Controller: IDE** all klõpsa **Empty** CD/DVD ikoonil ja siis väiksel CD ikoonil selle kõrval. Vali **"Choose a disk file..."** ja otsi üles varem alla laaditud Alma Linux ISO fail.
     5. Klõpsa **OK**, et sulgeda seadistuste aken.
     6. Käivita virtuaalmasin, klõpsates **Start**.
     7. Järgi ekraanil kuvatavaid juhiseid Alma Linuxi paigaldamiseks:
        - Vali oma eelistatud keel.
        - Vali **Install Alma Linux**.
        - Paigalduse ajal määrad **kasutajanime**, **parooli** ja seadistad võrguühenduse, kui küsitakse. 
        - Graafilist kasutajaliidest (GUI) pole vaja, sest tegemist on serverikeskkonnaga.
     8. Kui paigaldus on lõpule jõudnud, eemalda ISO fail, minnes tagasi **Settings** → **Storage** ja klõpsa **Empty** CD/DVD ikoonil, et eemaldada Alma Linux ISO.
     9. Taaskäivita virtuaalmasin, kui küsitakse.

### 3. Uuri virtuaalkeskkonda
   - **Eesmärk**: Pärast edukat Alma Linuxi paigaldust logi sisse ja uuri virtuaalmasina käsurea keskkonda, tehes lihtsaid ülesandeid.
   - **Juhised**:
     1. Pärast taaskäivitust peaksid nägema sisselogimisekraani. Logi sisse, kasutades paigalduse ajal määratud kasutajanime ja parooli.
     2. Teosta järgmised ülesanded:

   **Ülesanne 1: Loo kataloog**
   - **Käsk**: `mkdir my_first_vm`
   - **Selgitus**: Käsk `mkdir` luuakse uus kataloog (kaust) praeguses töökaustas. Siin lood kausta nimega "my_first_vm".

   **Ülesanne 2: Loo uus kasutaja**
   - **Käsk**: `sudo useradd newuser && sudo passwd newuser`
   - **Selgitus**: Käsk `useradd` lisab süsteemi uue kasutaja ja `passwd` võimaldab määrata parooli. Kui lisad käsule `sudo`, saad haldusõigused, mis võimaldavad luua uue kasutajakonto administraatori õigustega. Sul palutakse määrata parool uuele kasutajale.

   **Ülesanne 3: Testi internetiühendust**
   - **Käsk**: `ping google.com`
   - **Selgitus**: Käsk `ping` kasutatakse võrguühenduse testimiseks. Siin kontrollid, kas su virtuaalmasin pääseb internetti, saates pakette Google'i serveritesse. Kui võrk töötab, näed serveri vastuseid. Kasuta `Ctrl + C`, et ping peatada mõne sekundi pärast.

   **Ülesanne 4: Vaata süsteemiinfot**
   - **Käsud**:
     1. `top` – Näitab süsteemi protsesside ja ressursside kasutust reaalajas, näiteks protsessori ja mälu kasutust.
     2. `df -h` – Kuvab kõigi ühendatud failisüsteemide kettakasutuse inimloetavas vormingus.
   - **Selgitus**: Need käsud aitavad jälgida süsteemi jõudlust ja vaadata kettakasutust. Oluline on teada, kuidas sinu virtuaalmasin ressursse kasutab, et seda edaspidi hooldada.

---

### Täiendav ressurss
Kui vajate veelgi detailsemat juhendit Alma Linuxi paigaldamise kohta VirtualBoxi kasutades, vaadake Alma Linuxi ametlikku dokumentatsiooni või otsige spetsiifilisi juhendeid veebist.
