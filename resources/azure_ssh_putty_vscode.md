# Täielik juhend Azure Linux VM-iga ühendamiseks

## Sisukord
1. Sissejuhatus
2. Eeltingimused
3. SSH võtmete loomine (valikuline, kuid soovitatav)
4. Azure Linux VM-i ettevalmistamine
5. Ühenduse meetodid
   5.1 SSH kasutamine käsureal
   5.2 PuTTY kasutamine Windowsis
   5.3 Visual Studio Code kasutamine
6. Turvalisuse parimad praktikad
7. Veaotsing

## 1. Sissejuhatus

See juhend annab põhjaliku ülevaate erinevatest meetoditest Azure Linux virtuaalmasinaga (VM) ühenduse loomiseks, sealhulgas SSH käsureal, PuTTY ja Visual Studio Code'i kasutamine.

## 2. Eeltingimused

- Azure konto ja loodud Linux VM
- Interneti-ühendus
- VM-i avalik IP-aadress ja kasutajanimi

## 3. SSH võtmete loomine (valikuline, kuid soovitatav)

Linux/macOS:
```
ssh-keygen -t rsa -b 4096
```

Windows (PowerShell):
```
ssh-keygen -t rsa -b 4096
```

## 4. Azure Linux VM-i ettevalmistamine

1. Logige sisse Azure portaali
2. Navigeerige oma VM-i juurde
3. Veenduge, et SSH port (22) on avatud võrguturbe gruppides

## 5. Ühenduse meetodid

### 5.1 SSH kasutamine käsureal

Linux/macOS/Windows (PowerShell):
```
ssh kasutajanimi@avalik_ip_aadress
```

SSH võtmega:
```
ssh -i /tee/võtmeni/id_rsa kasutajanimi@avalik_ip_aadress
```

### 5.2 PuTTY kasutamine Windowsis

1. Käivitage PuTTY
2. Sisestage VM-i IP-aadress "Host Name" väljale
3. Port: 22
4. Connection type: SSH
5. (Valikuline) Laadige SSH võti "Connection > SSH > Auth" all
6. Klõpsake "Open"

### 5.3 Visual Studio Code kasutamine

1. Installige VSCode laiendus "Remote - SSH"
2. Vajutage F1 ja sisestage "Remote-SSH: Connect to Host"
3. Lisage uus host: `ssh kasutajanimi@avalik_ip_aadress`
4. Valige platvorm (Linux)
5. Ühenduge

#### SSH võtmega autentimine VSCode'is:

1. Vajutage F1 ja sisestage "Remote-SSH: Open Configuration File..."
2. Valige konfiguratsioonifail (tavaliselt `~/.ssh/config` Linuxis/macOS-is või `C:\Users\YourUsername\.ssh\config` Windowsis)
3. Lisage või muutke hosti konfiguratsiooni:
   ```
   Host MyAzureVM
       HostName avalik_ip_aadress
       User kasutajanimi
       IdentityFile ~/.ssh/id_rsa
   ```
   Asendage `~/.ssh/id_rsa` oma privaatse võtme täieliku teega.
4. Salvestage fail
5. Nüüd vajutage F1 ja sisestage "Remote-SSH: Connect to Host"
6. Valige oma lisatud host nimekirjast
7. VSCode peaks nüüd ühenduma teie VM-iga, kasutades SSH võtit

Märkus: Kui teie SSH võti on parooliga kaitstud, küsib VSCode seda parooli ühenduse loomisel.

#### Parooliga autentimine VSCode'is:
1. Avage SSH konfiguratsioonifail (samad sammud nagu ülal)
2. Lisage host:
   ```
   Host MyAzureVM
       HostName avalik_ip_aadress
       User kasutajanimi
       PasswordAuthentication yes
   ```

## 6. Turvalisuse parimad praktikad

1. Kasutage SSH võtmeid parooli asemel
2. Hoidke oma süsteem ja tarkvarad uuendatuna
3. Kasutage tugevaid paroole
4. Piirake SSH juurdepääsu kindlatele IP-aadressidele
5. Kaaluge SSH pordi muutmist vaikimisi 22-lt
6. Kasutage kahefaktorilist autentimist, kui võimalik

## 7. Veaotsing

- Kontrollige, kas VM on käivitatud
- Veenduge, et SSH port on avatud
- Kontrollige kasutajanime ja parooli/võtme õigsust
- Vaadake üle Azure võrguturbe grupi seaded
- Kontrollige kohaliku tulemüüri seadeid

SSH logid:
- VM-is: `/var/log/auth.log` või `/var/log/secure`
- Kohalik: Kasutage SSH verbosses režiimis: `ssh -vv ...`

VSCode ja SSH võtmetega seotud probleemid:
- Veenduge, et `IdentityFile` viitab õigele privaatse võtme asukohale
- Kontrollige, et privaatse võtme faili õigused on korrektsed (600 Linuxis/macOS-is)
- Kui kasutate mitut SSH võtit, võite kasutada `ssh-agent`'i võtmete haldamiseks
