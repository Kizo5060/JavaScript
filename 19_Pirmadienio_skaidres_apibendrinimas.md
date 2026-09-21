

## Funkcijos pasikartojimas

Funkcija yra kodo blokas, kurį galime išsikviesti tada, kada reikia.

```js
function calculateBill(meal, taxRate = 0.05) {
    const total = meal * (1 + taxRate);
    return total;
}
```

- `function` – nurodo, kad kuriame funkciją.
- `calculateBill` – funkcijos pavadinimas.
- `meal` ir `taxRate` – parametrai.
- `taxRate = 0.05` – numatytoji reikšmė.
- `{ }` – funkcijos kūnas.
- `return` – grąžina rezultatą.

Funkcijos iškvietimas:

```js
const myTotal = calculateBill(100, 0.15);
```

- `100` ir `0.15` – argumentai.
- Gauta reikšmė išsaugoma į `myTotal`.

Trumpai:
- **parametrai** – ką funkcija tikisi gauti;
- **argumentai** – ką realiai paduodame;
- **return** – ką funkcija grąžina.

---

## Arrow functions

Arrow function yra trumpesnis būdas užrašyti funkciją.

```js
let sum = (a, b) => a + b;
```

- `a` ir `b` – parametrai.
- `=>` – arrow function ženklas.
- Kai viskas vienoje eilutėje, `return` rašyti nereikia.

Jeigu funkcijoje daugiau kodo:

```js
let sum = (a, b) => {
    return a + b;
};
```

Kai naudojam `{ }`, dažniausiai reikia `return`.

Be argumentų:

```js
let sayHi = () => alert("Hello");
```

Su vienu argumentu:

```js
let double = n => n * 2;
```

Trumpai:
- keli parametrai → `(a, b)`
- vienas parametras → galima `n`
- nėra parametrų → `()`
- viena operacija → `return` nereikia
- kelios eilutės su `{}` → reikia `return`, jei norim grąžinti reikšmę

---

## JavaScript ciklai

Ciklai naudojami tada, kai norim tą patį kodą paleisti kelis kartus.

### `while`

Kartojamas kodas tol, kol sąlyga yra `true`.

```js
while (condition) {
    // kodas
}
```

Pvz.:

```js
let i = 0;

while (i < 5) {
    console.log(i);
    i++;
}
```

Svarbu nepamiršti keisti reikšmės, pvz. `i++`, nes kitaip ciklas gali suktis be galo.

### `do...while`

Pirma paleidžia kodą, o tik tada tikrina sąlygą.

```js
do {
    // kodas
} while (condition);
```

Svarbiausia: kodas bus paleistas **bent vieną kartą**.

### `for`

Patogu naudoti, kai žinom, kiek kartų reikia kartoti.

```js
for (let i = 0; i < 10; i++) {
    // kodas
}
```

Čia:
- `let i = 0` – nuo ko pradedam;
- `i < 10` – iki kada kartojam;
- `i++` – po kiekvieno ciklo padidinam `i` per 1.

### Kada kurį ciklą naudoti

- `while` → kai nežinom tiksliai, kiek kartų reikės kartoti.
- `do...while` → kai kodas turi įvykti bent vieną kartą.
- `for` → kai žinom, kiek kartų reikės kartoti.

---

## JavaScript masyvai

Masyvas – vieta, kur galim laikyti kelias reikšmes viename kintamajame.

Tuščias masyvas:

```js
let arr = [];
```

Masyvas su reikšmėmis:

```js
let fruits = ["Apple", "Orange", "Plum"];
```

Masyvo reikšmės vadinamos **elementais**.

### Masyvo indeksai

Indeksai prasideda nuo `0`.

```js
let fruits = ["Apple", "Orange", "Plum"];
```

- `fruits[0]` → `"Apple"`
- `fruits[1]` → `"Orange"`
- `fruits[2]` → `"Plum"`

### Elemento pakeitimas

```js
fruits[2] = "Pear";
```

Tada masyvas bus:

```js
["Apple", "Orange", "Pear"]
```

### Naujo elemento pridėjimas

```js
fruits[3] = "Lemon";
```

Tada:

```js
["Apple", "Orange", "Pear", "Lemon"]
```

Trumpai:
- `[]` → masyvas;
- indeksai prasideda nuo `0`;
- `array[index]` → gaunam elementą;
- taip pat galim pakeisti arba pridėti reikšmę.

---

## `for...of`

`for...of` naudojamas masyvams.

Jis eina per masyvą ir paima kiekvieną elementą po vieną.

```js
const vaisiai = ["Obuolys", "Bananas", "Kriaušė"];

for (const vaisius of vaisiai) {
    console.log("Vaisius:", vaisius);
}
```

Čia:
- `vaisiai` – visas masyvas;
- `vaisius` – vienas tuo metu paimtas elementas;
- `of` – imam elementus iš masyvo.

Trumpai:

```text
FOR every fruit OF fruits
```

T. y. kiekvienam vaisiui iš vaisių masyvo.

---

## `for...in`

`for...in` dažniausiai naudojamas objektams.

Jis eina per objekto raktus (`key`).

```js
const auto = {
    marke: "Audi",
    spalva: "Juoda",
    metai: 2022
};
```

```js
for (const savybe in auto) {
    console.log(savybe + ": " + auto[savybe]);
}
```

Rezultatas:

```text
marke: Audi
spalva: Juoda
metai: 2022
```

Čia:
- `auto` – objektas;
- `savybe` – kiekvienas objekto raktas;
- `auto[savybe]` – gaunam to rakto reikšmę.

Trumpai:
- `for...of` → masyvams, eina per reikšmes;
- `for...in` → objektams, eina per raktus.

---

## Spread operator `...`

`Spread operator` išskaido masyvo elementus.

```js
const arrValue = ["My", "name", "is", "Jack"];
```

Jeigu:

```js
console.log(arrValue);
```

gausim visą masyvą:

```js
["My", "name", "is", "Jack"]
```

O jeigu:

```js
console.log(...arrValue);
```

gausim:

```text
My name is Jack
```

### Masyvų sujungimas

```js
const arr1 = ["one", "two"];
const arr2 = [...arr1, "three", "four", "five"];
```

`arr2` bus:

```js
["one", "two", "three", "four", "five"]
```

### Masyvo kopija

```js
const kopija = [...arr1];
```

Trumpai:
- `...array` → išskleidžia masyvo elementus;
- patogu jungiant masyvus;
- patogu kopijuojant masyvus.
