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

---

## Kaip suprasti metodo iškvietimą

Pvz.:

```js
text.toUpperCase()
```

Galima skaityti:

> paimk `text` ir jam pritaikyk `toUpperCase()`.

Pvz.:

```js
numbers.push(5)
```

> paimk `numbers` masyvą ir pridėk į jo galą `5`.

## Metodas gali turėti argumentus

```js
text.includes("Java")
```

Čia `"Java"` perduodamas metodui kaip argumentas.

```js
array.slice(1, 3)
```

Čia metodui perduodami du argumentai:
- `1` – pradžia;
- `3` – pabaiga.

## Metodų grandinė

Galima jungti kelis metodus:

```js
let result = "  LABAS  "
    .trim()
    .toLowerCase();

console.log(result); // labas
```

Skaitome iš viršaus į apačią:

```text
"  LABAS  "
↓ trim()
"LABAS"
↓ toLowerCase()
"labas"
```

Tokios grandinės dažnai pasitaiko string užduotyse.

