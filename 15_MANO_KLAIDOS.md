# 15 – Dažnos mano klaidos

Šitas failas skirtas ne teorijai, o klaidoms, kurios kartojasi.

## 1. Terminalas ne tame folderyje

Klaida:

```text
Cannot find module ...
```

Patikrink, kur esi:

```powershell
pwd
```

Pereik į tinkamą folderį:

```powershell
cd "C:\kelias\iki\projekto"
```

Tada:

```powershell
node string4.js
```

## 2. Failo pavadinimo typo

Pvz. failas:

```text
sting4.js
```

o terminale:

```powershell
node string4.js
```

Node ieško kito failo.

## 3. `console.log()` po `return`

Blogai:

```js
function test() {
    return 5;
    console.log("test");
}
```

Po `return` funkcija jau baigta.

## 4. Tas pats kintamasis deklaruotas du kartus

Blogai:

```js
function test(text) {
    let text = "Labas";
}
```

`text` jau egzistuoja kaip parametras.

## 5. Metodo typo

Blogai:

```js
toUoerCase()
```

Gerai:

```js
toUpperCase()
```

## 6. Pamirštas `return`

```js
function sum(a, b) {
    let result = a + b;
}
```

Funkcija suskaičiuoja, bet rezultato negrąžina.

Gerai:

```js
return result;
```

## 7. Indeksai prasideda nuo 0

```js
let text = "Hello";

text[0]; // H
text[1]; // e
```

## Mano taisyklė

Kai neveikia kodas – nepanikuoti ir patikrinti:

```text
1. failo vardas
2. terminalo folderis
3. skliaustai
4. kabutės
5. metodo pavadinimas
6. return
7. console.log testas
```
