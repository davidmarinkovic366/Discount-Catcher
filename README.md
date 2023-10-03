# Discount Catcher

Web aplikacija za pracenje popusta raznih proizvoda u raznim trgovinama.

:computer: Backend deo je implementiran koriscenjem Node.js framework-a Express.js, dok je za povezivanje sa bazama podataka korisceni: 
- **Redis:** **redis client** *(https://www.npmjs.com/package/redis)*
- **Neo4j:** **neo4j-driver** *(https://www.npmjs.com/package/neo4j-driver)*

:tv: Frontend deo je implementiran koriscenjem **React.js** i **Redux-a**.

## Priprema za pokretanje

Pre pokretanja, potrebno da preuzmemo sve pakete neophodne za funkcionisanje aplikacije, pa unutar foldera :file_folder: "*discount-catcher/**backend***" i "*discount-catcher/**frontend***" otvorimo novu instancu terminala i pokrenemo komandu:

```bat
npm install
```

### :key: Redis

Za potrebe aplikacije, kako bi mogli da pretrazujemo samu Redis bazu podataka, koriscena je modifikacija Redisa - **Redis Stack** *(https://redis.io/docs/about/about-stack/)*, koju mozete instalirati koriscenjem Docker Desktop-a, koriscenjem komande:

```bat
docker run -d --name redis-stack-server -p 6379:6379 redis/redis-stack-server:latest
```

Za pregled baze podataka, mozemo da koristimo **redis-cli** kroz WSL, ili **RedisInsight** *(https://github.com/RedisInsight/RedisInsight)*.


### :spider_web: Neo4j

Za potrebe ovog projekta koriscena je lokalna instanca Neo4j Community Edition, koju mozete preuzeti sa zvanicnog Neo4j sajta.

Pre pokretanja aplikacije, neophodno je popuniti bazu podataka nekim pocetnim podacima, a naredbe za popunjavanje mozemo da nadjemo u fajlu :notebook: **db.txt**, kopiramo sadrzaj fajla i izvrsimo sve naredbe unutar Neo4j konzole, nakon cega je baza spremna za rad.

## :checkered_flag: Pokretanje:

Pre pokretanja same aplikacije, potrebno je pokrenuti instance baza podataka lokalno. 

Nakon toga, ponovo otvaramo nove instance terminal-a unutar foldera :file_folder: "*discount-catcher/**backend***" i "*discount-catcher/**fronten***", i izvrsavamo komandu:

```bat
npm start
```

> *Potrebno je prvo pokrenuti backend deo aplikacije, pa tek onda frontend deo, zbog povezivanja soketa u frontend-u sa backend-om pri startovanju frontend dela aplikacije.*

Napokon, nakon pokretanja frontend dela aplikacije, mozemo da pristupimo aplikaciji koriscenjem browser-a na adresi: *http://localhost:3000*.

> :warning: Prilikom login-a kao admin, nekad je potrebno nakon unosa email-a i sifre kliknuti 2 puta na dugme: "*login*".

