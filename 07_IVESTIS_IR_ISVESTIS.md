# 07 – Įvestis ir išvestis

## `console.log()`

Dažniausias mokymosi metu naudojamas būdas pamatyti rezultatą.

```js
let age = 28;

console.log(age);
```

## `alert()`

Naršyklėje parodo pranešimą:

```js
alert("Labas!");
```

Node.js terminale `alert()` neveikia.

## `prompt()`

Naršyklėje gali paprašyti vartotojo įvesti reikšmę:

```js
let name = prompt("Koks tavo vardas?");
```

`prompt()` paprastai grąžina **string**.

Jeigu reikia skaičiaus:

```js
let age = Number(prompt("Kiek tau metų?"));
```

## Kodėl svarbus duomenų tipas?

```js
let a = "5";
let b = "2";

console.log(a + b); // "52"
```

Jei konvertuojame:

```js
let a = Number("5");
let b = Number("2");

console.log(a + b); // 7
```

## Mokantis per Node

Dažniausiai užtenka:

```js
console.log(...)
```

Paleidimas:

```powershell
node failas.js
```

## Dažna klaida

Jei terminale esi kitame folderyje, Node failo neras.

Pirma:

```powershell
cd "kelias\ikiolderio"
```

tada:

```powershell
node failas.js
```
