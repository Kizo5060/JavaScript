# 20 pamoka – JavaScript datos

## Dabartinė data ir laikas

JavaScript datoms naudojamas `Date` objektas.

```js
let now = new Date();

console.log(now);
```

`new Date()` be papildomų reikšmių sukuria dabartinę datą ir laiką.

Pvz. gali gauti kažką panašaus į:

```text
Sun Sep 18 2022 14:52:08 GMT+0300
```

Čia matom:
- savaitės dieną;
- mėnesį;
- dieną;
- metus;
- laiką;
- laiko juostą.

---

## Timestamp

`timestamp` – skaičius, kuris parodo, kiek milisekundžių praėjo nuo `1970-01-01 00:00:00 UTC`.

Svarbu:

```text
1 sekundė = 1000 milisekundžių
```

Pvz.:

```js
let Jan01_1970 = new Date(0);

console.log(Jan01_1970);
```

`0` reiškia `1970-01-01 00:00:00 UTC`.

Jeigu pridedam vieną parą:

```js
let Jan02_1970 = new Date(24 * 3600 * 1000);
```

Čia:
- `24` – valandos;
- `3600` – sekundžių per valandą;
- `1000` – milisekundžių per sekundę.

Datos prieš 1970 metus turi neigiamą timestamp:

```js
let Dec31_1969 = new Date(-24 * 3600 * 1000);
```

Trumpai:
- `new Date()` → dabartinė data ir laikas;
- `new Date(0)` → 1970-01-01;
- teigiamas timestamp → data po 1970-01-01;
- neigiamas timestamp → data prieš 1970-01-01.

---

## Data iš timestamp

Jeigu turim timestamp, iš jo galim sukurti datą:

```js
let timestamp = 1607110465663;

let date = new Date(timestamp);

console.log(date);
```

`new Date(timestamp)` paverčia milisekundžių skaičių į `Date` objektą.

---

## Datą paversti į timestamp

Jeigu jau turim `Date` objektą:

```js
let today = new Date();

let timeSt = today.getTime();

console.log(timeSt);
```

`getTime()` grąžina timestamp milisekundėmis.

Konkrečiai datai:

```js
let date = new Date("2018-03-15");

let timeSt = date.getTime();

console.log(timeSt);
```

---

## `Date.now()`

Jeigu reikia tik dabartinio timestamp:

```js
let timestamp = Date.now();

console.log(timestamp);
```

Tai praktiškai tas pats kaip:

```js
let now = new Date();
let timestamp = now.getTime();
```

Trumpai:

```text
new Date(timestamp) → timestamp į datą
date.getTime()      → data į timestamp
Date.now()          → dabartinis timestamp
```

---

## Datos kūrimo būdai

### Data kaip tekstas

```js
let date = new Date("2017-01-26");

console.log(date);
```

Formatas dažniausiai:

```text
YYYY-MM-DD
```

Pvz.:

```text
2017-01-26
```

reiškia 2017 metų sausio 26 dieną.

---

### Metai, mėnuo, diena ir laikas atskirai

```js
new Date(metai, menuo, diena, valandos, minutes, sekundes, milisekundes);
```

Pvz.:

```js
new Date(2011, 0, 1, 0, 0, 0, 0);
```

Tai reiškia:

```text
2011-01-01 00:00:00
```

Svarbu: mėnesiai prasideda nuo `0`.

```text
0  = sausis
1  = vasaris
2  = kovas
3  = balandis
...
11 = gruodis
```

Todėl:

```js
new Date(2011, 0, 1);
```

reiškia 2011 metų sausio 1 dieną.

Jeigu valandų, minučių ar sekundžių nenurodom, jos bus `0`.

Pvz.:

```js
let date = new Date(2011, 0, 1, 2, 3, 4, 567);
```

Čia:
- `2011` – metai;
- `0` – sausis;
- `1` – diena;
- `2` – valanda;
- `3` – minutės;
- `4` – sekundės;
- `567` – milisekundės.

