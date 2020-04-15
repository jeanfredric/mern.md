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
+ **Virtual DOM**

* **Hur använder man React?**

## Node.js

* **Vad är Node.js?**

* **Varför är Node.js bra?**

* **Hur använder man Node.js?**

## Express

* **Vad är Express?**

* **Varför är Express bra?**

* **Hur använder man Express?**

## MongoDB

* **Vad är MongoDB?**

* **Varför är MongoDB bra?**

* **Hur använder man MongoDB?**

## Hur kommer jag igång?

* **React**

* **Node.js**

* **Express**

* **MongoDB**
