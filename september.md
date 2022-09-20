
# Tisdag 20/9
Anteckningar: Noah

## Syntax

## Logic

### Övnings uppgift
Hitta en simple java cod man skrivit tidigare och gör om uppgiften till javascript helst någon som innehåller loops och variabler

Jens repository finns länkat på classroom v38 Tisdag JS Syntax där du kan hitta uppgifterna som gjorts samt en ogjord som används som övningsuppgift
### Jens exempel "bussbiljet Javascript"
int finns inte så blir let x = ParseInt(prompt('message')); ParseInt tvingar let att tolkas som en int istället för en string (rekommenderas av Jens så att koden tolkas som den ska)

Det kan bli problem med < och > på grund av hur = fungerar med javascript exempel

4 == '4' blir "true"

4 ===  '4' blir "false"


```js
let x = ParseInt(prompt('message'));

if (x < y) {
  alert ('message')
}

else if ('x < z'){
  alert ('message')
}
```
### Jens exempel "kalk Omkrets & radie till Javascript"
```js
const radie = document.getElementById('input-field')

const button = document.quarySelect

// Ett modärnare exempel skulle vara document.quarySelector('#input-field')

//Om man använder parseInt där innehållet inte kan vara en int så kommer man få upp en error NaN (Not a Number)

const radius = radiusImput.value;

const area = Math.PI * radius * radius;

const circumference = 2 * math.PI * radius;

const message messageBox = document.quarySelector('#message-box');

message.textContent = 'omkrets är $(circumference)cm';
messageBox.appendchild(message);
```
* koden är inte färdig furmulerad så får gå in och titta bland Jens repositaries (finns länkat i classroom v38 Tisdag JS Syntax. Filen är är Simons.js) för att se den färdiga koden.

## Funktioner
DOM = Dokument Object Model

Exempel på vad DOM står för
* .H1
* .Body

DOM kan sammanfattas som .css element och de elemt man skriver för styling

# Fredag 16/9
Antecknare: Rasmus

MySQL
* Installera MySQL genom att följa [Jens guide](https://www.jensa.xyz/posts/webbserver-programmering/#mysql) 
* Ta bort MySQL användare genom kommandot ```DROP user 'username'@'localhost'``` ifall det behövs
* Glöm inte semikolon
* TablePlus
  * ```Create a new connection```
    * MySQL
      * Anslut till localhost genom att skriva in ```localhost``` i Host fältet
      * Använd ditt MySQL användarnamn och lösenord för att skapa anslutningen
  * Högerklicka demo tabellen i TE20 databasen och exportera sedan som en .SQL 
  * Anslut till localhost användaren
  * Tryck på ```Show databases list``` och anslut till webbserver databasen du gjorde tidigare
  * ```Menu``` > ```File``` > ```Import``` > ```From SQL Dump``` > Välj SQL Dump filen > ```Import```
  * Välj ```Structure``` för att ändra och lägga till kolumner
  * Skapa en ny kolumn kallad "age" och ange den data typen ```int unsigned```, ```unsigned``` betyder att det inte kan vara negativt
* Ändra i .env så att den ansluter till localhost, kommentera ut den gammla anslutningen
* Uppdatera ```index.njk``` så att den visar de nya kolumnerna

# Fredag 9/9
Antecknare: Loke

**kom ihåg att byta text language från plain text till html i nedre högra hörnet när du arbetar med njk filer.**

**Components ska börja med “_” t.ex. “_nav.njk” för att visa att det är en component alltså en del av en sida.**

## index.js

Skapa en ny route

```js
router.get(‘/test’, function(request, response) {
 response.render(‘test.njk’, {
 title: ‘kursdemo’});
})
```

## test.njk

```html
{%extends “layout.njk” %}
{%block content %}
 <h1>{{ title }}</h1>
{% endblock %}%
```

**views > gör map som heter “components” > fil “_nav.njk”**

## nav.njk

```html
<nav>
 Sidnavigation
 <a href=”/”>Hem</a>
 <a href=”test”>Test</a>
</nav>
```

## layout.njk

lägg till “{% include “components/_nav.njk” %}” och “{% include “components/_footer.njk” %}” I body

```html
 {% include "components/_nav.njk" %}
 {% block content %}
 {% endblock %}
```

## Bilder

public > skapa images folder

components > skappa _footer.njk

```html
<footer>
 Din valfria text där du får skriva vad du vill :)🍔
</footer>
```

## Om du vill stänga dina servrar

```bash
sudo killall npm
```


# Tisdag 6/9
Antecknare: Alexander med lite Loke
* Hell yeah
* Konfigurationsfiler eller gömda filer börjar med en . [punkt]
* npm = node packet manager (first install)
  * Används för projekt, måste finnas
  * Paket kommer från package.json
    * config fil
    * uppdateras automatiskt (när du installerar paket)
* JavaScript Object Notation
  * Sparar data och skickar runt det på ett bra sätt 👍
  * Bättre version av XML (enligt Jens, ta det som du vill)
## Javascript!!!!!!!!!
* const, var och let för variabler
* index är det som laddas först i en mapp
  * Webb routern är en index (dvs. indexRouter)
* url (uniform resource locator)
  * http → https
  * localhost
  * port = localhost:3000
* port 80 är nästan alltid tillgänglig
  * http standard
* port 443
  * https standard
* port 3306
  * MySQL protocol
## Gratis domäner!!
Du behöver Github Student Pack
* Name.com
* get.tech
Mer om domäner
DNS (domain name system)
IP-adresser
localhost gör en ALS för 127.0.0.1
## Dags att installera mer
Tableplus
* Databassystem som är lätthanterlig och fin
* Create new connection… → MySQL → fyll i information (port 3306) → save
* Tables → Demo → Data
* SQL knapp → “select * from demo;” (exempel)

ඞ Efter rast fixade vi id, namn, secret_identity och bio.
Gör css och fixa index 👍
