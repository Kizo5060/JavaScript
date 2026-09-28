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

---

## Funkcija eilutė po eilutės

```js
function multiply(a, b) {
    let result = a * b;

    return result;
}

console.log(multiply(4, 5));
```

Kas vyksta:

```text
function multiply(a, b)
→ sukuriame funkciją, kuri laukia 2 reikšmių

multiply(4, 5)
→ a gauna 4
→ b gauna 5

let result = a * b
→ result tampa 20

return result
→ funkcija grąžina 20

console.log(...)
→ parodo 20 terminale
```

## Parametras ir argumentas

```js
function greet(name) {
```

`name` yra **parametras**.

```js
greet("Jonas");
```

`"Jonas"` yra **argumentas**.

## Keli `return`

```js
function checkNumber(number) {
    if (number > 0) {
        return "Teigiamas";
    }

    if (number < 0) {
        return "Neigiamas";
    }

    return "Nulis";
}
```

Vos tik vienas `return` suveikia, funkcija baigiasi.

## Callback paprastai

Turime:

```js
let numbers = [1, 2, 3, 4];
```

Ir:

```js
numbers.filter(number => number % 2 === 0);
```

Funkcija:

```js
number => number % 2 === 0
```

yra perduodama į `filter()`.

Tai ir yra callback idėja:
> viena funkcija paduodama kitai funkcijai.

Pradžioje nereikia callback iškalti teoriškai – svarbiau atpažinti jį `map`, `filter`, `find`, `sort`, `forEach`, `reduce` metoduose.

## Higher-order function

Kurso skaidrėse `filter()` pateikiamas kaip higher-order function, nes jis priima kitą funkciją.

Pvz.:

```js
let even = numbers.filter(number => number % 2 === 0);
```

## Nested funkcija

Funkcija gali būti kitos funkcijos viduje:

```js
function outer() {
    let name = "Jonas";

    function inner() {
        console.log(name);
    }

    inner();
}
```

Vidinė funkcija gali matyti išorinės funkcijos kintamuosius.

