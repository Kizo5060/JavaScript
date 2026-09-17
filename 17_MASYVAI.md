# 17_MASYVAI

#js #masyvai #array #javascript

## Kas yra masyvas?

Masyvas leidžia viename kintamajame saugoti kelias reikšmes.

### Sukūrimas

```js
let arr = new Array();
let arr2 = new Array(5);
let fruits = new Array("Apple", "Orange", "Plum");
```

Dažniausiai naudojamas trumpesnis variantas:

```js
let fruits = ["Apple", "Orange", "Plum"];
```

Indeksai prasideda nuo `0`:

```text
0 → Apple
1 → Orange
2 → Plum
```

Elemento pasiekimas:

```js
console.log(fruits[0]); // Apple
```

## `.length`

```js
console.log(fruits.length); // 3
```

Jeigu:

```js
fruits[10] = "Banana";
```

masyvo ilgis tampa `11`, nes indeksas `10` yra 11-ta vieta.

## Skirtingi duomenų tipai masyve

```js
let arr = [
    "Apple",
    { name: "John" },
    true,
    function () {
        console.log("hello");
    }
];
```

Objekto reikšmė:

```js
console.log(arr[1].name); // John
```

Funkcijos paleidimas:

```js
arr[3](); // hello
```

---

# Reference

Masyvas saugomas atmintyje, o kintamasis laiko nuorodą į jį.

```js
let arr1 = ["Apple", "Orange"];
let arr2 = arr1;
```

`arr1` ir `arr2` rodo į tą patį masyvą.

```js
arr2[0] = "Pear";
console.log(arr1); // ["Pear", "Orange"]
```

```js
console.log(arr1 === arr2); // true
```

---

# Spread operator `...`

Spread išskaido masyvo elementus.

```js
const arrValue = ["My", "name", "is", "Jack"];
console.log(...arrValue);
```

Rezultatas:

```text
My name is Jack
```

## Masyvų sujungimas

```js
const arr1 = ["one", "two"];
const arr2 = [...arr1, "three", "four", "five"];
```

## Kopijavimas

```js
const clone1 = arr1.slice();
const clone2 = [...arr1];
```

Abu variantai sukuria naują masyvą.

## Kelių masyvų sujungimas

```js
const numbersOne = [1, 2, 3];
const numbersTwo = [4, 5, 6];

const numbersCombined = [...numbersOne, ...numbersTwo];
```

---

# Rest parameter `...`

Rest surenka funkcijai perduotus argumentus į masyvą.

```js
function func(...args) {
    console.log(args);
}

func(3);       // [3]
func(4, 5, 6); // [4, 5, 6]
```

```text
spread → išskaido
rest   → surenka
```

---

# Masyvų metodai

## `pop()`

Pašalina paskutinį elementą.

```js
let fruits = ["Apple", "Orange", "Pear"];
let removed = fruits.pop();

console.log(removed); // Pear
console.log(fruits);  // ["Apple", "Orange"]
```

## `push()`

Prideda elementą į galą.

```js
fruits.push("Pear");
```

## `shift()`

Pašalina pirmą elementą.

```js
fruits.shift();
```

## `unshift()`

Prideda elementą į pradžią.

```js
fruits.unshift("Apple");
```

### Greita atmintinė

```text
push()    → prideda į galą
pop()     → pašalina iš galo
unshift() → prideda į pradžią
shift()   → pašalina iš pradžios
```

---

# `splice()`

`splice()` gali ištrinti, pakeisti arba įterpti elementus ir keičia originalų masyvą.

```js
arr.splice(index, deleteCount, elem1, elem2);
```

- `index` → nuo kur pradėti
- `deleteCount` → kiek ištrinti
- `elem1...` → ką įterpti

## Ištrynimas

```js
let arr = ["I", "study", "JavaScript"];
arr.splice(1, 1);

console.log(arr); // ["I", "JavaScript"]
```

## Kelių elementų pakeitimas

