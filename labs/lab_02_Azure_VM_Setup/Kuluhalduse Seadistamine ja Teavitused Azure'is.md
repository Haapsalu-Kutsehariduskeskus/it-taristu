# Lab 2: Kuluhalduse Seadistamine ja Teavitused Azure'is

## Eesmärk
Selles laboris õpid, kuidas seadistada **Azure Cost Management + Billing**, et jälgida ressursside kasutamist ja seadistada **teavitused**, mis hoiatavad, kui ressursid jäävad töötama ja põhjustavad eelarve ületamist või tarbetuid kulutusi.

---

## Ülesanded

### 1. Kuluhalduse Ülevaade

1. **Ava Azure'i juhtpaneel** ja mine **Cost Management + Billing** sektsiooni:
   - Otsi Azure'i juhtpaneelis **Cost Management + Billing** ja vali see.
   
2. **Jälgi oma kasutust**:
   - Klõpsa **Cost Management** ja vali **Cost analysis**, et näha reaalajas ülevaadet, kui palju ressursse oled kasutanud ja mis see maksma läheb.
   - Vali **Usage by resource** ja otsi oma ressursse (näiteks virtuaalmasinaid), et näha, kui palju on nende käitamine maksma läinud.

### 2. Eelarve ja Teavituste Seadistamine

#### 2.1 Eelarve Lisamine

1. Mine **Budgets** sektsiooni ja klõpsa **Add**.
2. Vali oma tellimus (**subscription**) ja loo eelarve, mis määrab kindla summa, mida oled valmis kulutama.
3. Määra eelarve nimi, summa ja periood (nt kuus).
4. Salvesta eelarve.

#### 2.2 Teavituste Seadistamine (kui eelarve ületatakse)

1. Eelarvet luues või redigeerides saad seadistada **teavitusi**, mis saadavad automaatselt e-kirju, kui sinu kulutused ületavad määratud protsendi (nt 80%) eelarvest.
2. Klõpsa **Add alert condition** ja määra:
   - **Alert trigger**: vali protsent (nt 80%).
   - **Action group**: loo uus tegevusrühm või vali olemasolev, mis määrab, milline kasutaja või meeskond saab teateid.
   - **Notification type**: vali **Email** ja sisesta e-posti aadress, kuhu teade saadetakse.

3. Salvesta teavitus. Nüüd saad teate, kui sinu kulud lähenevad eelarvele.

### 3. Ressursi Käitamise Teavitus

#### 3.1 Ressursi Jooksuaja Teavitus (näiteks VM-i puhul)

1. Mine **Monitor** sektsiooni ja vali **Alerts**.
2. Klõpsa **New alert rule**, et seadistada uus teavitus.
3. Vali oma ressurss (näiteks virtuaalmasin).
4. Lisa reegel, mis tuvastab ressursi jooksuaja. Otsi **Metric** ja vali **CPU usage** või **VM running**.
5. Määra teavitus:
   - Kui virtuaalmasin töötab teatud aja (nt üle 24 tunni), siis saadetakse teavitus.
6. Vali tegevusrühm (action group), kuhu teavitused saadetakse. Loo uus tegevusrühm, mis saadab e-kirju.

#### 3.2 E-kirjade Saamine (kui unustad masina välja lülitada)

1. Kui masin töötab pikemat aega, saad määratud aja möödumisel automaatselt e-kirja teavituse.
2. Seda reeglit saad kohandada ka teiste ressursside jaoks, näiteks andmebaaside või teiste teenuste puhul.
