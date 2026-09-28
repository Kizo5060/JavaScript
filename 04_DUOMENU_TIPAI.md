# 04 – Duomenų tipai

JavaScript yra dinamiškai tipizuota kalba – kintamajam tipas nėra „prikalamas“ visam laikui.

```js
let value = 10;
value = "Labas";
```

## Pagrindiniai tipai

### Number

```js
let age = 28;
let price = 12.50;
```

Prie `number` temos sutinkame:
- `Infinity`
- `NaN` – „Not a Number“

```js
console.log("abc" * 2); // NaN
```

### String

Tekstas:

```js
let name = "Jonas";
let city = 'Vilnius';
let message = `Labas`;
```

### Boolean

Tik dvi reikšmės:

```js
true
false
```

### `null`

Specialiai priskirta „tuščia / nėra reikšmės“ reikšmė.

```js
let user = null;
```

### `undefined`

Kintamasis sukurtas, bet reikšmė nepriskirta.

```js
let result;
console.log(result); // undefined
```

### BigInt

Labai dideliems sveikiesiems skaičiams.

```js
let huge = 12345678901234567890n;
```

## `typeof`

Parodo reikšmės tipą:

```js
console.log(typeof 10);       // number
console.log(typeof "Labas");  // string
console.log(typeof true);     // boolean
```

Galimi abu variantai:

```js
typeof x;
typeof(x);
```

## Tipų keitimas

### Į Number

```js
Number("123");   // 123
parseInt("123"); // 123
```

`parseInt()` gali nuskaityti skaičių nuo string pradžios:

```js
parseInt("123px"); // 123
```

### Į String

```js
String(123); // "123"
```

### Į Boolean

```js
Boolean(1);  // true
Boolean(0);  // false
```

## Automatinis keitimas

```js
"6" / "2" // 3
```

Matematiniai operatoriai dažnai konvertuoja string į number.

Tačiau `+` gali jungti tekstą:

```js
"6" + "2" // "62"
```

Todėl su `+` reikia būti ypač atsargiam.
