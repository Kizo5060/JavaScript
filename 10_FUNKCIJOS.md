# Funkcijos

#js #funkcijos

## Kas yra funkcija?
Funkcija = kodo blokas, kurį galima iškviesti kada reikia.

Vieną kartą parašai → gali naudoti daug kartų.

## Function declaration

```js
function sayHello() {
    console.log("Labas");
}

sayHello();
```

## Parametrai

```js
function greet(name) {
    console.log(`Labas, ${name}`);
}

greet("Jonas");
```

`name` yra parametras.

## `return`
`return` grąžina rezultatą iš funkcijos.

```js
function sum(a, b) {
    return a + b;
}

let result = sum(5, 3);

console.log(result);
```

Rezultatas:

```text
8
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

Trumpai:

```js
const sum = (a, b) => a + b;
```

## Svarbiausia pradžioje
Tau dabar svarbiausia suprasti:
- funkcija pati nesuveikia, kol jos neiškvieti;
- parametrai leidžia perduoti duomenis;
- `return` grąžina rezultatą.

## Pažangesnės temos iš skaidrių
Skaidrėse dar yra:
- callback funkcijos;
- higher-order functions;
- asinchroniniai callback;
- recursive funkcijos;
- nested funkcijos.

Kol bazinės funkcijos neaiškios, šitų dar nereikia kalti.

Susiję:
- [[11_CIKLAI]]
- [[12_METODAI]]
