KAUNO TECHNOLOGIJOS UNIVERSITETAS
INFORMATIKOS FAKULTETAS



![image](https://user-images.githubusercontent.com/23249189/209313088-8a1ff165-59d2-45ed-a8ac-19c25b588cc1.png)





Saityno taikomųjų programų projektavimas (T120B165)
Projekto ataskaita
Žaidimų turnyrų sistema



Darbą atliko:
IFF-9/2 gr. Studentas
Vilmantas Pieškus

Darbą priėmė:
doc. prakt. Rasa Mažutienė
doc. prakt. Petras Tamošiūnas



KAUNAS 2022

Turinys
1. Sprendžiamo uždavinio aprašymas	2
1.1. Sistemos paskirtis	2
1.2. Funkciniai reikalavimai	2
2. Pasirinktų technologijų aprašymas	3
3. Sistemos architektūra	4
4. Naudotojo sąsajos projektas	5
5. API specifikacija	10
6. Išvados	12


1. Sprendžiamo uždavinio aprašymas
1.1. Sistemos paskirtis

Projekto tikslas – sukurti žaidimų turnyrų sistemą, kurioje yra galima lengvai sekti žaidimų istoriją ir rungtis, kurios yra žaidžiamos tuo metu. Tai padės sukurti žaidimų eiliškumą be rankinio rašymo.
Veikimo principas – pačią kuriamą platformą sudaro dvi dalys: internetinė aplikacija, kuria naudosis žaidėjai ir administratorius bei aplikacijų programavimo sąsaja (angl. trump. API).
Žaidėjas, prisiregistruos prie internetinės aplikacijos, galės susidaryti savo profilį ir ieškoti bei prisiregistruoti prie turnyrų. Prisiregistravę prie turnyro žaidėjai gali patys įkelti rungties rezultatus ir tada turės teisėjas ar turnyro moderatorius patvirtinti rezultatus. Bet koks žaidėjas gali sukurti turnyrą ir būti to turnyro administratorius. Galima išregistruoti žaidėją, pakeisti turnyrų taisykles ir pradėti/stabdyti turnyrą. Administratorius gali pridėti žaidimus prie žaidimų sąrašo, skirti tam tikras teises žaidėjams ir redaguoti patį puslapį.

1.2. Funkciniai reikalavimai 

Neregistruotas sistemos naudotojas galės: 
1. Peržiūrėti platformos reprezentacinį puslapį; 
2. Prisijungti prie internetinės aplikacijos;
3. Peržiūrėti visus turnyrus;

Registruotas sistemos naudotojas galės:
1. Atsijungti nuo internetinės aplikacijos; 
2. Prisijungti (užsiregistruoti) prie platformos; 
3. Redaguoti profilį:
	3.1. Pasikeisti profilio nuotrauka;
3.2. Atnaujinti informacija apie save;
4. Sukurti turnyrą; 
4.1. Priimti registruotus žaidėjus; 
4.2. Redaguoti turnyro taisykles; 
4.3.Pradėti turnyrą; 
4.4. Stabdyti turnyrą; 
5. Registruotis į turnyrą; 
6. Pateikti turnyro rungties rezultatus; 

Administratorius galės: 
1. Patvirtinti naudotojo registraciją;
2. Patvirtinti turnyro registraciją;
3. Šalinti naudotojus;
4. Šalinti netinkamus algoritmus;

2. Pasirinktų technologijų aprašymas
Kliento pusei (angl. Front-end) bus naudojamas JavaScript React.js karkasas. Serverio pusei – ASP.NET (angl. Back-end). Duombazei bus naudojamas SQL.
3. Sistemos architektūra
 
4. Naudotojo sąsajos projektas
Pradinio lango wireframe ir realizuotas 
 

![image](https://user-images.githubusercontent.com/23249189/209313141-f9cd4360-ab69-402f-a3e8-4a90e0fa6e7a.png)
![image](https://user-images.githubusercontent.com/23249189/209313155-c1f89b83-a18b-4d6e-9fda-ed8deef2156c.png)






Registracijos lango wireframe ir realizuotas:
 
 ![image](https://user-images.githubusercontent.com/23249189/209313182-ec10f600-ec45-4d7e-a79f-2bb173fa68a5.png)
![image](https://user-images.githubusercontent.com/23249189/209313197-d5068a9a-b4c5-4d16-9359-3fbba92b8a58.png)









Turnyro lango wireframe ir realizuotas:
 ![image](https://user-images.githubusercontent.com/23249189/209313236-2f4af827-53f9-47df-a890-b52c702c45af.png)
![image](https://user-images.githubusercontent.com/23249189/209313265-639527c9-363f-4024-b304-cf1e3fafdd50.png)

 
Turnyrų lango wireframe ir realizuotas:  
 
![image](https://user-images.githubusercontent.com/23249189/209313291-c31eac19-b68c-4688-b786-750d860c0314.png)
![image](https://user-images.githubusercontent.com/23249189/209313304-502ade0a-6ee9-45c0-b5b7-6d8fbcde8465.png)








Naudotojų lango wireframe ir realizuotas:
 
 ![image](https://user-images.githubusercontent.com/23249189/209313334-b622dd9a-4e3d-49a0-b804-1c7b1e86c5be.png)
![image](https://user-images.githubusercontent.com/23249189/209313349-3bf0bf95-b89f-4d8e-bfee-8f49218eb3a7.png)








5. API specifikacija

Get Tournaments
Gražina visus turnyrus.

Create Tournament
Sukuria turnyrą.
Kurimo pavyzdys
{
    "name": "authorizationtestxd",
    "description": "The gigaschnozer to decide the winner of the grand prize.",
    "tournamentStartDate": "2023-02-11"
}

Remove Tournament
Ištrina specifinį turnyrą nurodytą pagal id.
Pašalinimo pavyzdys 
http://localhost:5106/api/tournaments/6

Edit Tournament
Redaguoja specifinį turnyrą nurodytą pagal id.
Atnaujinimo pavyzdys
http://localhost:5106/api/tournaments/6
{
    "Description": "Valorant winning team will get deez nuts."
}

Get Games
Gražina visus žaidimus.

Create Game
Sukūria žaidimą.
Kūrimo pavyzdys
{
    "name": "Black Desert Online",
    "description": "MMORPG game made by Pearl Abyss."
}

Remove Game
Ištrina specifinį žaidimą nurodytą pagal id.
Pašalinimo pavyzdys 
http://localhost:5106/api/tournaments/1/games/1

Edit Game
Redaguoja specifinį žaidimą nurodytą pagal id.
Atnaujinimo pavyzdys
http://localhost:5106/api/tournaments/3/games/4

{
    "description": "MMORPG game created by Smilegate. It's very good."
}


Get Users
Gražina visus naudotojus.

Create User
Sukuria naudotoją.
Kūrimo pavyzdys
{
    "nickname": "pvz",
    "profilePicture": "dasfiafd-a213dw2",
    "Age": "-25"
}

Remove User
Ištrina specifinį naudotoją nurodytą pagal id.
Pašalinimo pavyzdys 
http://localhost:5106/api/tournaments/3/games/6/users/10


Edit User
Redaguoja specifinį naudotoją nurodytą pagal id.
Atnaujinimo pavyzdys
http://localhost:5106/api/tournaments/3/games/4

{
    "profilePicture": "684das8d64ad-asd16w"
}

6. Išvados
Modulio metu buvo sukurta dalinai veikianti žaidimų turnyrų sistema skirta žaidėjams. Buvo išmokta kurti API su ASP.NET pagal pristatytą kūrimo specifikaciją, pagilintos žinios su React.js. Išmokta pritaikyti JWT tokenus autorizacijai ir autentifikacijai. Back-end ir front-end galutiniame projekte nebuvo sujungti, todėl daug funkcionalumų neveikė, tačiau išpildyti visi front-end’o reikalavimai. 	
