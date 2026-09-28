# 12 – Metodai

Metodas – funkcija, susieta su konkrečiu objektu ar duomenų tipu.

Atpažinsi pagal tašką:

```js
text.toUpperCase();
array.push("x");
```

## String metodų pavyzdžiai

```js
let text = " Labas ";
```

```js
text.trim();        // "Labas"
text.toUpperCase(); // " LABAS "
text.toLowerCase(); // " labas "
```

## Array metodų pavyzdžiai

```js
let numbers = [1, 2, 3];
```

```js
numbers.push(4);
numbers.pop();
numbers.shift();
numbers.unshift(0);
```

## Metodas gali grąžinti naują reikšmę

```js
let text = "labas";

let upper = text.toUpperCase();

console.log(upper); // LABAS
```

Originalus string lieka tas pats, nes string yra immutable.

## Metodas gali keisti originalą

Kai kurie masyvų metodai, pvz.:

```js
push()
pop()
shift()
unshift()
splice()
sort()
```

gali pakeisti patį masyvą.

## Metodas gali sukurti naują masyvą

Pvz.:

```js
slice()
map()
filter()
concat()
```

Dažnai grąžina naują masyvą.

## Kodėl tai svarbu?

Užduotyje dažnai nereikia „išrasti algoritmo nuo nulio“ – reikia atpažinti tinkamą metodą.

Pvz.:

```text
„pašalink tarpus nuo pradžios ir galo“ → trim()
„padalink sakinį į žodžius“ → split(" ")
„patikrink ar yra žodis“ → includes()
```
