Algemeen
===
![Magister 6 Logo](https://martinus.magister.net/Content/app/images/startup-image2.png)

**Voorbeeld live:** 

https://martinus.magister.net/#/inloggen

**API:**
- Gebruikt de Schoolmaster ZEN api (zelfde als mata)
```
https://martinus.magister.net/api/ (magister 6)
https://mata-sgtongerlo.magister.net/api/ (mata - magister 5)
```

- Sessie (heb geen login v/h martinus dus dit is voorlopig het enige dat we hebben...)
```
https://martinus.magister.net/api/sessie

Headers:
POST /api/sessie HTTP/1.1
Host: martinus.magister.net
Connection: keep-alive
Content-Length: 101
Accept: application/json, text/plain, */*
Origin: https://martinus.magister.net
User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/35.0.1916.114 Safari/537.36
Content-Type: application/json;charset=UTF-8
Referer: https://martinus.magister.net/
Accept-Encoding: gzip,deflate,sdch
Accept-Language: nl,en;q=0.8,de;q=0.6,en-GB;q=0.4
Request Payloadview parsed
{"Gebruikersnaam":"test","Wachtwoord":"test","GebruikersnaamOnthouden":false,"IngelogdBlijven":false}
Response Headersview parsed
HTTP/1.1 401 Unauthorized
Cache-Control: max-age=120, private
Content-Length: 76
Content-Type: application/json
Vary: Accept-Encoding,Cookie
X-AspNet-Version: 4.0.30319
Date: Thu, 05 Jun 2014 14:34:06 GMT
X-Frame-Options: DENY
Strict-Transport-Security: max-age=31536000
```
Lijkt allemaal mooi aan te sluiten op MATA dus waarschijnlijk blijft onze code gewoon werken als we de urls aanpassen ;-)

**Opmerkelijke code op pagina:**
- Settings in Javascript
```
<script type="text/javascript">
    var globalSettings = {
        apiHost: 'https://martinus.magister.net/',
        leerlingUrl: '/leerling',
        ouderUrl: '/ouder',
        deviceType: 'desktop'
    };
</script>
```
- Responsive
```
<meta name="application-name" content="Magister 6">
<meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1, maximum-scale=1, user-scalable=no">
<meta name="mobile-web-app-capable" content="yes">
```
- Snelkoppeling Iconen
Respectievelijk Ios/Android 

![](https://martinus.magister.net/content/app/images/apple/apple-touch-icon-152x152.png)![](https://martinus.magister.net/content/app/images/android/drawable-xxhdpi/ic_launcher.png)

**Door beetje te proberen in de JS-console kun je wat functies ontdekken in:**
```
https://martinus.magister.net/bundles/scripts-account-min?v=vgp9QHo949qBHb0ozzf3JoawPlkLZvpHeFwhTVvGZ_k1
```

### LANDELIJKE UITROL IS KLAAR VÓÓR VOLGEND SCHOOLJAAR!

.NET
===
coming by [DutchCodeGeeks](https://github.com/DutchCodeGeeks)

JavaScript
===
coming by [DutchCodeGeeks](https://github.com/DutchCodeGeeks)
