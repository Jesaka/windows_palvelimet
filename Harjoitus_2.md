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

Klikkasin luodun koneen aktiiviseksi ja valitsin Settings. Setting valikosta menin kohtaan Processors ja muutin Virtuaaliprosessorien määrän 1 -> 4

<img width="508" alt="image" src="https://github.com/user-attachments/assets/5435dad0-567f-4bf3-aa2f-847a4b3c16f2" />

