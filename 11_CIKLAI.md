# Ciklai

#js #ciklai

## Kas yra ciklas?
Ciklas = kartoti kodą kelis kartus.

## `for`
Naudok, kai žinai, kiek kartų reikia kartoti.

```js
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

Kaip skaityti:

```text
let i = 1   → pradedam nuo 1
i <= 5      → kartojam kol i yra 5 arba mažiau
i++         → po kiekvieno karto +1
```

Rezultatas:

```text
1
2
3
4
5
```

## `while`
Naudok, kai nežinai tikslaus kartų skaičiaus.

```js
let x = 1;

while (x <= 5) {
    console.log(x);
    x++;
}
```

## `do...while`
Kodas įvykdomas bent vieną kartą.

```js
let x = 1;

do {
    console.log(x);
    x++;
} while (x <= 5);
```

## `for...of`
Skirtas eiti per masyvo elementus.

```js
let fruits = ["obuolys", "bananas", "kriaušė"];

for (let fruit of fruits) {
    console.log(fruit);
}
```

## `for...in`
Skirtas eiti per objekto `key`.

```js
let person = {
    name: "Jonas",
    age: 20
};

for (let key in person) {
    console.log(key, person[key]);
}
```

## `break`
Visiškai nutraukia ciklą.

```js
for (let i = 1; i <= 10; i++) {
    if (i === 5) {
        break;
    }

    console.log(i);
}
```

## `continue`
Praleidžia vieną ciklo kartą.

```js
for (let i = 1; i <= 5; i++) {
    if (i === 3) {
        continue;
    }

    console.log(i);
}
```

## Paprasta atmintinė
- `for` → žinau kiek kartų;
- `while` → nežinau kiek kartų;
- `do...while` → bent 1 kartą;
- `for...of` → masyvo reikšmės;
- `for...in` → objekto key.

Susiję:
- [[05_MASYVAI_IR_OBJEKTAI]]
- [[06_OPERATORIAI]]
- [[08_IF_ELSE]]
