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
