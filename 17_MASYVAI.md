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

---

# Kaip suprasti svarbiausius masyvų metodus

Turime:

```js
let numbers = [1, 2, 3, 4];
```

## `forEach()` – padaryk kažką su kiekvienu

```js
numbers.forEach(number => {
    console.log(number);
});
```

Mąstymas:

```text
1 → vykdyk funkciją
2 → vykdyk funkciją
3 → vykdyk funkciją
4 → vykdyk funkciją
```

Dažniausiai naudojamas veiksmui, o ne naujam masyvui sukurti.

---

## `map()` – pakeisk kiekvieną

```js
let doubled = numbers.map(number => {
    return number * 2;
});
```

Rezultatas:

```js
[2, 4, 6, 8]
```

Originalus `numbers` lieka:

```js
[1, 2, 3, 4]
```

Mąstymas:

```text
1 → 2
2 → 4
3 → 6
4 → 8
```

---

## `filter()` – palik tik tinkamus

```js
let even = numbers.filter(number => {
    return number % 2 === 0;
});
```

Rezultatas:

```js
[2, 4]
```

Callback turi grąžinti:

```text
true  → elementas lieka
false → elementas atmetamas
```

---

## `find()` – rask pirmą tinkamą

```js
let found = numbers.find(number => {
    return number > 2;
});
```

Rezultatas:

```text
3
```

Skirtumas:

```text
filter → gali grąžinti daug elementų masyve
find   → grąžina pirmą rastą elementą
```

---

## `slice()` vs `splice()`

Tai labai lengva supainioti.

### `slice()`

```js
let arr = ["a", "b", "c", "d"];

let part = arr.slice(1, 3);
```

`part`:

```js
["b", "c"]
```

Originalas nepasikeičia.

### `splice()`

```js
let arr = ["a", "b", "c", "d"];

arr.splice(1, 2);
```

Originalas tampa:

```js
["a", "d"]
```

Trumpai:

```text
slice  → kopijuoja
splice → keičia originalą
```

---

## `sort()` su skaičiais

Blogas beginner netikėtumas:

```js
let numbers = [2, 10, 3];

numbers.sort();
```

Gali gauti ne norimą skaitinę tvarką, nes numatytasis `sort()` lygina kaip tekstą.

Skaičiams:

```js
numbers.sort((a, b) => a - b);
```

Didėjančiai.

Mažėjančiai:

```js
numbers.sort((a, b) => b - a);
```

---

## `reduce()` paprastai

```js
let numbers = [1, 2, 3, 4];

let sum = numbers.reduce((total, number) => {
    return total + number;
}, 0);
```

Galima galvoti taip:

```text
total = 0
+ 1 → 1
+ 2 → 3
+ 3 → 6
+ 4 → 10
```

Rezultatas:

```text
10
```

`0` gale yra `initialValue` – pradinė reikšmė.

---

# Masyvų užduoties mąstymas

Jei užduotis:

> Grąžink tik žodžius, kurių ilgis bent 5.

Variantas su ciklu:

```js
function longWords(words) {
    let result = [];

    for (let word of words) {
        if (word.length >= 5) {
            result.push(word);
        }
    }

    return result;
}
```

Variantas su `filter()`:

```js
function longWords(words) {
    return words.filter(word => word.length >= 5);
}
```

Abu daro tą patį.

Mokantis pradžioje ilgesnis ciklo variantas kartais net naudingesnis, nes aiškiau matosi visa logika.

