# 01 – JavaScript įvadas

## Kas yra JavaScript?

JavaScript yra programavimo kalba, kuri leidžia puslapiui ar programai **reaguoti į veiksmus**.

Paprasta schema:

```text
VARTOTOJAS → VEIKSMAS → PROGRAMOS REAKCIJA
```

Pvz.:
- paspaudi mygtuką → atsiranda pranešimas;
- paspaudi „Patinka“ → skaičius padidėja;
- įdedi prekę į krepšelį → krepšelis atsinaujina;
- įvedi slaptažodį → programa tikrina jo stiprumą.

JavaScript naudojamas tiek **frontend**, tiek **backend** pusėje.

## JavaScript nėra Java

Tai dvi skirtingos programavimo kalbos.

## ECMAScript

Paprastai:
- **ECMAScript** – kalbos taisyklės / standartas;
- **JavaScript** – kalba, kuri tas taisykles įgyvendina.

## Kur JavaScript vykdomas?

### Naršyklėje

Naršyklės JavaScript gali:
- keisti HTML;
- keisti CSS;
- reaguoti į pelę ir klaviatūrą;
- siųsti užklausas serveriui;
- dirbti su `localStorage`, cookies ir kt.

### Node.js aplinkoje

Node.js leidžia JavaScript kodą vykdyti be naršyklės.

```js
console.log("Hello World!");
```

Terminale:

```powershell
node task1.js
```

## Browser ir Node nėra tas pats

Naršyklėje galime naudoti tokius dalykus kaip:

```js
document
alert()
```

Node aplinkoje jų paprastai nėra.

O paprastas JavaScript:

```js
let x = 5;
console.log(x);
```

veikia abiejose aplinkose.

## JavaScript prijungimas prie HTML

```html
<script src="script.js"></script>
```

Dažnai `<script>` dedamas prieš `</body>` arba naudojamas `defer`:

```html
<script src="script.js" defer></script>
```

`defer` leidžia pirma užkrauti HTML, o tada vykdyti JavaScript.

## Ką prisiminti

> JavaScript = logika ir elgesys.  
> HTML = struktūra.  
> CSS = išvaizda.
