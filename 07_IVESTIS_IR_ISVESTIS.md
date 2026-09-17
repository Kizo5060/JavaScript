# Įvestis ir išvestis

#js #input #output

## `console.log()`
Patogiausias mokantis.

```js
console.log("Labas");
```

## `alert()`
Parodo iššokantį langą naršyklėje.

```js
alert("Labas");
```

## `prompt()`
Paklausia vartotojo ir grąžina tekstą.

```js
let name = prompt("Koks tavo vardas?");
```

Svarbu: `prompt()` dažniausiai grąžina **String**.

Jei reikia skaičiaus:

```js
let age = Number(prompt("Kiek tau metų?"));
```

## `confirm()`
Parodo OK / Cancel.

```js
let answer = confirm("Ar tęsti?");
```

Gauna:
- `true`, jei OK;
- `false`, jei Cancel.

## Išvedimas į HTML

```js
document.getElementById("result").innerHTML = "Labas";
```

Susiję:
- [[04_DUOMENU_TIPAI]]
- [[08_IF_ELSE]]
