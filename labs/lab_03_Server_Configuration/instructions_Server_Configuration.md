# Lab 3: Põhiline veebiserveri seadistamine Azure'is

## Eesmärk
Õpilased seadistavad Azure'i platvormil põhiveebiserveri, õppides samal ajal serverite põhikomponentide ja teenuste haldamist pilves.

## Ülesanded

### 1. Azure'i konto loomine ja sisse logimine
- Juhenda õpilasi, kuidas registreerida ja logida sisse Azure'i konto (kui neil veel pole).
- **Placeholder pilt 1**: Azure'i konto loomine.

### 2. Uue virtuaalmasina loomine
- Azure'i juhtpaneelilt vali **Create a resource** > **Virtual Machine**.
- Juhenda õpilasi, kuidas valida sobiv suurus ja OS (näiteks Ubuntu või Windows Server).
- **Placeholder pilt 2**: Virtuaalmasina loomise protsess Azure'is.

### 3. Veebiserveri tarkvara installimine
- Pärast virtuaalmasina loomist logi SSH (Linuxi VM puhul) või RDP (Windows Server puhul) kaudu sisse.
- Installi veebiserveritarkvara:
  - **Linux**: 
    ```bash
    sudo apt update && sudo apt install apache2 -y
    ```
  - **Windows**: IIS-i seadistamine serveri halduri kaudu.
- **Placeholder pilt 3**: SSH või RDP ühenduse loomine.

### 4. Portide avamine veebiserveri jaoks
- Azure'i juhtpaneelilt lisa turvareeglitesse reegel, mis avab HTTP liikluse jaoks pordi 80 ja HTTPS liikluse jaoks pordi 443.
- **Placeholder pilt 4**: Turvareeglite seadistamine portide avamiseks.

### 5. Veebiserveri testimine
- Leia virtuaalmasina IP-aadress ja ava see brauseris. Kontrolli, kas veebileht kuvatakse (näiteks Apache'i vaikimisi tervitusleht).
- **Placeholder pilt 5**: Veebilehe kuvamine brauseris.

### 6. Veebiserveri põhifunktsioonide konfigureerimine
- Juhenda, kuidas muuta veebiserveri vaikimisi lehte ja lisada lihtsaid HTML-failide näiteid.
- **Placeholder pilt 6**: Veebilehe kohandamine ja HTML-failide lisamine.

### 7. Azure'i ressursi lõpetamine (või peatamine)
- Selgita, kuidas õpilased saavad pärast lab'i lõpetamist Azure’i virtuaalmasina peatada või kustutada, et vältida tasulisi jooksvaid ressursikulusid.
- **Placeholder pilt 7**: Ressursi lõpetamine või peatamine Azure'is.

