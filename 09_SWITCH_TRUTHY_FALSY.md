# 09 – `switch`, truthy ir falsy

## `switch`

Patogu, kai vieną reikšmę lyginame su daug konkrečių variantų.

```js
let day = 2;

switch (day) {
    case 1:
        console.log("Pirmadienis");
        break;
    case 2:
        console.log("Antradienis");
        break;
    default:
        console.log("Nežinoma diena");
}
```

### `break`

`break` sustabdo `switch`, kad programa neeitų į kitą `case`.

### `default`

Veikia kaip `else`.

## Truthy ir falsy

Kai JavaScript laukia `true/false`, kai kurios reikšmės automatiškai laikomos `false`.

Dažniausi **falsy**:

```js
0
""
null
undefined
NaN
false
```

Kitos reikšmės dažniausiai yra truthy.

Pvz.:

```js
let name = "";

if (name) {
    console.log("Vardas įvestas");
} else {
    console.log("Tuščia");
}
```

## Optional chaining `?.`

Padeda saugiai pasiekti gilesnę objekto reikšmę.

```js
let user = {};

console.log(user.address?.city);
```

Vietoj klaidos gausime:

```text
undefined
```

Beginner pradžioje svarbiausia suprasti:
- `switch` – daug konkrečių variantų;
- falsy – reikšmės, kurios sąlygoje elgiasi kaip `false`.

---

## Kada `switch`, kada `if`?

`switch` patogus, kai tikriname konkrečias reikšmes:

```js
switch (month) {
    case 0:
        return "Sausis";
    case 1:
        return "Vasaris";
}
```

`if` patogiau, kai tikriname intervalus:

```js
if (age >= 18) {
    ...
}
```

arba kelias sąlygas:

```js
if (age >= 18 && hasTicket) {
    ...
}
```

## Falsy praktiškai

Galima patikrinti, ar string tuščias:

```js
let text = "";

if (!text) {
    console.log("Tekstas tuščias");
}
```

Bet pradžioje, jei taip aiškiau, visiškai gerai rašyti:

```js
if (text === "") {
    console.log("Tekstas tuščias");
}
```

Aiškumas mokantis svarbiau už trumpiausią kodą.

