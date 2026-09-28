# 17 – Masyvai išsamiau

## Sukūrimas

```js
let numbers = [1, 2, 3];
let empty = [];
```

Taip pat egzistuoja:

```js
let numbers = new Array(1, 2, 3);
```

Pradžiai paprasčiau naudoti `[]`.

## Reference

Masyvas yra objektas. Priskyrus vieną masyvą kitam:

```js
let a = [1, 2, 3];
let b = a;

b.push(4);

console.log(a);
```

Pasikeis ir `a`, nes abu kintamieji rodo į tą pačią vietą atmintyje.

## Kopija su spread

```js
let a = [1, 2, 3];
let b = [...a];

b.push(4);
```

Dabar `a` ir `b` atskiri.

## Spread `...`

```js
let a = [1, 2];
let b = [3, 4];

let all = [...a, ...b];
```

## Rest parameter

```js
function sum(...numbers) {
    console.log(numbers);
}

sum(1, 2, 3);
```

`numbers` funkcijoje bus masyvas.

# Pagrindiniai metodai

## `push()`

Prideda į galą:

```js
arr.push("x");
```

## `pop()`

Pašalina paskutinį:

```js
arr.pop();
```

## `shift()`

Pašalina pirmą:

```js
arr.shift();
```

## `unshift()`

Prideda į pradžią:

```js
arr.unshift("x");
```

## `splice()`

Keičia originalų masyvą.

```js
arr.splice(start, deleteCount, newItem);
```

Pvz.:

```js
let arr = ["a", "b", "c"];

arr.splice(1, 1);

console.log(arr); // ["a", "c"]
```

## `slice()`

Nukopijuoja dalį į naują masyvą:

```js
let arr = [1, 2, 3, 4];

let part = arr.slice(1, 3);
```

Originalas nesikeičia.

## `map()`

Transformuoja kiekvieną elementą ir grąžina naują masyvą.

```js
let numbers = [1, 2, 3];

let doubled = numbers.map(number => number * 2);
```

## `forEach()`

Atlieka veiksmą su kiekvienu elementu.

```js
numbers.forEach(number => {
    console.log(number);
});
```

Paprastai nenaudojamas rezultatui grąžinti.

## `concat()`

Sujungia masyvus:

```js
let result = [1, 2].concat([3, 4]);
```

## `filter()`

Palieka tik sąlygą atitinkančius:

```js
let numbers = [1, 2, 3, 4];

let even = numbers.filter(number => number % 2 === 0);
```

## `find()`

Grąžina pirmą atitinkantį elementą:

```js
let found = numbers.find(number => number > 2);
```

## `sort()`

Stringams:

```js
names.sort();
```

Skaičiams:

```js
numbers.sort((a, b) => a - b);
```

## `reduce()`

Sutraukia masyvą į vieną reikšmę.

Pvz. suma:

```js
let numbers = [1, 2, 3];

let sum = numbers.reduce((total, number) => {
    return total + number;
}, 0);
```

## Kaip pasirinkti metodą?

```text
pridėti galą       → push
pašalinti galą     → pop
pridėti pradžią    → unshift
pašalinti pradžią  → shift
kopijuoti dalį     → slice
keisti/trinti      → splice
pakeisti kiekvieną → map
atrinkti           → filter
rasti vieną        → find
surikiuoti         → sort
suskaičiuoti į 1   → reduce
```
