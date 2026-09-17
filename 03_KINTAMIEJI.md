# Kintamieji

#js #kintamieji

Kintamasis = vieta duomenims saugoti.

## `let`
Naudok, kai reikšmė gali keistis.

```js
let age = 18;
age = 19;
```

## `const`
Naudok, kai kintamojo nenori perrašyti.

```js
const name = "Jonas";
```

## `var`
Senas deklaravimo būdas. Pradžioje jo geriau nenaudoti.

## Gera taisyklė
Jei nežinai ką rinktis:
- pradėk nuo `const`;
- jei reikšmę reikės pakeisti → `let`.

## Vardai

Gerai:

```js
let userAge = 20;
let firstName = "Jonas";
```

Blogiau:

```js
let x = 20;
```

Jei pavadinimas iš kelių žodžių, naudok `camelCase`.

## Mini pavyzdys

```js
let money = 20;
money = money + 5;

console.log(money);
```

Rezultatas:

```text
25
```

Susiję:
- [[04_DUOMENU_TIPAI]]
- [[06_OPERATORIAI]]
