# Ohjauspalvelin

## Johdanto

Tässä tehtävässä kuvataan Ohjauspalvelimen asentaminen opettajan antamien ohejeiden mukaan. Raportissa lukee mitä asennuksen aikana on tehty kohta kohdalta. Raportissa kuvataan ongelmien vastaan tullessa mitä niissä tapahtui ja miten ne on ratkaistu Raportin lopuksi käsitellään tiivistelmä mitä olen oppinut. Lopputilanne ei täysin täsmää edellisen raportin https://github.com/Jesaka/windows_palvelimet/blob/main/Harjoitus_2.md tilannetta, koska olin ymmmärtänyt ohjeet väärin ja jouduin tekemään virtuaalisen kovalevyn kopiot ennen tämän tehtävän aloittamista opetuksen aikana.

## TEHTÄVÄ 1: Ohjauspalvelimen rungon määritys 

Tehtävä 1 tehtiin täysin samalla tavalla kun raportissa H2, poikkeuksena kohdassa Connect Virtual Hard Disk valittiin jo tehty virtuaalikiintolevy
WindosServer_DC.vhdx


Seuraavaksi vaihdon ohjauspalvelimen ydinten määrän 1 -> 4 Apply ja ok

<img width="959" alt="image" src="https://github.com/user-attachments/assets/217674c1-4ac8-4254-94d5-2543fdc6820b" />

## TEHTÄVÄ 2: Ohjauspalvelimen määrityksiä 

Käynnistin tehdyn virtuaalikoneen painamalla connect ja start


<img width="860" alt="image" src="https://github.com/user-attachments/assets/04dedc29-bec5-4c15-9ca7-b0da4fcf3ccd" />

Seuraavaksi määritin asetukset, jotka edellisessä kappaleessa tehty sysprep oli pyyhkinyt.


<img width="509" alt="image" src="https://github.com/user-attachments/assets/8a32edd3-6611-4342-9ba5-c701a7d4854b" />

License term: Accept

Tämän jälkeen määritin käyttäjälle Administrator salasann ohjeiden mukaisesti -> Finnish

Kirjauduin sisään Tietokoneeseen äsken asennetuilla tunnuksilla.

##  Ohjauspalvelimen staattisen IP-osoitteen määritys 

Avasin Server mangerista kohdan Ethernet 

<img width="502" alt="image" src="https://github.com/user-attachments/assets/af0dead6-1b58-4810-ae81-9a1fb9e9e4cf" />


Seuraavaksi asetin ohjeidren mukaiset IP ja DNS osoitteet


<img width="199" alt="image" src="https://github.com/user-attachments/assets/3ea78e36-27fe-4a5e-bdc1-e76163442987" />

## Ohjauspalvelimen verkkoyhteyden testaus

Testaaminen suoritettuun CMD:ssä suorittamallakomento `nslookup haaga-helia.fi`


<img width="257" alt="image" src="https://github.com/user-attachments/assets/93bb913f-7af8-4a45-94d1-a9d2bfc452c3" />

Lopputilanteessa asetukset näyttävät tältä 


<img width="506" alt="image" src="https://github.com/user-attachments/assets/76178908-4eee-41f1-9eab-1cb51394250c" />

## Ohjauspalvelimen nimi 

Ohjauspalvelimen nimenmuutos tehtiin Server Manager - Localserver kohdasta Computer name -> klikkaa jolloin aukesi System propertie -> Paina Change ja vaihda computer name, hyväksyin painamalla ok


<img width="505" alt="image" src="https://github.com/user-attachments/assets/4c58a12c-4011-4ee2-b430-cc9634028158" />

Tämän jälkeen hyväksyin tietokoneen ehdottaman uudelleenkäynnistykset

##  Ohjauspalvelimen lukitusruutu pois päältä 

Käynnistetään gpedit.msc

 Local Computer Policy 
 
 Computer Configuration
 
 Administrative Templates
 
 Control Panel
 
 Personalization
 
 Do not display the lock screen

<img width="376" alt="image" src="https://github.com/user-attachments/assets/96b46949-64ad-4417-8529-c0178902114d" />

## Ohjauspalvelimen käyttöjärjestelmän (Windows) aktivointi 

cmd -> Run as administrator ja konento `slmgr.vbs` ok ok ok ok ok ok...


<img width="483" alt="image" src="https://github.com/user-attachments/assets/a7be019f-8200-4562-8339-0a7aa49bf563" />y

Seuraavaksi komento  `slmgr.vbs /dlv` ok

seuraavaksi komento `slmgr /skms kms.core.windows.net`

<img width="479" alt="image" src="https://github.com/user-attachments/assets/45e13cb5-b99a-4436-b5df-9c4ac18b179c" />

suoritetaan aktivointipyyntö komennolla `slmgr/ato`

<img width="479" alt="image" src="https://github.com/user-attachments/assets/edddfc02-93c5-4d60-9862-8ba44231f3a2" />

## TEHTÄVÄ 3: Ohjauspalvelimen palvelinohjelmiston asennus

Valitsin server managerista - Manage -> Add roles and features 

<img width="393" alt="image" src="https://github.com/user-attachments/assets/190bb887-3b59-449b-bce6-a6e3d4ccebfa" />

Before you begin: NEXT 

Installation Type: NEXT

Server Selection: Controller omanimic, NEXT

Server Roles: valitaan active directory domain services -> Include management tools -> add features ja pää ikkunasta NEXT

Features: Oletukset NEXT

AD DS: NEXT

Confirmation: Restart the destination server automatically if required -> Install -> Odotin asentumisen

<img width="391" alt="image" src="https://github.com/user-attachments/assets/6c7a50f7-0683-4808-ba4d-ae9c4e7ef4b4" />

## Asennusvaihe 2 - Domain Controller & DNS: Toimialueen määritys sekä ohjauspalvelin- ja nimipalvelinohjelmistojen asennus 

Hain AD DS valikosta oma kone ja valitaan promote this server....

<img width="509" alt="image" src="https://github.com/user-attachments/assets/ecc40880-66dc-4add-a93b-1a7a7986c2b4" />

Lisäsin kohdan forest 

<img width="379" alt="image" src="https://github.com/user-attachments/assets/8f4b5e8c-0a0d-4868-b94c-cb2a4f1473d9" />

Domain controller Options: oletusasetukset ja ohjeen antama salasana -> NEXT

DNS Options: NEXT

Addutional Options: Odotin niemn ilmestymsitä -> NEXT

Paths: NEXT

Review Options: NEXT

Prerequisities Check: Install

<img width="381" alt="image" src="https://github.com/user-attachments/assets/af70dc17-2182-4a52-a0ca-eff1041a4b49" />

Tietokone käynnityy uudelleen

## TEHTÄVÄ 4: Tutustuminen toimialueelle kirjautumiseen

Dashboardissa näkyy tällä hetkellä asennettuna keskeiset toimialueen ohjauspalvelimen palvelut. 

<img width="353" alt="image" src="https://github.com/user-attachments/assets/c32a4fb4-f84c-482c-80b5-e16ff6796152" />

# Lopuksi

Ohjauspalvelimen asennus tuntui helpolta, ohjeet olivat selkeät eikä asennuksen kanssa tullut uusia ongelmia. Opin käyttämään ohjeessa annettuja kometopäätteen komentoja ja sain kertauksen ip osoitteiden konfiguroinnista. 





















