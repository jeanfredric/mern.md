# Teknikutvärderingsrapport

Detta dokument är framplockat av två studenter vid Umeå Universitet som läser kursen Applikationsutveckling för Internet. Syftet med dokumentet är att ge en inblickande guide till hur utvekclingsstacken MERN är uppbyggd samt hur man går till väga för att skapa ett nytt projekt.

## Överblick

Dokumentet är uppdelat i olika sektioner för att ge en bättre förståelse för hur de olika delarna är uppbydda samt vart koden exekveras. Vi väljer att titta på stacken från "front-end" sidan och arbetar oss sedan igenom stacken för att sedan avsluta med att förklara hur databasen är uppbyggd. 

**Men vad är då MERN, och varför används denna "stack"?**

Det som är bra med den här stacken är att man genomgående endast använder JavaScript och JSON. Denna stack består av fyra av fyra teknologier som gör det möjligt att designa och utveckla webbapplikationer på ett snabbt och smidigt vis. 

MERN stacken är uppbydds av följande komponenter:
Verktyg | Beskrivning
:--- | :---
**M**ongoDB | Databas
**E**xpress | Ramverk som underlättar Node.js
**R**eact   | View
**N**ode.js | Controller & Model

För att få en bättre överblick vilka program som exekverar vart kan vi titta på nedstående bild. 

På klientsidan av programmet (view) arbetar **R**eact. Denna del står för all UI som användaren möts av.

På seversidan arbetar resterande program. **N**ode.js och **N**ode package manager (npm) är en open source plattform som exekverar på serversidan. Node.js gör det möjligt att exekvera javascriptkod direkt på servern, utöver detta har plattformen väldigt många användbara framework att utnyttja (om du ska utföra någon specifik uppgift är det väldigt stor chans att någon annan redan skapat ett framework för att utöfra just denna uppgift). 

Ett av dessa framework är **E**xpress, detta framework gör det möjligt att hantera POST, GET, DELETE osv på specifika "router". Utöver detta tillhandahåller den flera andra användbara funktionaliteter såsom att göra de möjligt att lägga in **M**iddleware (detta går att läsa mer om under sektionen Express).

**M**ongoDB körs ofta på en separat server och fungerar som databas för att lagra data. MongoDB **A**tlas är en molnbaserad databas som kan användas av alla som innhar nyckeln till databasern.

All kommunikation (data) som skickas mellan browser, server samt databas skickas i **J**SON format. JSON är ett kompakt textbaserat fomat som lämpar sig väl för att skickas mellan olika klienter.

## React

* **Vad är React?**
React.js är ett JavaScript-bibliotek som används för att bygga webbgränssnitt. Biblioteket utvecklades av företagen Facebook samt Instagram och är släppt med öppen källkod. Om vi tittar till designmönster MVC (Model - View - Controller) ser vi att React befinner sig under View-delen.

* **Varför är React bra?**

**Components** - React använder sig av komponenter för att uppdatera gränssnitttet. Ett exempel på en komponent skulle kunna vara en profilbeskrivning i ett socialt nätverk. När man laddar sidan för att läsa specifikationen om en person laddas informationen upp som en komponent. Det vill säga, informationen inhämtas från databasen och react uppdaterar sedan HTML filen med informationen i en komponent.

**Virtual DOM:** - Virtual DOM (Document object Model) är en direkt representation av ett DOM objekt. Det virituala dokumentet går att se som en kopia av orginal dokumentet. När en förändring sker i gränssnittet (UI) jämför webbapplikationen förändingen som skedde mellan orginal dokumentet samt det virituella dokumentet. Detta gör att applikationen exekveras snabbt samt gör det möjligt att endast uppdatera specifika delar av gränsnittet istället för att behöva skapa en helt ny layout av HTML filen.

**JSX** - JSX står för Javascript XML och är ett HTML samt XML "extension" (utvecklingspaket) till React. Detta paket underlättar hanteringen när det kommer till att skriva komponenter i React.

