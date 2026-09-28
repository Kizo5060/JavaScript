# 20 pamoka – JavaScript datos

## Dabartinė data

```js
let now = new Date();

console.log(now);
```

`Date` yra objektas.

## Timestamp

Timestamp – milisekundžių kiekis nuo:

```text
1970-01-01 00:00:00 UTC
```

```js
let date = new Date(0);

console.log(date);
```

Dabartinis timestamp:

```js
Date.now();
```

Datos timestamp:

```js
let date = new Date();

date.getTime();
```

Timestamp į datą:

```js
let timestamp = 1700000000000;

let date = new Date(timestamp);
```

## Datos kūrimas iš string

```js
let date = new Date("2017-01-26");
```

## Datos kūrimas iš dalių

```js
let date = new Date(2026, 8, 24);
```

Svarbu:

```text
mėnesiai skaičiuojami nuo 0
0 = sausis
1 = vasaris
...
8 = rugsėjis
11 = gruodis
```

## Informacijos gavimas

```js
date.getFullYear();
date.getMonth();
date.getDate();
date.getDay();
date.getHours();
date.getMinutes();
date.getSeconds();
date.getMilliseconds();
date.getTime();
```

### `getDate()` ir `getDay()` nėra tas pats

```text
getDate() → mėnesio diena, pvz. 24
getDay()  → savaitės diena, 0–6
```

## Datos keitimas

```js
date.setFullYear(2030);
date.setMonth(5);
date.setDate(15);
date.setHours(12);
date.setMinutes(30);
```

## Datų palyginimas

```js
let a = new Date("2026-01-01");
let b = new Date("2026-02-01");

console.log(a < b); // true
```

## Dienų skirtumas

```js
let date1 = new Date("2026-09-01");
let date2 = new Date("2026-09-10");

let difference = date2 - date1;

let days = difference / (1000 * 60 * 60 * 24);

console.log(days); // 9
```

## Mėnesio pavadinimas su `switch`

```js
let month = date.getMonth();

switch (month) {
    case 0:
        console.log("Sausis");
        break;
    case 1:
        console.log("Vasaris");
        break;
}
```

## Moment.js

Moment.js – biblioteka darbui su datomis.

```js
import moment from "moment";

let now = moment();

console.log(now.format("YYYY-MM-DD"));
```

Jei naudojamas ES module `import`, `package.json` turi turėti:

```json
"type": "module"
```

## Ką prisiminti

```text
new Date()       dabartinė data
Date.now()       dabartinis timestamp
getTime()        Date → timestamp
getFullYear()    metai
getMonth()       mėnuo 0–11
getDate()        mėnesio diena
getDay()         savaitės diena
```

---

## Datos objekto išskaidymas

Turime:

```js
let date = new Date("2026-09-24");
```

Galime atskirai pasiimti:

```js
let year = date.getFullYear();
let month = date.getMonth();
let day = date.getDate();
```

Svarbiausia nepainioti:

```text
getMonth() → 0–11
getDate()  → mėnesio diena
getDay()   → savaitės diena
```

## Kodėl datų skirtumas duoda didelį skaičių?

```js
let difference = date2 - date1;
```

Gaunamos **milisekundės**.

Todėl:

```text
1000 ms = 1 sekundė
60 sekundžių = 1 minutė
60 minučių = 1 valanda
24 valandos = 1 diena
```

Dienoms:

```js
difference / (1000 * 60 * 60 * 24)
```

## Dažna klaida su mėnesiu

```js
new Date(2026, 9, 1)
```

čia `9` reiškia **spalį**, ne rugsėjį.

Nes:

```text
0 sausis
1 vasaris
...
8 rugsėjis
9 spalis
```

