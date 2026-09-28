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