```js
let arr = ["I", "study", "JavaScript", "right", "now"];
arr.splice(0, 3, "Let's", "dance");

console.log(arr); // ["Let's", "dance", "right", "now"]
```

## Įterpimas nieko netrinant

```js
let arr = ["I", "study", "JavaScript"];
arr.splice(2, 0, "complex", "language");
```

Rezultatas:

```js
["I", "study", "complex", "language", "JavaScript"]
```

## Ištrintų elementų grąžinimas

```js
let arr = ["I", "study", "JavaScript", "right", "now"];
let removed = arr.splice(0, 2);

console.log(removed); // ["I", "study"]
```

Trumpai:

```text
splice(1, 1)          → ištrina
splice(1, 1, "X")     → pakeičia
splice(1, 0, "X")     → įterpia
splice(0, 3, "X","Y") → ištrina kelis ir įterpia naujus
```

---

# `slice()`

Nukopijuoja masyvo dalį į naują masyvą ir originalo nekeičia.

```js
arr.slice(start, end);
```

Svarbu: `end` indeksas neįtraukiamas.

```js
let arr = ["t", "e", "s", "t"];
console.log(arr.slice(1, 3)); // ["e", "s"]
```

Neigiamas indeksas:

```js
console.log(arr.slice(-2)); // ["s", "t"]
```

Viso masyvo kopija:

```js
let copy = arr.slice();
```

```text
slice()  → kopijuoja, originalo nekeičia
splice() → keičia originalą
```

---

# `map()`

`map()` transformuoja kiekvieną elementą ir grąžina naują masyvą.

```js
const numbers1 = [45, 4, 9, 16, 25];

const numbers2 = numbers1.map(value => value * 2);
```

Rezultatas:

```js
[90, 8, 18, 32, 50]
```

Callback gali gauti:

```text
value → dabartinis elementas
index → indeksas
array → visas masyvas
```

---

# `forEach()`

`forEach()` atlieka veiksmą su kiekvienu elementu, bet naujo masyvo automatiškai nesukuria.

```js
const names = ["Bilbo", "Gandalf", "Nazgul"];

names.forEach((item, index, array) => {
    console.log(`${item} is at index ${index} in ${array}`);
});
```

Jei reikia naujo masyvo, jį galima susikurti rankiniu būdu:

```js
const apps = ["WhatsApp", "Instagram", "Facebook"];
const playStore = [];

apps.forEach(item => {
    playStore.push(item);
});
```

```text
forEach() → atlieka veiksmą
map()     → sukuria naują transformuotą masyvą
```

---

# `concat()`

Sujungia kelis masyvus ir sukuria naują masyvą.

```js
const arr1 = ["Cecilie", "Lone"];
const arr2 = ["Emil", "Tobias", "Linus"];

const children = arr1.concat(arr2);
```

Galima prijungti ir atskiras reikšmes:

```js
const newArr = arr1.concat("Peter");
```

---

# `filter()`

Sukuria naują masyvą tik iš elementų, kurie atitinka sąlygą.

```js
let users = [
    { id: 1, name: "John" },
    { id: 2, name: "Pete" },
    { id: 3, name: "Mary" }
];

let someUsers = users.filter(item => item.id < 3);
```

Rezultatas:

```js
[
    { id: 1, name: "John" },
    { id: 2, name: "Pete" }
]
```

Jeigu niekas netinka:

```js
const result = [1, 2, 3].filter(number => number > 10);
console.log(result); // []
```

---

# `find()`

Grąžina pirmą elementą, kuris atitinka sąlygą.

```js
const array1 = [5, 12, 8, 130, 44];
const found = array1.find(element => element > 10);

console.log(found); // 12
```

Su objektais:

```js
const inventory = [
    { name: "apples", quantity: 2 },
    { name: "bananas", quantity: 0 },
    { name: "cherries", quantity: 5 }
];

const found = inventory.find(fruit => fruit.name === "cherries");
```

Jeigu nieko neranda:

```text
undefined
```

```text
find()   → pirmas tinkamas elementas
filter() → visi tinkami elementai
```

---

