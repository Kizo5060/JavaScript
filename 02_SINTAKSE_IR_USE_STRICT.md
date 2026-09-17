# Sintaksė ir `use strict`

#js #pagrindai

## Sakiniai
JavaScript kodas susideda iš sakinių.

```js
let age = 18;
console.log(age);
```

Kabliataškis `;` rekomenduojamas, nors dažnai nėra privalomas.

## Komentarai

```js
// vienos eilutės komentaras

/*
kelių
eilučių
komentaras
*/
```

## Case sensitive
JavaScript skiria didžiąsias ir mažąsias raides.

```js
let age = 18;
let Age = 20;
```

Čia yra **du skirtingi kintamieji**.

## `use strict`

Failo pradžioje:

```js
"use strict";
```

Tai griežtesnis JavaScript režimas ir padeda greičiau pastebėti klaidas.

## Ką verta atsiminti
- rašyk aiškius vardus;
- laikyk kodą tvarkingai;
- naudok įtraukas;
- pradžioje geriau naudok `let` ir `const`, o ne `var`.

Susiję:
- [[03_KINTAMIEJI]]
- [[15_MANO_KLAIDOS]]
