# 13 – Greita atmintinė

## Kintamieji

```js
let x = 5;
const name = "Jonas";
```

## Tipai

```js
typeof 5        // number
typeof "Labas"  // string
typeof true     // boolean
```

## Sąlyga

```js
if (x > 5) {

} else {

}
```

## Funkcija

```js
function sum(a, b) {
    return a + b;
}
```

## `for`

```js
for (let i = 0; i < 5; i++) {

}
```

## `for...of`

```js
for (let item of array) {

}
```

## Masyvas

```js
let arr = [1, 2, 3];

arr[0];
arr.length;
arr.push(4);
```

## Objektas

```js
let user = {
    name: "Jonas",
    age: 28
};

user.name;
```

## String

```js
text.length
text[0]
text.toUpperCase()
text.toLowerCase()
text.trim()
text.split(" ")
text.includes("abc")
text.replaceAll(" ", "")
```

## Dažna užduoties logika

### Skaičiuoti

```js
let count = 0;

for (let item of items) {
    if (/* sąlyga */) {
        count++;
    }
}

return count;
```

### Kaupti sumą

```js
let sum = 0;

for (let number of numbers) {
    sum += number;
}

return sum;
```

### Kurti naują masyvą

```js
let result = [];

for (let item of items) {
    if (/* sąlyga */) {
        result.push(item);
    }
}

return result;
```

### Kurti naują string

```js
let result = "";

for (let char of text) {
    result += char;
}

return result;
```
