# 2. Virtuaalikoneiden malli ja palvelinkoneiden alustus 30.1.2025 11:10 

## Lähtötilanne ja johdanto
Tässä raportissa käydään läpi tehtävä 2 Virtaalikoneen luominen HyperV ympäristöön. Lähtötilanne on tehtävän 1 lopputilanne
https://github.com/Jesaka/windows_palvelimet/blob/main/harjoitus_1.md


## Virtuaalikoneen luominen
Aloitin avaamalla HyperV Managerin ja luomalla uuden koneen painamalla New -> Virtual machine

<img width="530" alt="image" src="https://github.com/user-attachments/assets/b9614889-113d-4d08-b2f2-b9e9962b5591" />

Asetin tietokoneeseen seuraavat asetuksen ohjeiden mukaan:
chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://hhmoodle.haaga-helia.fi/pluginfile.php/4144251/mod_resource/content/13/2_Virtuaalikoneiden_malli_palvelinkoneiden_alustus_V3.1.pdf
Before you begin: Ei muutoksia painetaan suoraan Next 
Specify Name and Location: WindowsServerTemplate ja tallennus ehdotettuun polkuun -> Next
Specify Generation: Generation 1 oli ohjeiden mukaan riittävä kurssille, valitsin sen -> Next
Assign Memory: Muistin määrä 3072 ja raksi kohtaan Use Dynamic Memory... -> Next
Configure Networking: Valitaan aikaisemmin luotu HyperVVSwitch -> Next 
Connect Virtual Hard Disk: Laitoin täpän kohtaan Create a virtual hard disk, muutetaan koko 30GB ja muuten standardiasetukset -> Next
Installation Options: Valitaan Install an operating system froma a bootable CD/DVD-ROM ja valitaan Image fileksi itse ohjeiden mukainen media työpöydältä -> Next

Yhteenveto asetuksista ennen Finish painamista:

<img width="524" alt="image" src="https://github.com/user-attachments/assets/7e965491-c92a-4a4e-905e-a798d0bcf60d" />

Uusi Kone näkyi kohdassa Virtual Machines 

<img width="211" alt="image" src="https://github.com/user-attachments/assets/fb83139a-60e2-42d2-88c1-d0c453f0ac6c" />

### Prosessiytimien säätäminen

Klikkasin luodun koneen aktiiviseksi ja valitsin Settings. Setting valikosta menin kohtaan Processors ja muutin Virtuaaliprosessorien määrän 1 -> 4 -> Apply -> Ok

<img width="508" alt="image" src="https://github.com/user-attachments/assets/5435dad0-567f-4bf3-aa2f-847a4b3c16f2" />

## Windows asentaminen

Aloitin käynnistämnällä tässä Raportissa kuvatun virtuaalitietokoneen

Tietokoneen ruutu alkoi pomppia ja vaihdella kokoa, korjasin tialnteen valitsemalla view -> Zoom level 100% 

### Asetukset
Kieli: Engalnti US Aikavyöhyke: Finland Keyboard: Finland -> Next

Aloitin asennuksen painamalla Install now 

Hyväksyin lisenssit, täppä ruutuun -> Next 

Valitaan Custom Install Windows only (adcanced) 

Jatkoin seuraavasta kohdasta next painikkeella, koska levytilan allokointi ei ollut pakollista 

Odotin Windowsin asentumista asennus aloitettu 11:43 

<img width="435" alt="image" src="https://github.com/user-attachments/assets/640987b9-fb5f-45c8-be1c-ee028adb8296" />

Asennus oli päättynyt 11:56 

Tämän jälkeen käynnistin koneen uudelleen. Kun Windows käynnistyslogo tuli ruudulle painoin media, DVD Drive ja Eject SW..... (Oletan ettei kone lähde asentamaan käyttöjärjestelmää uudelleen)

<img width="497" alt="image" src="https://github.com/user-attachments/assets/5e15a546-da05-4343-8634-9b631fe10327" />

Lopuksi asetin salasanat ohjeiden määrittämiin asetuksiin.

<img width="428" alt="image" src="https://github.com/user-attachments/assets/13b99f16-5f22-4df0-ac95-19c3140d4a35" />

Lopuksi vielä painoin action valikosta ctrl alt del ja testasin että käyttäjä toimii 

<img width="505" alt="image" src="https://github.com/user-attachments/assets/25d31368-9898-43a4-a0ed-4648c386e700" />

Asennuksen jälkeen käytin hetken tutustuessani Server manageriin,

Raportti päättyy 30.1.2025 11:58 




