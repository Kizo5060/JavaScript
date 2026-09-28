# 03 – Kintamieji

## Kas yra kintamasis?

Kintamasis – vardu pažymėta vieta reikšmei saugoti.

```js
let age = 28;
```

- `let` – deklaravimo žodis;
- `age` – kintamojo vardas;
- `28` – reikšmė.

## `let`

Naudojame, kai reikšmė vėliau gali keistis.

```js
let score = 10;
score = 15;
```

Tame pačiame scope negalima iš naujo deklaruoti tuo pačiu `let` vardu:

```js
let score = 10;
// let score = 20; // klaida
```

## `const`

Naudojame, kai kintamojo nenorime perrašyti.

```js
const PI = 3.14;
```

Blogai:

```js
const PI = 3.14;
PI = 4;
```

## `var`

Senas deklaravimo būdas.

```js
var name = "Jonas";
```

Kurso medžiagoje akcentuojama, kad geriau rinktis `let` ir `const`, nes `var` turi kitokį scope ir gali sukelti painiavą.

## Scope

Kintamasis gali galioti tik tam tikrame bloke.

```js
if (true) {
    let message = "Labas";
}

// console.log(message); // neveiks
```

## Kintamųjų vardai

Galima:

```js
let userName;
let age2;
let _value;
let $price;
```

Negalima pradėti skaičiumi:

```js
// let 2age;
```

Kelių žodžių vardams naudojamas `camelCase`:

```js
let firstName;
let totalPrice;
```

## Kada `let`, kada `const`?

Paprasta taisyklė:

```text
reikšmė keisis → let
reikšmė neturėtų būti perrašoma → const
```

---

## Deklaravimas ir priskyrimas nėra tas pats

Deklaruojame:

```js
let age;
```

Priskiriame reikšmę:

```js
age = 28;
```

Galima ir iškart:

```js
let age = 28;
```

## Reikšmės keitimas

```js
let score = 10;

score = 20;
```

Čia antro `let` nebereikia.

Blogai:

```js
let score = 10;
let score = 20;
```

## Kodėl svarbūs geri vardai?

Blogiau:

```js
let x = 5;
let y = 10;
```

Aiškiau:

```js
let price = 5;
let quantity = 10;
```

Kuo aiškesni vardai, tuo lengviau suprasti užduotį ir rasti klaidą.

