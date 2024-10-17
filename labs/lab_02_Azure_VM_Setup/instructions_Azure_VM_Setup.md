# Lab 2: Pilvekeskkonna seadistamine

🚨 **TEE KULUHALDUSE SEADISTAMISE ENNEM ÄRA!!!** 🚨
⚠️ **KUI SA RAISKAD FREE TRIAL ÄRA !!! SA EI SAA LÕPETADA SEDA KURSUST!** ⚠️


## Eesmärk

Selles laboris õpid looma ja uurima virtuaalmasinat Microsoft Azure's, keskendudes Eesti kontekstile. See annab sulle praktilise kogemuse pilvepõhise infrastruktuuri seadistamisel.

## Tööriistad

- **GitHub Education** konto, millel on **Azure for Students** hüved

## Juhised

### 1. Registreeri Azure kontole läbi GitHub Education

- Kui sul ei ole veel Azure kontot, mine [GitHub Education hüvede lehele](https://education.github.com/pack) ja registreeru **Azure for Students** pakkumisele.
- See annab sulle ligipääsu Azure teenustele ilma krediitkaardita, pakkudes tasuta teenuseid, mis on mõeldud spetsiaalselt tudengitele.

> ![Microsoft Azure pack](/lectures/images/azure_pack.png)
> *https://education.github.com/pack*

### 2. Azure'i portaali sisselogimine ja ressursi loomine

1. Kui su GitHub Student Developer Pack on heaks kiidetud, mine tagasi GitHub Student Developer Pack'i lehele, kerides alla, kuni leiad "Microsoft Azure" sektsiooni. Klõpsa **Get Microsoft Azure** nupul. See suunab sind **Azure for Students** pakkumise lehele.
Logi sisse või loo Azure'i konto:
  -  Kui sul juba on Microsofti konto, logi sisse. Kui ei, siis loo uus konto.
  -  Pärast sisselogimist viiakse sind Azure for Students lehele, kus saad aktiveerida oma $100 tasuta krediidi, ilma et oleks vaja krediitkaarti.
Aktiveeri oma tellimus:
   - Järgi juhiseid, et tõendada oma õpilasstaatust. See võib hõlmata ülikooli e-posti aadressi.
   - Pärast edukat kontrollimist aktiveeritakse sinu tasuta Azure'i tellimus koos $100 krediidiga, mis kehtib 12 kuud, ja saad ligipääsu enam kui 25 tasuta teenusele.
3. Klõpsa "Create a resource" nupul.
4. Vali "Compute" kategooria alt "Virtual Machine".

### 3. Virtuaalmasina konfigureerimine

Kasutame näitena õpilast nimega Maria. Järgi neid samme:

1. **Subscription**: Vali "Azure for Students" tellimus.
2. **Resource group**: Loo uus, nimeta see "RG-Maria-Lab" (asenda "Maria" oma nimega).
3. **Virtual machine name**: Sisesta "VM-Maria-Web" (asenda jälle "Maria" oma nimega).
4. **Region**: Vali "(Europe) North Europe". See on Eestile lähim Azure'i regioon.
5. **Availability options**: Jäta vaikeväärtusele (No infrastructure redundancy required).
6. **Security type**: Vali "Standard".
7. **Image**: Vali Ubuntu Server 20.04 LTS või uusim LTS versioon.
8. **Size**: Vali tasuta "B1s" suurus (1 vCPU, 1 GiB memory).

### 4. Administraatori konto seadistamine

1. **Authentication type**: Vali "SSH public key".
2. **Username**: Sisesta oma eelistatud kasutajanimi, näiteks "mariaadmin".
3. **SSH public key source**: Vali "Generate new key pair".
4. **Key pair name**: Sisesta "Maria-VM-key" (asenda "Maria" oma nimega).

### 5. Sissetulevad pordid

- Vali "Allow selected ports" ja märgi "SSH (22)".

### 6. Diskid

- Jäta vaikesätted.

### 7. Võrgustik

- Virtuaalvõrk ja alamvõrk luuakse automaatselt. Jäta vaikesätted.

### 8. Haldus

- **Azure Security Center**: Lülita "Basic" peale, et säästa ressursse.
- **Boot diagnostics**: Jäta lubatud.
- **Auto-shutdown**: Võid seadistada VM automaatselt välja lülituma öösel, et säästa ressursse.

### 9. Täpsemad sätted

- Jäta vaikesätted.

### 10. Tagid

Tagid aitavad ressursse organiseerida ja hallata. Lisa järgmised tagid:
- Key: "Project", Value: "WebLab"
- Key: "Owner", Value: "Maria" (asenda oma nimega)
- Key: "Environment", Value: "Development"

### 11. Ülevaatus ja loomine

1. Vaata üle kõik seaded.
2. Klõpsa "Create" nupul.
3. Kui küsitakse SSH võtmepaari allalaadimist, laadi see alla ja hoia turvalises kohas.

### 12. Ühenduse loomine virtuaalmasinaga

1. Kui VM on loodud, leia selle avalik IP-aadress Azure'i portaalist.
2. Kasuta SSH-d, et ühenduda:
   ```bash
   ssh -i /path/to/your-key.pem mariaadmin@your-vm-public-ip
   ```
   Asenda "/path/to/your-key.pem" oma allalaaditud võtme asukohaga ja "mariaadmin" oma valitud kasutajanimega.

### 13. Tutvu virtuaalmasina keskkonnaga

- Proovi käske nagu `ls`, `pwd`, `whoami`.
- Uuri süsteemi infot käsuga `uname -a`.

### 14. Virtuaalmasina peatamine

- Logi välja käsuga `exit`.
- Azure'i portaalis vali oma VM ja klõpsa "Stop" nupul.  🚨 **Oluline:** **Peata masin, et mitte kulu raisata!**

## Kokkuvõte

Oled nüüd loonud ja konfigureerinud virtuaalmasina Azure's

## Järgmised sammud

Järgmises laboris õpime, kuidas seadistada veebiserver oma virtuaalmasinas ja hostida lihtsat veebilehte.
