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
Hieronder kun je hoe en wat voor items je kunt opvragen.

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
Params: 	van={datumVanaf}
			tot={datumTot}
```
Bijvoorbeeld: `https://{schoolnaam}.magister.net/api/personen/4216/afspraken?van=2015-03-17&tot=2015-03-24`

###Cijfers
-

###Absentie
```
url:		/personen/{persoonid}/absenties
Method: 	GET
Params: 	van={datumVanaf}
			tot={datumTot}
```
Bijvoorbeeld: `https://{schoolnaam}.magister.net/api/personen/4216/absenties?van=2015-03-17&tot=2015-03-24`