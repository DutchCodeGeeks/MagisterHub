#Magister 6 Api documentatie 

##Login
Alle url's die in deze documentatie staan moeten achter onderstaande link geplakt worden:
`https://{schoolnaam}.magister.net/api`

Allereerst moeten we een sessie aanmaken met magister zodat we met de Magister-api kunnen communiceren.
Dit doen we als volgt:
```
url:		/sessie
Method: 	POST
Params: 	Gebruikersnaam={username}
			Wachtwoord={wachtwoord}
Optional:	IngelogdBlijven={boolean}
```

###Voorbeeld  
Als we dit zouden doen via curl doen zou dat er als volgt uit zien:
```
curl -X POST --cookie-jar ./somefile  -d "Gebruikersnaam={username}&Wachtwoord={wachtwoord}" https://{school}.magister.net/api/sessie
```

Als we hiermee dan data van de Magister-Api zouden willen opvragen dan doen wij dit als volgt:
```
curl --cookie ./somefile https://{school}.magister.net/api/account
```

##Data
Nu we een sessie met Magister hebben kunnen we gebruik maken van hun Api.
Hieronder kun je zien hoe en wat voor items je kunt opvragen met behulp van de api.

###Account
Hier misschien wel het belangrijkste onderdeel. De persoonid opvragen.
```
url:		/account
Method: 	GET
Params: 	Geen
```
In de response zie je als het goed is een JSONObject genaamd "Persoon".
Hierin zul je de "Id"(persoonId) vinden en die hebben we later in deze documentatie nodig om andere data op te vragen.

###Agenda
```
url:		/personen/{persoonid}/afspraken
Method: 	GET
Params: 	van={datumVanaf},
			tot={datumTot}
```
Bijvoorbeeld: `https://{schoolnaam}.magister.net/api/personen/4216/afspraken?van=2015-03-17&tot=2015-03-24`

###Cijfers
TODO.

###Absentie
Net zoals bij cijfers zijn er voor de absentie eigenlijk 2 onderdelen.
Het overzicht waarin je je jaar selecteert en de absentie's zelf.
```
url:		/personen/{persoonid}/absentieperioden
Method: 	GET
Params: 	Geen
```

Met de JSONTags "Start" en "Einde" kun je weer de absentie's zelf ophalen (je moet ze natuurlijk alleen nog wel even formatten :wink:). 
```
url:		/personen/{persoonid}/absenties
Method: 	GET
Params: 	van={datumVanaf},
			tot={datumTot}
```
Bijvoorbeeld: `https://{schoolnaam}.magister.net/api/personen/4216/absenties?van=2015-03-17&tot=2015-03-24`

###Opdrachten
TODO.

###Dashboard
Recent behaalde cijfers:
```
url:		/personen/{persoonid}/aanmeldingen/{cijferperiodenId}/cijfers
Method: 	GET
Params: 	Geen
```

Recente roosterwijzigingen:
```
url:		/personen/{persoonid}/roosterwijzigingen
Method: 	GET
Params: 	van={datumVanaf},
			tot={datumTot}
```

Opdrachten: 
TODO.


##Items toevoegen aan de documentatie
Wil jij zelf ook wat toevoegen aan onze documentatie? Dan kan dat natuurlijk!
Om dit te doen moet je de volgende stappen volgen.
1. Fork deze repo.
2. Commit jouw wijziging naar de geforkte repo.
3. Maak een pull request!

Heb je een nieuwe link gevonden of wil je iets aanpassen, 
gebruik dan het volgende schema daarvoor:
```
url:		/link/to/path
Method: 	GET, POST, DELETE, etc.
Params: 	foo=bar
Optional: 	foox=bar
```