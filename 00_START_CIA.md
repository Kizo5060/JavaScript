# START ČIA – JavaScript nuo nulio

Šis aplankas skirtas žmogui, kuris pradeda beveik nuo 0.

## Kaip mokytis

Nereikia bandyti iškalti viso JavaScript. Svarbiau suprasti pasikartojančią logiką:

1. **Ką gaunu?** – skaičių, tekstą, masyvą?
2. **Ką turiu padaryti?** – patikrinti, suskaičiuoti, pakeisti, atrinkti?
3. **Ką turiu grąžinti?** – skaičių, tekstą, `true/false`, masyvą?
4. Ar reikia:
   - `if` – kai yra sąlyga;
   - ciklo – kai veiksmą kartojame;
   - funkcijos – kai norime kodą panaudoti dar kartą;
   - masyvo metodo – kai dirbame su daug reikšmių.

## Minimalus darbo šablonas

```js
"use strict";

function task(value) {
    let result = value;

    return result;
}

console.log(task("test"));
```

## Kaip paleisti `.js` failą

Terminalas turi būti tame pačiame kataloge kaip failas.

```powershell
node task1.js
```

Jei matai:

```text
Cannot find module ...
```

dažniausiai esi ne tame folderyje arba neteisingai parašei failo vardą.

## Svarbiausia pradžiai

- `let` – reikšmę galime pakeisti.
- `const` – kintamojo negalime perrašyti.
- `if` – sprendimas pagal sąlygą.
- `function` – pakartotinai naudojamas kodo blokas.
- `return` – funkcijos rezultatas.
- `for` / `for...of` – kartojimas.
- `[]` – masyvas.
- `{}` – objektas.
- `"tekstas"` – string.
- `123` – number.
- `true / false` – boolean.

> Jei užduoties tekstas atrodo per sudėtingas, pirmiausia persakyk jį savo žodžiais.
