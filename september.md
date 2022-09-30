# Fredag 09/30
Antecknare : Kenth Emil Lukas Johansson den tredje
## Dags att starta med en ny mapp och installera roliga 11ty yay!
* Gör en ny mapp
* Gå in i den nya mappen 
* kör [npm init -y]
* Installera 1tty med [npm i @11ty/eleventy]
* Du kan kolla med hjälp av [la] över vad som är installerat
(Dessa tre skapar filer)
* Kör [mkdir src]
* Kör [touch .eleventy.js]
* Kör [touch .gitignore]
* Öppna sedan VSS med [code .]
## Dags för mycket rolig kod att börja funka

* I filen .eleventy skirv :
```js
module.exports = function(eleventyConfig) {
    return {
        dir: {
            input: "src",
            output: "dist"
        }
    }
};
```

* I package.json skriv under "test" (kom ihåg att det måste finnas ett "," bakom test linjen  > | "test": "echo \"Error: no test specified\" && exit 1",)
```json
"start": "eleventy --serve"
```
* Gör en index.md fil i mappen src (Skriv något roligt i den)
* Gör en mapp i src vid namn [_includes] där skapar du ditt templat
* I [_includes] mappen skapa en fil vid namn [base.njk]
* Få in HTML:5 i filen 
* I body skriv
```html
{{ content | safe}}
```
* På toppen av index.md skriv
```njk
---
layout: base.njk
title : Home
---
```
* Du kan så klart skapa flera delar av sidan med helt enkelt skapa en till .md fil
## Dags för att trycka in CSS i det hela
* I terminalen gör [ctrl, c]
* skriv [cd src]
* skriv [mkdir css]
* skriv cd ..
* [Man måste starta om eleventy för att lägga till css]
* I eleventy.js under moudle.exports skriv
```js
eleventyConfig.addPassthroughCopy("src/css")
```
* Skapa en style.css i din css mapp
* I din style skriv 
```html
body {
    max-width: min(80ch, 100vw - 1rem);
    margin-inline: auto;
}
```
* I din base.njk koppla din css som vanligt
```html
<link rel="stylesheet" href="/css/style.css">
```
## Hur man använder 11ty samt njk
* Gör en [navigation.njk] i [_includes] filen
* Nu skriva denna roliga kod i den :)
```css
<nav>
    <ul>
        <li>
            <a href="/">Home</a>
        </li>
        <li>
            <a href="/about">About</a>
        </li>
    </ul>
</nav>
```
* I [base.njk] över content safe skriv
```njk
{% include "navigation.njk" %}
```
* I filen [style.css] ska vi lägga till mer nav så skriv

```css
nav ul {
    display: flex;
    gap: 1rem;
    list-style: none;
    padding: 0;
}
```
* Skapa en ny mapp vid namn [_data] i src
* I denna mapp skapa en fil vid namn [navigation.json]
* I denna fil skriv
```json
[
    {
        "title": "Hem",
        "url": "/"
    },
    {
        "title": "Om",
        "url": "/om/"
    }
]
```
* Ta bort all kod i [navigation.njk] och byt ut det till
```css
<nav>
    <ul>
    {% for item in navigation}    
        <li>
            <a href="{{ item.url }}">{{ item.title }}</a>
        </li>    
    </ul>
</nav>
```
* Du kan även lägga till en bild med att skapa en ny mapp och lägga till den in i [.eleventy,js]

```js
module.exports = function(eleventyConfig) {
    eleventyConfig.addPassthroughCopy("src/css")
    eleventyConfig.addPassthroughCopy("src/images")
    return {
        dir: {
            input: "src",
            output: "dist"
        }
    }
};
``` 
* Du kan nu lägga till bilden som normal in i [index.md]

```md
![Foul image](/images/img.jpg)
```

# Tisdag 27/9
Anteckningar: Leo

Motsatsen till dymaisk sida kallas statisk sida.
### 
Att jobba med en statisk sida blir lätt problematiskt när man arbetar med flera produkter.

Repitera HTML och CSS. CSS -> SASS
```

cd code
mkdir te20-eleventy-intro
cd te20-eleventy-intro 

npm init -y
npm install @11ty/eleventy

git init
touch .gitignore
touch .index.html
code . 
```
I filen gitrignore skiver vi nu in
```
node_modules
public
```


Sedan skriver vi in i filen package.json
```json
"scrips":{
  "start": "eleventy --serve"
}
```
För att starta servern skriver vi in npm start i valfri terminal

Skapa en fil med namnet eleventy.js. I den skriver vi sedan in
```js
module.exports = funktion(eleventyConfig){
  
  return {
      dir: {
        input: 'src',
        output: 'public',
      },
  };
};
```
Efter ändringar i eleventy måste servern startas om med
```bash
^C //ctrl+c
npm start
```

Nu kan vi använda en mapp ```/src``` för att skapa filerna till systemet i.
I den skapar vi en mapp som heter ```_includes```, i denna mapp kan vi skapa layout filer som 11ty använder.
I ```includes``` skapa en fil med namnet ```base.njk```, denna fil kommer vara grundtemplaten för hela siten.

Fortsättning finns i intro [repot](https://github.com/jensnti/te20-eleventy-intro)

# Tisdag 20/9
Anteckningar: Noah

## Syntax

## Logic

### Övnings uppgift
Hitta en simple java cod man skrivit tidigare och gör om uppgiften till javascript helst någon som innehåller loops och variabler

Jens repository finns länkat på classroom v38 Tisdag JS Syntax där du kan hitta uppgifterna som gjorts samt en ogjord som används som övningsuppgift
* tricket med uppgiften är att man måste ha två stycken input

### Övnings uppgift #2
Gör en input där du kan vända bak och fram på input'ens text 

#### Kommandon jämförelser java till js
```js
//for loop
for (let i = 0; i <name.lenght; i++){
  console.log(name[i]); // Uppgift: hur ska det bli baklänges som en li (list)
}
// int
let x = 5;
//konstant
const y = 'hejsan svesans';
//skapa en user-list
const ul = document.createElement('ul');
//skapa en lista
const li = document.createElement('li');

//Kommand som kan vara till hjälp till uppgift på andra passet
li.textContent = BOKSTAVEN;
ul.appendChild(li);
messageBox.appendChild(ul);

console.log(x); //x kan bytas ut baserat på vad man vill titta. Används alltså för att titta så att kommandon lagras som dem ska
```
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

## Jens slutsatser
Använd konsolen i webbläsaren för att felsöka när du stöter på problem

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

