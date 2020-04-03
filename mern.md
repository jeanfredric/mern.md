# MERN

Beskrivning. Det som är bra med den här stacken är att man genomgående endast använder JavaScript och JSON.

Verktyg | Beskrivning
:--- | :---
**M**ongoDB | Databas
**E**xpress | Ramverk som underlättar Node.js
**R**eact   | View
**N**ode.js | Controller & Model

Det är även bra att kunna:
* **HTTP** - Hur protokollet är uppbyggt, meddelande-koder och typer av förfrågningar.
* **JSON** - Lättviktat språk som används när man skickar kod mellan tex. klient och server.
* **Postman** - HTTP-klient att testa sitt program med genom att skicka requests. Istället för att använda webbläsaren.
* **React Hooks** - Tillägg till React som gör det möjligt att skapa states utan att skapa en klass.
* **Redux** - Underlättar när man har mycket data i React. När man tex. vill dela states mellan komponenter.

## React
Installera react genom att gå till din projektmapp och skriv in följande kommando:
```
npx create-react-app
```

## Express


### Middleware
Funktioner som har tillgång till HTTP-request och respons-objekt. 
* Express har inbyggd middleware
* Det finns ytterligare tredjeparts middleware
* Man kan bygga egna middleware

I samband med att man tar emot en HTTP-request från klienten så kan man kalla på denna middleware-funktionen. I exemplet nedan kallar vi på en middleware-funktion som heter auth innan requesten hanteras:
```javascript
router.get('/', auth, (req, res) => {
  res.send('Middleware function auth has been executed before this line');
});
```
Man kan även köra flera middleware-funktioner:

```javascript
router.get('/', [auth, check], (req, res) => {
  res.send('Middleware functions auth and check has been executed before this line');
});
```
## Node.js
Består av tre core-moduler:
* **HTTP** *- Används för att kommunicera med en web-klient.*
* **path** *- Kan navigera och hämta bland fil-rutter.*
* **fs** *- Kan skapa filer och mappar*

### Node Packet Manager (npm)
Gör det möjligt att installera tredjepartspaket. Alla paket finns att läsa om [här](https://www.npmjs.com/)  och nedan finns några exempel:
* **concurrently** *- Gör det möjligt att köra React och Express samtidigt*
* **nodemon** *- Gör att man inte måste starta om servern vid varje ändring*
* **bcryptjs** *- Verktyg för att kryptera lösenord*
* **config** *- Ger möjlighet att spala globala variabler*
* **express** *- Mängder funktioner som underlättar användningen av Node.js*
* **express-validator** *- Funktioner som gör det möjlighet att validera data (lösenord, användarnamn etc) från vyn*
* **gravatar** *- Hämtar en avatar om användarens email är kopplat till gravatar, lite som bitmoji*
* **jsonwebtoken** *- Hjälper till att hålla koll på vem som är inloggad samt avgör vilka routes användaren har tillgång till*
* **mongoose** *- Innehåller funktioner som underlättar gränssnittet mellan Node.js och MongoDB, motsvarar DAL*
* **request** *- Förenklar syntax i samband med HTTP-meddelanden*

*(Vissa av dessa kanske bör tillhöra annat än Node.js dock. Typ mongoose är la MongoDB? Borde vi reda ut)*

Installera alla samtidigt genom följande syntax i terminalen:
```
npm i express express-validator bcryptjs config gravatar jsonwebtoken mongoose request
```
Kör servern genom att navigera till rätt mapp och kör följande kommando:
```
npm run server
```

### async / await
Varje gång vi använder mongoose måste vi använda denna pga "it returns a promise" vad det nu innebär.

## MongoDB

En fördel jämte relationsdatabaser är att man kan stoppa in data utan att på förhand bestämma namn typ osv på den data som ska sparas.

Man kan med ett funktionsanrop (mha mongoose!?) hämta ett objekt från servern och sedan skicka till klienten. Eftersom alla program förstår samma språk behöver inget parsas. Exempel:

```javascript
res.json(User.findById(req.user.id));
```

Det går självklart även att spara ned objektet från servern i ett JavaScript-objekt:

```javascript
let user = User.findById(req.user.id);
```

## Markdown language (.md)

* [Mastering Markdown](https://guides.github.com/features/mastering-markdown/) - En guide till språket
* [Syntax](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) - Markdown syntax
* [Template](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2) - Exempel på README.md
* [Traversy](https://gist.github.com/bradtraversy/c831baaad44343cc945e76c2e30927b3) - Exempel på hur Brad Traversys .md
