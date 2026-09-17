# IF / ELSE

#js #if #salygos

## Kas tai?
`if` = **jeigu**.

```js
if (salyga) {
    // vykdyk šitą kodą
}
```

## `if / else`

```js
let age = 16;

if (age >= 18) {
    console.log("Galima vairuoti");
} else {
    console.log("Negalima vairuoti");
}
```

Programa tikrina:

```text
16 >= 18 → false
```

Todėl vykdo `else`.

## `else if`

```js
let age = 15;

if (age < 13) {
    console.log("Vaikas");
} else if (age < 18) {
    console.log("Paauglys");
} else {
    console.log("Suaugęs");
}
```

Programa tikrina sąlygas iš viršaus į apačią.

## Kaip galvoti
1. Ką tikrinu?
2. Kokia sąlyga?
3. Ką daryti jei `true`?
4. Ką daryti jei `false`?

## Mini užduotis sau

```js
let temperature = 25;
```

Padaryk:
- `>= 20` → `"Šilta"`
- kitu atveju → `"Šalta"`

Susiję:
- [[06_OPERATORIAI]]
- [[09_SWITCH_TRUTHY_FALSY]]
