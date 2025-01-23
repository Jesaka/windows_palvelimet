# Tehtävä 1: Kuvaile mitä teit harjoituksessa: Virtuaalikoneiden käyttöalusta Hyper-V

## Lähtötilanne 23.1.2025 19:04 
Kuten kuvattu raportissa https://github.com/Jesaka/windows_palvelimet/blob/main/Harjoitus_0.md
Hyper V installation on ajettu ja kone käynnistetty uudelleen. 
Apuna Tehtävän tekemiseen käytin ohjetta 
https://hhmoodle.haaga-helia.fi/mod/resource/view.php?id=3160665

Kun avasin Labin uudelleen Hyper-V Manager aukesi automaattisesti 

<img width="455" alt="image" src="https://github.com/user-attachments/assets/e0a9db6f-18fa-4bfa-b281-36284effe83a" />

Avansin näkymästä WINDOWSLABSSERVI -> Virtual switch manager -> Internal -> Create virtual switch. Jonka jälkeen pääsin kohtaan virtual switch properties. 

<img width="802" alt="image" src="https://github.com/user-attachments/assets/dd290a4a-23b6-435e-8785-acf4b9b28cf7" />

Virtuaalikytkimen nimeksi muutettu HyperVVSwitch ja ohjeen mukaiset asetukset (Ei muutoksia muita kuin nimi) -> OK
Tämän jälkeen tarkistin Network and Sharting Centeristä, että virtuaalinen verkkokortti on asentunut 

<img width="562" alt="image" src="https://github.com/user-attachments/assets/8c24eb4d-bafb-482f-af05-157750363b96" />

Ohjeiden mukainen kuva Powershellistä, komennolla `Get-NetAdapter`

<img width="422" alt="image" src="https://github.com/user-attachments/assets/594274ab-81ca-4c50-bbdd-6279a23bf832" />






