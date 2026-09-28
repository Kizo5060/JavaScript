# 10 – Funkcijos

## Kas yra funkcija?

Funkcija – kodo blokas, kuris suveikia tik tada, kai jį iškviečiame.

```js
function sayHello() {
    console.log("Labas");
}

sayHello();
```

Kodėl jos naudingos?

> Tą patį kodą parašome vieną kartą, o vykdyti galime daug kartų.

## Parametrai

```js
function greet(name) {
    console.log("Labas " + name);
}

greet("Jonas");
greet("Petras");
```

`name` – parametras.

`"Jonas"` – argumentas, kurį perduodame iškvietimo metu.

## `return`

`return` grąžina funkcijos rezultatą.

```js
function sum(a, b) {
    return a + b;
}

let result = sum(5, 3);

console.log(result); // 8
```

Svarbu:

```js
console.log()
```

tik parodo reikšmę.

```js
return
```

grąžina reikšmę iš funkcijos.

## Function declaration

```js
function sum(a, b) {
    return a + b;
}
```

## Function expression

```js
const sum = function(a, b) {
    return a + b;
};
```

## Arrow function

```js
const sum = (a, b) => {
    return a + b;
};
```

Trumpas variantas:

```js
const sum = (a, b) => a + b;
```

## Callback

Callback – funkcija, perduodama kitai funkcijai.

```js
let numbers = [1, 2, 3, 4];

let even = numbers.filter(function(number) {
    return number % 2 === 0;
});
```

`filter()` gauna funkciją, kuri nusprendžia, kas tinka.

## Metodas ir funkcija

Funkcija:

```js
sum(2, 3);
```

Metodas kviečiamas su tašku:

```js
text.toUpperCase();
```

## Kaip pradėti funkcijos užduotį?

Jei užduotis sako:

> Sukurk funkciją, kuri gauna tekstą ir grąžina jo ilgį.

Pradžia:

```js
function getLength(text) {

}
```

Tada klausi:
1. ką gaunu? → `text`
2. ko reikia? → ilgio
3. kuo randamas ilgis? → `.length`
4. ką grąžinti? → `return`
