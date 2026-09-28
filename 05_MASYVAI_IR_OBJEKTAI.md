# 05 – Masyvai ir objektai

## Masyvas (`Array`)

Masyvas leidžia viename kintamajame laikyti daug reikšmių.

```js
let cars = ["Saab", "Volvo", "BMW"];
```

Masyvo indeksai prasideda nuo `0`:

```text
Saab   Volvo   BMW
 0       1      2
```

```js
console.log(cars[0]); // Saab
```

Masyve gali būti ir skirtingų tipų reikšmių:

```js
let person = ["John", "Doe", 46];
```

## Objektas (`Object`)

Objektas saugo reikšmes `key: value` principu.

```js
let person = {
    firstName: "John",
    lastName: "Doe",
    age: 46
};
```

- `firstName` – key;
- `"John"` – value.

Reikšmę pasiekiame:

```js
console.log(person.firstName);
```

## Masyvas vs objektas

Masyvas:

```js
let colors = ["red", "green", "blue"];
```

Reikšmę randame pagal **indeksą**:

```js
colors[1];
```

Objektas:

```js
let user = {
    name: "Jonas",
    age: 28
};
```

Reikšmę randame pagal **rakto vardą**:

```js
user.name;
```

## Masyve gali būti objektai

```js
let users = [
    { name: "Jonas", age: 20 },
    { name: "Petras", age: 25 }
];

console.log(users[0].name);
```

Mąstymas:

```text
users[0]      → pirmas objektas
users[0].name → jo name reikšmė
```

---

## Masyvo ilgis

```js
let colors = ["red", "green", "blue"];

console.log(colors.length); // 3
```

Paskutinis indeksas visada:

```js
colors.length - 1
```

Todėl paskutinis elementas:

```js
colors[colors.length - 1];
```

## Elemento keitimas

Masyvo elementą galima pakeisti:

```js
let colors = ["red", "green"];

colors[0] = "blue";

console.log(colors);
```

## Objekto reikšmės keitimas

```js
let user = {
    name: "Jonas",
    age: 20
};

user.age = 21;
```

## Dot notation ir bracket notation

Dažniausiai:

```js
user.name
```

Bet galima ir:

```js
user["name"]
```

`for...in` cikle bracket notation labai naudinga:

```js
for (let key in user) {
    console.log(user[key]);
}
```

Nes `key` kiekvieną kartą yra kitas objekto rakto vardas.

