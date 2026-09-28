# 19 – Pirmadienio skaidrių apibendrinimas

Šita pamoka sujungia kelias ankstesnes temas.

## Funkcijos

```js
function add(a, b) {
    return a + b;
}
```

Trumpas arrow variantas:

```js
const add = (a, b) => a + b;
```

## Ciklai

### `while`

```js
let i = 0;

while (i < 3) {
    console.log(i);
    i++;
}
```

### `do...while`

```js
let i = 0;

do {
    console.log(i);
    i++;
} while (i < 3);
```

### `for`

```js
for (let i = 0; i < 3; i++) {
    console.log(i);
}
```

### `for...of`

```js
let fruits = ["apple", "banana"];

for (let fruit of fruits) {
    console.log(fruit);
}
```

### `for...in`

```js
let user = {
    name: "Jonas",
    age: 20
};

for (let key in user) {
    console.log(key, user[key]);
}
```

## Masyvai

```js
let numbers = [1, 2, 3];
```

Pridėjimas:

```js
numbers.push(4);
```

## Spread

```js
let a = [1, 2];
let b = [...a, 3, 4];
```

`...a` išskleidžia masyvo elementus.

## Svarbiausia užduotims

Dažna struktūra:

```js
function task(items) {
    let result = [];

    for (let item of items) {
        if (/* sąlyga */) {
            result.push(item);
        }
    }

    return result;
}
```

Jeigu pradedi strigti – pirma nuspręsk, ar `result` turi būti:
- `[]` – jei grąžinsi masyvą;
- `""` – jei kursi tekstą;
- `0` – jei skaičiuosi kiekį arba sumą.
