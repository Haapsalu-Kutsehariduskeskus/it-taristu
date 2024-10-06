# Lab 1.2: Pilvekeskkonna seadistamine

**Eesmärk**:  
Selles laboris õpid looma ja uurima virtuaalmasinat Microsoft Azure's. Samuti seadistad põhiveebiserveri **Apache**, et mõista, kuidas pilveinfrastruktuur töötab ja kuidas veebi teenuseid rakendada.

---

**Tööriistad**:  
- **GitHub Education** konto, millel on **Azure for Students** hüved

---

### Juhised

1. **Registreeri Azure kontole läbi GitHub Education**:  
   - Kui sul ei ole veel Azure kontot, mine [GitHub Education hüvede lehele](https://education.github.com/pack) ja registreeru **Azure for Students** pakkumisele.
   - See annab sulle ligipääsu Azure teenustele ilma krediitkaardita, pakkudes tasuta teenuseid, mis on mõeldud spetsiaalselt tudengitele.

2. **Järgi ametlikku Azure virtuaalmasina seadistamise juhendit**:  
   - Alustamiseks järgi seda detailset [Microsoft juhendit](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-portal?tabs=ubuntu), mis õpetab, kuidas luua virtuaalmasinat kasutades **Ubuntu** Azure portaalis.
   - See juhend aitab sul igat sammu läbi teha ja kindlustab, et seadistad oma virtuaalmasina korrektselt.

3. **Virtuaalmasina loomine**:  
   - Pärast juhendi järgimist vali kindlasti tasuta **B1s** suurus.
   - Loo **SSH key pair**, et kindlustada turvaline ligipääs oma virtuaalmasinale.
   - Vaata üle ja loo virtuaalmasin ning oota, kuni selle seadistamine lõpeb.

4. **Ühendu oma virtuaalmasinaga**:  
   - Kui sinu virtuaalmasin on käivitatud, pead sellega ühenduse looma kasutades **SSH**-i.
   - Azure's leia oma virtuaalmasina **Public IP**. Kasuta oma key pair’i, et ühendada SSH kaudu:
     ```bash
     ssh -i /path/to/your-key.pem azureuser@your-vm-public-ip
     ```

5. **Apache veebiserveri paigaldamine**:

   **Mis on Apache?**  
   **Apache** on populaarne, avatud lähtekoodiga veebiserveri tarkvara, mis võimaldab veebisaite teenindada üle interneti. See töötleb päringuid ja edastab veebilehti kasutajatele. Selles laboris installid ja käivitad Apache, et teenindada lihtsat veebilehte.

   - Pärast virtuaalmasinaga ühenduse loomist paigalda **Apache**:
     ```bash
     sudo apt update
     sudo apt install apache2
     ```

   - Pärast veebiserveri paigaldamist käivita teenus:
     ```bash
     sudo systemctl start apache2
     ```

6. **Kontrolli seadistust**:

   **Kuidas kontrollida, kas Apache töötab**:  
   - Sa saad kontrollida, kas Apache töötab, minnes oma virtuaalmasina **Public IP**-le veebibrauseris. Kui Apache töötab õigesti, näed vaikimisi Apache tervituslehte, kus on kirjas midagi sarnast: "Apache2 Ubuntu Default Page."
     - **Public IP** leidmiseks mine Azure portaalis oma virtuaalmasina juurde ja otsi välja **Public IP** väli.
     - Ava oma brauser ja sisesta see IP, näiteks:
       ```
       http://your-vm-public-ip
       ```

   Kui näed vaikimisi lehte, siis töötab sinu **Apache server** edukalt.

---

Selle labori lõpuks oled edukalt loonud virtuaalmasina Azure's, paigaldanud **Apache** ja kontrollinud, kas veebiserver töötab. See annab sulle praktilise kogemuse lihtsa pilvepõhise veebiteenuse seadistamisel.
