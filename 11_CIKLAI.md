# 11 – Ciklai

Ciklas leidžia kartoti kodą.

## `while`

Naudojame, kai nežinome, kiek kartų reikės kartoti.

```js
let i = 1;

while (i <= 5) {
    console.log(i);
    i++;
}
```

Svarbu pakeisti sąlygoje naudojamą reikšmę, kitaip gali gautis begalinis ciklas.

## `do...while`

Kodas įvykdomas bent vieną kartą.

```js
let i = 1;

do {
    console.log(i);
    i++;
} while (i <= 5);
```

## `for`

Kai žinome, kiek kartų kartosime:

```js
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

Išskaidymas:

```text
let i = 0 → nuo ko pradedame
i < 5     → iki kada kartojame
i++       → po kiekvieno rato pridedame 1
```

## `for...of`

Patogus masyvams ir iteruojamoms reikšmėms.

```js
let fruits = ["apple", "banana", "orange"];

for (let fruit of fruits) {
    console.log(fruit);
}
```

Skaitome:

> kiekvienam `fruit` iš `fruits`.

Taip pat tinka string simboliams:

```js
for (let char of "Labas") {
    console.log(char);
}
```

## `for...in`

Dažniausiai naudojamas objekto raktams:

```js
let user = {
    name: "Jonas",
    age: 28
};

for (let key in user) {
    console.log(key);
    console.log(user[key]);
}
```

## `break`

Nutraukia ciklą:

```js
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break;
    }

    console.log(i);
}
```

## `continue`

Praleidžia vieną iteraciją:

```js
for (let i = 0; i < 5; i++) {
    if (i === 2) {
        continue;
    }

    console.log(i);
}
```

## Kaip pasirinkti?

```text
while      → nežinai, kiek kartų suksis
do...while → turi suveikti bent kartą
for        → žinai pakartojimų skaičių
for...of   → nori kiekvieno masyvo elemento / string simbolio
for...in   → nori objekto key
```

---

## Ciklas eilutė po eilutės

```js
for (let i = 0; i < 3; i++) {
    console.log(i);
}
```

Vykdymas:

```text
i = 0 → 0 < 3 → true → spausdina 0 → i tampa 1
i = 1 → 1 < 3 → true → spausdina 1 → i tampa 2
i = 2 → 2 < 3 → true → spausdina 2 → i tampa 3
i = 3 → 3 < 3 → false → ciklas baigiasi
```

## Ciklas per masyvą su indeksais

```js
let names = ["Jonas", "Petras", "Mantas"];

for (let i = 0; i < names.length; i++) {
    console.log(names[i]);
}
```

Čia `i` yra indeksas.

## Tas pats su `for...of`

```js
for (let name of names) {
    console.log(name);
}
```

Jei indekso nereikia, `for...of` dažnai lengviau skaityti.

## Kintamojo kaupimas cikle

Suma:

```js
let sum = 0;

for (let number of [2, 4, 6]) {
    sum += number;
}

console.log(sum); // 12
```

Skaičiavimas:

```js
let count = 0;

for (let number of [1, 2, 3, 4]) {
    if (number % 2 === 0) {
        count++;
    }
}

console.log(count); // 2
```

Tai labai dažni užduočių šablonai.