**Redux** - Denna del kan ses som en aning komplicerad och svårförståelig om man ej tidigare utvecklat med React. (Om du ej tidigare utvecklat med React och känner att du har svårt att greppa konceptet med hur React fungerar skulle jag avråda dig ifrån att lägga ner alldeles för mycket kraft på att förstå detta segment innan du testat på React och förstått grunden).
Redux är en extension som används för att underlätta hanteringen av data inom applikationen. Det finns inget krav på att använda sig av denna extension. Om webbapplikationen ej är uppbyggd med någon större datahantering kan det vara att föredra att ej använda sig av denna modell. Översiktligt kan man beskriva Redux som ett moln som finns ovanför applikationslagret som gör det möjligt för olika delar av applikationen att komma åt data. Som ett expemel kan det vara bra för en del av applikationen att komma åt en profilbild som är länkad till en viss profil. En miniatyr denna profilbild kanske sedan ska anvädas när en sökning av användare utförs. Istället för att måste gå igenom flera "lager" innan man kan plocka fram denna bild gör Redux det möjligt för alla komponenter inom applikationen att få tillgång till det som lagras där. Det blir en aning komplicerat innan man förstått uppläget men när man väl förstått konceptet är det väldigt användbart samt tillför ett bättre struktur till koden. 
Redux används för att underlätta datahanteringen inom applikationen. 

Användningen av dessa olika extensions samt komponenter gör React till ett väldigt kraftigt utvecklingsverktyg. När man väl förstår sig på hur React fungerar är det möjligt att utveckla sin kunskap genom att börja använda sig av React Native. Med detta verktyg kan man utveckla Android samt IOS baserade applikationer.

* **Hur använder man React?**

## Node.js

* **Vad är Node.js?**

* **Varför är Node.js bra?**

* **Hur använder man Node.js?**

## Express
### Vad är Express?

Express är ett tilläggs-paket till Node.js och installeras via npm. Det Node.js's mest populära tillägg. Eftersom Node.js opererar back-end så är även Express back-end.

Express är ett ramverk ovanpå Node.js - alltså en samling funktioner skrivna i Node.js. Utan dessa funktioner skulle utvecklaren behöva skriva stora mängder kod för simpla uppgifter. Funktionerna är vanligt förekommande och en funktion kan användas i många olika syften. Utvecklaren adderar sedan egen kod till dessa funktioner för att fylla applikationens syfte.

Express syfte i MERN-stacken är att göra det enkelt att ta emot HTTP-requests från front-end (React) och skicka tillbaka HTTP-respons. Express är alltså back-end-serverns API mot front-end.

### Varför är Express bra?

Express gör det enklare och snabbare att utveckla i Node.js.

Ett minimalistiskt exempel: När front-end (React) skickar en HTTP-request krävs följande kod utan Express:
```javascript
const server = http.createServer(function(req, res) {
  if (req.url === ’/’) {
    res.writeHead(200 { ’Content-Type’ : ’application/json’ });
    res.end(JSON.stringify(data));
  }
});
```
Med Express räcker denna kod:
```javascript
app.get('/', function(req, res) {
  res.send(JSON.stringify(data);
});
```

I fallet ovan slipper man en if-sats och man slipper skriva och fylla i Content-Type. I en applikation som hanterar ett tiotal olika typer av HTTP-meddelanden blir det snabbt mycket mer att hantera för utvecklaren.

### Hur använder man Express?

#### Request & Response

#### Middleware

#### Routes

Express har en inbyggd router. Detta gör att man kan strukturera sin kod så att HTTP-förfrågningar som om exempelvis profilen i en mapp och HTTP-förfrågningar om ett foruminlägg i en annan.


#### Body Parser???



## MongoDB

* **Vad är MongoDB?**

* **Varför är MongoDB bra?**

* **Hur använder man MongoDB?**

## Hur kommer jag igång?

* **React**

* **Node.js**

* **Express**

I server.js:
```javascript
// Importera ramverket så att det går att använda
const express = require('express');

// Tilldela Express till en variabel så att man kan använda Express-funktionerna
const app = express();

// Ta emot olika typer av HTTP-förfrågningar
app.get('/login', function(req, res) {
  // Här kan du manipulera data i den mottagna HTTP-requesten
  // Här kan du interagera med databasen
  // Här kan du skicka tillbaka en HTTP-response
});
app.post('/login', function(req, res) {
  // Här kan du manipulera data i den mottagna HTTP-requesten
  // Här kan du interagera med databasen
  // Här kan du skicka tillbaka en HTTP-response
});

// Lyssna efter HTTP-förfrågningar som i det här fallet skickas till port http://localhost:5000/
app.listen(5000);

```

* **MongoDB**
