# 08 – `if / else`

`if` naudojame tada, kai programa turi **priimti sprendimą**.

## Paprastas `if`

```js
let age = 20;

if (age >= 18) {
    console.log("Pilnametis");
}
```

Skaitome:

> JEIGU `age >= 18`, vykdyk kodą `{ }`.

## `if / else`

```js
if (age >= 18) {
    console.log("Pilnametis");
} else {
    console.log("Nepilnametis");
}
```

`else` vykdomas, kai `if` sąlyga yra `false`.

## `else if`

```js
let score = 75;

if (score >= 90) {
    console.log("Labai gerai");
} else if (score >= 60) {
    console.log("Gerai");
} else {
    console.log("Reikia pasimokyti");
}
```

## Kaip atpažinti užduotyje?

Jei užduotyje matai:
- „jeigu“;
- „kitu atveju“;
- „patikrink ar“;
- „jei daugiau nei...“

greičiausiai reikia `if`.

## Pavyzdys funkcijoje

```js
function checkNumber(number) {
    if (number > 10) {
        return "Daugiau už 10";
    }

    return "10 arba mažiau";
}
```

## Svarbu apie `return`

Kai funkcija pasiekia `return`, ji baigia darbą.

```js
function test() {
    return 5;

    console.log("Šita eilutė nebus vykdoma");
}
```

---

## Sąlygų tvarka svarbi

Pvz.:

```js
let score = 95;

if (score >= 60) {
    console.log("Išlaikyta");
} else if (score >= 90) {
    console.log("Puikiai");
}
```

Čia `95` jau atitinka pirmą sąlygą, todėl iki `>= 90` programa nebeateis.

Geriau:

```js
if (score >= 90) {
    console.log("Puikiai");
} else if (score >= 60) {
    console.log("Išlaikyta");
}
```

Dažnai sąlygas patogu rašyti nuo **griežčiausios / didžiausios** į mažesnę.

## Trumpas variantas be `else`

```js
function checkAge(age) {
    if (age >= 18) {
        return "Pilnametis";
    }

    return "Nepilnametis";
}
```

Kadangi `return` užbaigia funkciją, `else` čia nebūtinas.

