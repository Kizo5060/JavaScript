# JavaScript Strings

## Nauja eilutė tekste

Kai naudojame paprastas kabutes `" "` arba `' '`, naujai eilutei galime naudoti:

```js
\n
```

Pvz.:

```js
let guestList = "Guests:\n * John\n * Pete\n * Mary";

console.log(guestList);
```

Rezultatas:

```text
Guests:
 * John
 * Pete
 * Mary
```

## Specialūs simboliai

Dažniausiai naudojami:

```text
\n   nauja eilutė
\r   carriage return
\"   dviguba kabutė
\'   vienguba kabutė
\\   backslash
\t   tab
```

Svarbiausia:

```text
\n = nauja eilutė
\t = tab
\\ = \
```

---

## Kabutės teksto viduje – escape

Jeigu tekstą rašome su viengubomis kabutėmis, bet pačiame tekste irgi reikia `'`, prieš ją rašome `\`.

```js
alert('I\'m the Walrus!');
```

Rezultatas:

```text
I'm the Walrus!
```

Tas `\` reiškia, kad kabutė nėra string pabaiga, o yra teksto dalis.

Pvz. su dvigubomis kabutėmis:

```js
let text = "He said: \"Hello\"";
```

---

## Backticks `` ` ` ``

Su backticks galima tekstą rašyti per kelias eilutes be `\n`.

```js
let str2 = `Hello
World`;
```

Rezultatas:

```text
Hello
World
```

Jei stringą rašome su backticks, paprastų `' '` ar `" "` kabučių dažniausiai escape'inti nereikia.

```js
alert(`I'm the Walrus!`);
```

Trumpai:

```text
' ' arba " "  → naujai eilutei dažnai reikia \n
` `            → galima rašyti per kelias eilutes tiesiogiai
```

---

## String ilgis – `.length`

Norint sužinoti, kiek simbolių yra tekste, naudojame `.length`.

```js
"use strict";

let str = "My name";

console.log(str.length);
```

Rezultatas:

```text
7
```

Tarpas irgi skaičiuojamas kaip simbolis.

Trumpai:

```js
string.length
```

grąžina teksto simbolių kiekį.

---

## String simbolių indeksai

Kiekvienas string simbolis turi savo indeksą.

Svarbu: indeksas prasideda nuo `0`.

```js
let text = "Javascript";
```

Indeksai:

```text
J a v a s c r i p t
0 1 2 3 4 5 6 7 8 9
```

Pvz.:

```js
console.log(text[0]);
```

grąžins:

```text
J
```

O:

```js
console.log(text[4]);
```

grąžins:

```text
s
```

Trumpai:

```text
position = žmogui įprastas skaičiavimas nuo 1
index    = JavaScript skaičiuoja nuo 0
```

---

## String simbolio paėmimas pagal indeksą

Turime:

```js
let str = "Hello";
```

Pirmą simbolį galima paimti dviem būdais:

```js
console.log(str[0]);
```

arba:

```js
console.log(str.charAt(0));
```

Abu grąžins:

```text
H
```

### Paskutinis simbolis

```js
console.log(str[str.length - 1]);
```

grąžins:

```text
o
```

Trumpai:

```js
str[0]              // pirmas simbolis
str.charAt(0)       // pirmas simbolis
str[str.length - 1] // paskutinis simbolis
```

---

## String yra nekeičiamas (`immutable`)

JavaScript stringo simbolio negalima pakeisti tiesiogiai pagal indeksą.

Negalima:

```js
let str = "Hi";

str[0] = "h";
```

Reikia sukurti naują stringą:

```js
let str = "Hi";

str = "h" + str[1];

console.log(str);
```

Rezultatas:

```text
hi
```

Trumpai:

```text
String = immutable
```

Tai reiškia, kad pats stringas nekeičiamas vietoje.

---

# Dažniausiai naudojami String metodai

## `charAt()`

`charAt()` grąžina simbolį pagal nurodytą indeksą.

```js
let text = "HELLO WORLD";

let letter = text.charAt(1);

console.log(letter);
```

Rezultatas:

```text
E
```

Paskutinis simbolis:

```js
let letter = text.charAt(text.length - 1);
```

---

## `concat()`

`concat()` sujungia du ar daugiau tekstų.

```js
let text1 = "Hello";
let text2 = "world!";

let result = text1.concat(" ", text2);

console.log(result);
```

Rezultatas:

```text
Hello world!
```

Galima ir taip:

```js
let result = text1 + " " + text2;
```

---

## `replace()` ir `replaceAll()`

### `replace()`

Pakeičia pirmą rastą teksto dalį.

```js
let text = "Visit Microsoft!";

let result = text.replace("Microsoft", "W3Schools");

