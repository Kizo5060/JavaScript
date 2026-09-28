# 16 – JavaScript žemėlapis

```text
JavaScript
│
├── Kintamieji
│   ├── let
│   ├── const
│   └── var
│
├── Duomenų tipai
│   ├── number
│   ├── string
│   ├── boolean
│   ├── null
│   ├── undefined
│   ├── array
│   └── object
│
├── Operatoriai
│   ├── + - * / %
│   ├── === !==
│   ├── > < >= <=
│   └── && || !
│
├── Sąlygos
│   ├── if
│   ├── else if
│   ├── else
│   └── switch
│
├── Funkcijos
│   ├── parameters
│   ├── arguments
│   ├── return
│   ├── arrow
│   └── callback
│
├── Ciklai
│   ├── for
│   ├── while
│   ├── do...while
│   ├── for...of
│   └── for...in
│
├── Masyvai
│   ├── index
│   ├── length
│   ├── push/pop
│   ├── shift/unshift
│   ├── slice/splice
│   ├── map/filter/find
│   ├── sort
│   └── reduce
│
├── Datos
│   ├── new Date()
│   ├── timestamp
│   ├── get...
│   └── set...
│
└── Strings
    ├── length
    ├── index
    ├── split/join
    ├── slice/substring
    ├── replace
    ├── includes
    └── upper/lower case
```

## Kaip viskas susijungia užduotyse

Dažnas taskas:

```text
FUNKCIJA
   ↓
gauna MASYVĄ arba STRING
   ↓
CIKLAS pereina per reikšmes
   ↓
IF patikrina sąlygą
   ↓
kaupiamas rezultatas
   ↓
RETURN grąžina rezultatą
```

Pvz.:

```js
function getLongWords(words) {
    let result = [];

    for (let word of words) {
        if (word.length >= 5) {
            result.push(word);
        }
    }

    return result;
}
```

Čia vienoje užduotyje yra:
- funkcija;
- masyvas;
- ciklas;
- `if`;
- string `.length`;
- `push()`;
- `return`.
