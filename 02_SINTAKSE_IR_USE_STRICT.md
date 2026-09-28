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
