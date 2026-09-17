# Switch, truthy ir falsy

#js #switch #truthy #falsy

## `switch`
Naudingas, kai vieną reikšmę lygini su keliais konkrečiais variantais.

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

## `break`
Sustabdo `switch`, kad jis neitų toliau per kitus `case`.

## `default`
Veikia tada, kai netiko nė vienas `case`.

## Falsy
Šios reikšmės sąlygoje tampa `false`:
- `0`
- `""`
- `null`
- `undefined`
- `NaN`

## Truthy
Kitos reikšmės paprastai laikomos `true`.

Pavyzdys:

```js
let name = "";

if (name) {
    console.log("Vardas įvestas");
} else {
    console.log("Vardas tuščias");
}
```

## Optional chaining
Skaidrėse ši tema paminėta, bet jos paaiškinimas nėra pilnai pateiktas ištrauktame tekste. Kol kas užtenka žinoti, kad tai susiję su saugesniu objektų reikšmių pasiekimu.

Susiję:
- [[08_IF_ELSE]]
- [[05_MASYVAI_IR_OBJEKTAI]]