---

## Informacijos gavimas iš Date objekto

Kai turim datą:

```js
let date = new Date();
```

galim pasiimti atskiras jos dalis.

### `getFullYear()`

Grąžina metus:

```js
date.getFullYear();
```

Pvz.:

```text
2026
```

### `getMonth()`

Grąžina mėnesį nuo `0` iki `11`.

```js
date.getMonth();
```

Svarbu:

```text
0 = sausis
1 = vasaris
...
11 = gruodis
```

### `getDate()`

Grąžina mėnesio dieną nuo `1` iki `31`.

```js
date.getDate();
```

Svarbu nesumaišyti su `getDay()`.

### `getHours()`

Grąžina valandą nuo `0` iki `23`.

```js
date.getHours();
```

### `getMinutes()`

Grąžina minutes nuo `0` iki `59`.

```js
date.getMinutes();
```

### `getSeconds()`

Grąžina sekundes nuo `0` iki `59`.

```js
date.getSeconds();
```

### `getMilliseconds()`

Grąžina milisekundes nuo `0` iki `999`.

```js
date.getMilliseconds();
```

### `getTime()`

Grąžina timestamp:

```js
date.getTime();
```

### `getDay()`

Grąžina savaitės dieną nuo `0` iki `6`.

```js
date.getDay();
```

```text
0 = sekmadienis
1 = pirmadienis
2 = antradienis
3 = trečiadienis
4 = ketvirtadienis
5 = penktadienis
6 = šeštadienis
```

Svarbu:

```text
getDate() → mėnesio diena
getDay()  → savaitės diena
```

---

## Mėnesio pavadinimas žodžiu

Jeigu norim gauti ne skaičių, o žodį, pvz. `sausis`, `vasaris`, galim naudoti `switch`.

```js
let date = new Date();
let month = date.getMonth();

switch (month) {
    case 0:
        console.log("Sausis");
        break;
    case 1:
        console.log("Vasaris");
        break;
    case 2:
        console.log("Kovas");
        break;
    case 3:
        console.log("Balandis");
        break;
    case 4:
        console.log("Gegužė");
        break;
    case 5:
        console.log("Birželis");
        break;
    case 6:
        console.log("Liepa");
        break;
    case 7:
        console.log("Rugpjūtis");
        break;
    case 8:
        console.log("Rugsėjis");
        break;
    case 9:
        console.log("Spalis");
        break;
    case 10:
        console.log("Lapkritis");
        break;
    case 11:
        console.log("Gruodis");
        break;
}
```

Čia `getMonth()` duoda skaičių, o `switch` pagal tą skaičių parenka mėnesio pavadinimą.

---

## Datos nustatymas ir keitimas

`get...()` metodai paima informaciją iš datos.

`set...()` metodai keičia datos reikšmes.

### `setDate()`

Pakeičia mėnesio dieną:

```js
let date = new Date();

date.setDate(20);
```

### `setFullYear()`

Pakeičia metus:

```js
date.setFullYear(2020);
```

Galima nurodyti ir mėnesį bei dieną:

```js
date.setFullYear(2020, 5, 15);
```

### `setHours()`

Pakeičia valandą:

```js
date.setHours(15);
```

### `setMinutes()`

Pakeičia minutes:

```js
date.setMinutes(30);
```

### `setSeconds()`

Pakeičia sekundes:

```js
date.setSeconds(45);
```

### `setMilliseconds()`

Pakeičia milisekundes:

```js
date.setMilliseconds(500);
```

### `setMonth()`

Pakeičia mėnesį:

```js
date.setMonth(0);
```

`0` reiškia sausį.

### `setTime()`

Nustato datą pagal timestamp:

```js
date.setTime(1607110465663);
```

Trumpai:

```text
get = gauti
set = nustatyti / pakeisti
```

Pvz.:

```text
getDate()  → gauna dieną
setDate()  → pakeičia dieną

getMonth() → gauna mėnesį
setMonth() → pakeičia mėnesį

getHours() → gauna valandą
setHours() → pakeičia valandą
```

---

## JavaScript datų palyginimas

Datas galima lyginti su:

```js
>
<
>=
<=
```

Pvz.:

```js
let date1 = new Date("2018-01-12");
let date2 = new Date("2018-12-12");

console.log(date1 > date2);
console.log(date1 < date2);
console.log(date1 >= date2);
console.log(date1 <= date2);
```

Kai lyginam datas, JavaScript jas lygina pagal jų laiką / timestamp reikšmę.

Paprastai:

```text
<  → ankstesnė data
>  → vėlesnė data
<= → ankstesnė arba tokia pati
>= → vėlesnė arba tokia pati
```

Geriau lyginti `Date` objektus, o ne paprastus tekstus.

---

## Amžiaus skaičiavimas

Jeigu turim gimimo datą:

```js
let birthDateString = "2007-10-03";
let birthDate = new Date(birthDateString);
let now = new Date();
```

Galim gauti skirtumą:

```js
let difference = now - birthDate;
```

Skirtumas bus milisekundėmis.

Sekundės:

```js
let seconds = Math.floor(difference / 1000);
```

Dienos:

```js
let days = Math.floor(difference / 1000 / 60 / 60 / 24);
```

Jeigu dalintume dar iš `365`, gautume tik apytikslius metus:

```js
let age = difference / 1000 / 60 / 60 / 24 / 365;
```

Tai nėra visiškai tikslu, nes yra keliamieji metai.

`Math.floor()` numeta dalį po kablelio:

```js
Math.floor(18.98); // 18
```

Svarbu: tikras žmogaus amžius skaičiuojamas pagal tai, ar jo gimtadienis šiemet jau buvo.

---

## Moment.js

`Moment.js` yra JavaScript biblioteka darbui su datomis ir laiku.

Ji naudojama tam, kad būtų paprasčiau:
- perskaityti datas;
- tikrinti datas;
- keisti datas;
- formatuoti datas ir laiką.

Trumpai:

```text
parse      → perskaityti
validate   → patikrinti
manipulate → keisti
display    → parodyti
```

Moment.js nėra tas pats kas standartinis `Date` objektas – tai papildoma biblioteka.

---

## Moment.js įdiegimas

Projekto aplanke:

```powershell
npm init -y
```

Jeigu PowerShell blokuoja `npm.ps1`, galima naudoti:

```powershell
npm.cmd init -y
```

Tada:

```powershell
npm.cmd install moment
```

Po įdiegimo atsiranda:

```text
node_modules
package.json
package-lock.json
```

Naudojimas:

```js
const moment = require("moment");

console.log(moment().format());
```

Galima formatuoti datą:

```js
console.log(moment().format("YYYY-MM-DD"));
```

arba:

```js
console.log(moment().format("DD/MM/YYYY"));
```

---

## Trumpas visos temos apibendrinimas

Svarbiausi dalykai iš datos temos:

```text
new Date()         → sukuria datą
Date.now()         → dabartinis timestamp
getTime()          → datos timestamp
getFullYear()      → metai
getMonth()         → mėnuo 0–11
getDate()          → mėnesio diena
getDay()           → savaitės diena 0–6
getHours()         → valandos
getMinutes()       → minutės
getSeconds()       → sekundės
setFullYear()      → pakeičia metus
setMonth()         → pakeičia mėnesį
setDate()          → pakeičia dieną
```

Svarbiausi kabliukai:

- `getMonth()` prasideda nuo `0`;
- `getDate()` ir `getDay()` nėra tas pats;
- timestamp skaičiuojamas milisekundėmis nuo 1970-01-01;
- `get...()` paima reikšmę;
- `set...()` pakeičia reikšmę;
- datas galima lyginti su `<`, `>`, `<=`, `>=`;
- `Moment.js` yra papildoma biblioteka darbui su datomis.
