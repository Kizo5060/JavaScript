# 02 – Sintaksė ir `use strict`

## JavaScript sakiniai

JavaScript kodas sudarytas iš sakinių:

```js
let name = "Jonas";
console.log(name);
```

Kabliataškis `;` dažnai rekomenduojamas, nors daugeliu atvejų JS gali veikti ir be jo.

## Komentarai

Vienos eilutės:

```js
// čia komentaras
```

Kelių eilučių:

```js
/*
čia
kelių eilučių
komentaras
*/
```

## JavaScript yra case-sensitive

Šitie vardai yra skirtingi:

```js
let name = "Jonas";
let Name = "Petras";
```

## `"use strict"`

Kurso skaidrėse rekomenduojama `.js` failo pradžioje rašyti:

```js
"use strict";
```

Tai įjungia griežtesnį JavaScript režimą ir padeda greičiau pamatyti kai kurias klaidas.

Pvz. blogai:

```js
"use strict";

age = 25;
```

Nes `age` nebuvo deklaruotas.

Gerai:

```js
"use strict";

let age = 25;
```

## Dažna beginner klaida – skliaustai

Funkcijos blokas:

```js
function hello() {
    console.log("Labas");
}
```

`{` atidaro bloką, `}` uždaro.

## Dažna beginner klaida – kabutės

Teisingai:

```js
let text = "Labas";
```

Neteisingai:

```js
let text = "Labas;
```

## Greita patikra, kai kodas neveikia

1. Ar visi `()` uždaryti?
2. Ar visi `{}` uždaryti?
3. Ar string turi abi kabutes?
4. Ar kintamojo vardas visur parašytas vienodai?
5. Ar metodas parašytas be typo? Pvz. `toUpperCase()`.

---

## Sintaksė paprastai

JavaScript labai jautrus smulkioms rašymo klaidoms.

Pvz. šie metodai nėra tas pats:

```js
toUpperCase()
touppercase()
toUperCase()
```

Teisingas tik:

```js
toUpperCase()
```

Tas pats galioja kintamųjų vardams:

```js
let userName = "Jonas";

console.log(username); // klaida
```

Nes `userName` ir `username` yra skirtingi vardai.

## Kodo blokas

Kai matai:

```js
if (...) {

}
```

arba:

```js
function test() {

}
```

viskas tarp `{ }` priklauso tam blokui.

Todėl labai svarbu tvarkingai lygiuoti kodą:

```js
if (age >= 18) {
    console.log("Pilnametis");
}
```

Taip daug lengviau pastebėti trūkstamą skliaustą.

