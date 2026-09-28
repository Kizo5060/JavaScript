# 21 pamoka – JavaScript Strings

String = tekstas.

```js
let text = "Labas";
```

## Nauja eilutė ir specialūs simboliai

```text
\n   nauja eilutė
\t   tab
\\   backslash
\'   vienguba kabutė
\"   dviguba kabutė
```

Pvz.:

```js
let text = "Labas\nPasauli";
```

## Escape

Jeigu string aprašytas viengubomis kabutėmis ir tekste reikia `'`:

```js
let text = 'I\'m here';
```

## Backticks

```js
let text = `Hello
World`;
```

Backticks leidžia tekstą rašyti per kelias eilutes.

Taip pat galima įterpti reikšmę:

```js
let name = "Jonas";

let text = `Labas, ${name}`;
```

## `.length`

```js
let text = "My name";

console.log(text.length); // 7
```

Tarpas irgi yra simbolis.

## Indeksai

```text
H e l l o
0 1 2 3 4
```

```js
let text = "Hello";

text[0]; // H
text[1]; // e
```

Paskutinis simbolis:

```js
text[text.length - 1];
```

## `charAt()`

```js
text.charAt(0);
```

Taip pat paima simbolį pagal indeksą.

## String yra immutable

Negalime tiesiog pakeisti vieno simbolio:

```js
let text = "Hi";

// text[0] = "h"; // taip neveikia kaip tikimės
```

Kuriame naują string:

```js
text = "h" + text[1];
```

# String metodai

## `concat()`

Sujungia:

```js
let a = "Hello";
let b = "world";

let result = a.concat(" ", b);
```

## `replace()`

Pakeičia pirmą atitikimą:

```js
"abc abc".replace("abc", "xyz");
```

## `replaceAll()`

Pakeičia visus:

```js
"abc abc".replaceAll("abc", "xyz");
```

Labai naudinga tarpams pašalinti:

```js
text.replaceAll(" ", "");
```

## `split()`

String → array.

```js
let text = "Hello world";

let words = text.split(" ");
```

Rezultatas:

```js
["Hello", "world"]
```

Simboliais:

```js
text.split("");
```

## `join()`

Array → string.

```js
let words = ["Hello", "world"];

words.join("-");
```

Rezultatas:

```text
Hello-world
```

## `substring()` ir `slice()`

Paima teksto dalį:

```js
let text = "JavaScript";

text.slice(0, 4); // Java
```

Galinis indeksas neįtraukiamas.

## `toLowerCase()`

```js
"LABAS".toLowerCase(); // labas
```

## `toUpperCase()`

```js
"labas".toUpperCase(); // LABAS
```

## `trim()`

Nuima tarpus nuo pradžios ir galo:

```js
"   Labas   ".trim();
```

## `includes()`

Patikrina, ar tekstas yra viduje:

```js
"JavaScript".includes("Script"); // true
```

Skiria didžiąsias ir mažąsias raides.

## `search()`

Grąžina pirmo atitikimo indeksą arba `-1`.

```js
"JavaScript".search("Script"); // 4
```

# Kaip spręsti string užduotis?

## 1. Pašalinti tarpus

```js
function removeBlanks(text) {
    return text.replaceAll(" ", "");
}
```

## 2. Eiti per kiekvieną simbolį

```js
for (let char of text) {
    console.log(char);
}
```

## 3. Kurti naują tekstą

```js
let result = "";

for (let char of text) {
    result += char;
}

return result;
```

## 4. Sakinį paversti žodžiais

```js
let words = text.split(" ");
```

Tada galima:

```js
for (let word of words) {
    console.log(word);
}
```

# Greita atmintinė

```text
.length         simbolių kiekis
[index]         simbolis pagal indeksą
charAt()        simbolis pagal indeksą
concat()        sujungia
replace()       pakeičia pirmą
replaceAll()    pakeičia visus
split()         string → array
join()          array → string
slice()         teksto dalis
substring()     teksto dalis
toLowerCase()   mažosios
toUpperCase()   didžiosios
trim()          nuima tarpus iš kraštų
includes()      true / false
search()        pirmo atitikimo indeksas
```