console.log(result);
```

Rezultatas:

```text
Visit W3Schools!
```

### `replaceAll()`

Pakeičia visus sutapimus.

```js
let result = "1 abc 2 abc 3".replaceAll("abc", "xyz");

console.log(result);
```

Rezultatas:

```text
1 xyz 2 xyz 3
```

Trumpai:

```text
replace()    → pakeičia pirmą rastą tekstą
replaceAll() → pakeičia visus rastus sutapimus
```

---

## `split()`

`split()` naudojamas tekstą suskaidyti į masyvą.

```js
const greeting = "What a beautiful world";

const arr = greeting.split(" ");

console.log(arr);
```

Rezultatas:

```js
["What", "a", "beautiful", "world"]
```

`split(" ")` reiškia, kad tekstą skaidome per tarpus.

Jeigu naudojame tuščią stringą:

```js
const arr = greeting.split("");
```

tekstą suskaidys į atskirus simbolius.

Trumpai:

```text
split(" ") → padalina tekstą į žodžius
split("")  → padalina tekstą į simbolius
```

Svarbu: `split()` rezultatas yra array, ne string.

---

## `split()` + `join()`

Dažnai `split()` naudojamas kartu su `join()`.

```js
const sentence = "Hello world this is JavaScript";

const words = sentence.split(" ");

console.log(words);
```

Rezultatas:

```js
["Hello", "world", "this", "is", "JavaScript"]
```

Tada masyvą galima sujungti atgal į tekstą:

```js
const dashed = words.join("-");

console.log(dashed);
```

Rezultatas:

```text
Hello-world-this-is-JavaScript
```

Trumpai:

```text
string
↓ split(" ")
array
↓ join("-")
string
```

---

## `substring()` ir `slice()`

Abu metodai paima dalį teksto tarp nurodytų indeksų.

### `substring()`

```js
const message = "JavaScript is fun.";

let result = message.substring(0, 10);

console.log(result);
```

Rezultatas:

```text
JavaScript
```

### `slice()`

```js
const str = "JavaScript is a very absurd programming language.";

console.log(str.slice(28));
```

Jei nurodome abu indeksus:

```js
console.log(str.slice(4, 15));
```

paimama teksto dalis nuo `4` iki `15` indekso.

Svarbu: galinis `end` indeksas neįtraukiamas.

---

## `toLowerCase()`

Paverčia tekstą mažosiomis raidėmis.

```js
"LABAS".toLowerCase();
```

Rezultatas:

```text
labas
```

---

## `toUpperCase()`

Paverčia tekstą didžiosiomis raidėmis.

```js
"labas".toUpperCase();
```

Rezultatas:

```text
LABAS
```

---

## `trim()`

Pašalina tarpus nuo stringo pradžios ir galo.

```js
let text = "   Labas   ";

console.log(text.trim());
```

Rezultatas:

```text
Labas
```

---

## `includes()`

`includes()` patikrina, ar nurodytas tekstas yra kito teksto dalis.

Grąžina:

```text
true
```

arba:

```text
false
```

Pvz.:

```js
let sentence = "Java is to JavaScript what Car is to Carpet.";

let check = sentence.includes("Java");

console.log(check);
```

Rezultatas:

```text
true
```

`includes()` skiria didžiąsias ir mažąsias raides.

```js
let check = sentence.includes("java");
```

Rezultatas:

```text
false
```

Galima nurodyti, nuo kurio indekso pradėti ieškoti:

```js
let check = sentence.includes("Java", 20);
```

Trumpai:

```js
text.includes("žodis")
```

patikrina, ar toks tekstas egzistuoja.

---

## `search()`

`search()` ieško atitikimo tekste ir grąžina pirmo rasto atitikimo indeksą.

Jeigu nieko neranda:

```text
-1
```

Pvz. su regex:

```js
let string1 = "JavaScript JavaScript1";

let regExp = /(JavaScript)\d/;

let index = string1.search(regExp);

console.log(index);
```

Regex:

```js
/(JavaScript)\d/
```

ieško teksto `"JavaScript"`, po kurio eina skaičius.

Trumpai:

```js
text.search(...)
```

→ grąžina pirmo atitikimo indeksą

```text
nerado → -1
```

---

# Greita atmintinė

```text
.length         simbolių kiekis
[index]         simbolis pagal indeksą
charAt()        simbolis pagal indeksą
concat()        sujungia tekstus
replace()       pakeičia pirmą atitikimą
replaceAll()    pakeičia visus atitikimus
split()         string → array
join()          array → string
substring()     paima teksto dalį
slice()         paima teksto dalį
toLowerCase()   mažosios raidės
toUpperCase()   didžiosios raidės
trim()          pašalina tarpus pradžioje ir gale
includes()      patikrina, ar tekstas yra viduje
search()        randa pirmo atitikimo indeksą
```