# `sort()`

`sort()` rikiuoja originalų masyvą.

## Tekstas

```js
let fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();
```

Rezultatas:

```js
["Apple", "Banana", "Mango", "Orange"]
```

## `reverse()`

```js
fruits.reverse();
```

Apverčia esamą tvarką.

## Skaičiai

Didėjimo tvarka:

```js
let points = [40, 100, 1, 5, 25, 10];
points.sort((a, b) => a - b);
```

Rezultatas:

```js
[1, 5, 10, 25, 40, 100]
```

Mažėjimo tvarka:

```js
points.sort((a, b) => b - a);
```

```text
(a, b) => a - b → nuo mažo iki didelio
(a, b) => b - a → nuo didelio iki mažo
```

---

# `reduce()`

`reduce()` pereina per masyvą ir pagal taisyklę visas reikšmes suveda į vieną rezultatą.

Dažnas pavyzdys – suma.

```js
const numbers = [1, 2, 3, 4];

const sum = numbers.reduce((total, number) => {
    return total + number;
}, 0);

console.log(sum); // 10
```

Skaičiavimas:

```text
0 + 1 = 1
1 + 2 = 3
3 + 3 = 6
6 + 4 = 10
```

Bendra forma:

```js
array.reduce(callback, initialValue);
```

- `callback` → skaičiuoja rezultatą
- `initialValue` → pradinė reikšmė

## Be `initialValue`

```js
const numbers = [1, 2, 3, 4];

const sum = numbers.reduce((total, number) => {
    return total + number;
});
```

Tokiu atveju pirmas elementas tampa pradine reikšme.

---

# `reduce()` callback parametrai

```js
function callbackFn(
    previousValue,
    currentValue,
    currentIndex,
    array
) {
    // veiksmai
}
```

### `previousValue`

Sukauptas ankstesnio callback rezultatas.

### `currentValue`

Dabartinis masyvo elementas.

### `currentIndex`

Dabartinio elemento indeksas.

### `array`

Visas originalus masyvas.

## Su `initialValue`

```text
previousValue = initialValue
currentValue = array[0]
currentIndex = 0
```

## Be `initialValue`

```text
previousValue = array[0]
currentValue = array[1]
currentIndex = 1
```

---

# Greita masyvų metodų atmintinė

| Metodas | Ką daro | Keičia originalą? | Ką grąžina? |
|---|---|---:|---|
| `push()` | prideda į galą | Taip | naują ilgį |
| `pop()` | pašalina iš galo | Taip | pašalintą elementą |
| `unshift()` | prideda į pradžią | Taip | naują ilgį |
| `shift()` | pašalina iš pradžios | Taip | pašalintą elementą |
| `splice()` | trina / keičia / įterpia | Taip | ištrintų elementų masyvą |
| `slice()` | kopijuoja dalį | Ne | naują masyvą |
| `concat()` | sujungia masyvus | Ne | naują masyvą |
| `map()` | transformuoja elementus | Ne | naują masyvą |
| `forEach()` | atlieka veiksmą | Ne | `undefined` |
| `filter()` | atrenka pagal sąlygą | Ne | naują masyvą |
| `find()` | randa pirmą tinkamą | Ne | elementą arba `undefined` |
| `sort()` | rikiuoja | Taip | tą patį masyvą |
| `reverse()` | apverčia tvarką | Taip | tą patį masyvą |
| `reduce()` | suveda į vieną rezultatą | Ne | vieną rezultatą |

---

# Greitas palyginimas

```text
map()     → transformuoja
forEach() → atlieka veiksmą
filter()  → atrenka
find()    → suranda pirmą
reduce()  → suveda į vieną rezultatą
sort()    → surikiuoja
slice()   → nukopijuoja
splice()  → pakeičia originalą
```

## Susiję užrašai

- [[10_FUNKCIJOS]]
- [[11_CIKLAI]]
- [[13_GREITA_ATMINTINE]]
- [[15_MANO_KLAIDOS]]
- [[18_NAUDINGI_WEB]]
