# 22 pamoka – JavaScript objektai

> Šitas konspektas parašytas taip, kad objektų temą galėtų suprasti ir žmogus, kuris su JavaScript pradėjo nuo 0.

# 1. Kas yra objektas?

**Objektas (`object`)** – duomenų tipas, skirtas laikyti kelias susijusias reikšmes vienoje vietoje.

Paprasčiau:

```text
Objektas = vienas daiktas + visa informacija apie jį
```

Pvz. automobilis realiame gyvenime turi markę, modelį, spalvą ir metus.

JavaScript'e:

```js
const car = {
    brand: "BMW",
    model: "X5",
    color: "black",
    year: 2020
};
```

Čia:

```text
car      → visas objektas
brand    → savybės pavadinimas (key)
"BMW"    → savybės reikšmė (value)
```

---

# 2. Savybės ir metodai

Objektas gali turėti:

- **savybes (`properties`)** – informaciją apie objektą;
- **metodus (`methods`)** – veiksmus, kuriuos objektas gali atlikti.

```js
const car = {
    brand: "BMW",
    color: "black",

    drive: function() {
        return "Automobilis važiuoja";
    }
};
```

```text
brand → savybė
color → savybė
drive → metodas
```

Metodas iš esmės yra **funkcija objekto viduje**.

---

# 3. Objekto struktūra

```js
const user = {
    name: "Jonas",
    age: 25,
    city: "Vilnius"
};
```

Bendra forma:

```js
const objectName = {
    key: value,
    key: value
};
```

Svarbu:
- tarp savybių dedame kablelius;
- `key` ir `value` skiriami `:`;
- objektas rašomas tarp `{ }`.

---

# 4. Savybės paėmimas

```js
const user = {
    name: "Jonas",
    age: 25
};

console.log(user.name); // Jonas
console.log(user.age);  // 25
```

Galvok:

```text
user.name = iš objekto user paimk savybę name
```

---

# 5. Savybės paėmimas su `[]`

```js
console.log(user["name"]);
```

Tas pats kaip:

```js
console.log(user.name);
```

`[]` ypač naudinga, kai savybės vardas laikomas kintamajame:

```js
let propertyName = "name";

console.log(user[propertyName]);
```

Čia `propertyName` yra `"name"`, todėl gauname `user["name"]`.

---

# 6. Savybės keitimas

```js
const car = {
    brand: "Audi",
    year: 2000
};

car.brand = "Ford";
car.year = 2010;
```

Dabar:

```js
{
    brand: "Ford",
    year: 2010
}
```

## `const` ir objektai

Nors objektas sukurtas su `const`, jo savybes keisti galima:

```js
const user = {
    name: "Jonas"
};

user.name = "Petras";
```

Negalima perrašyti viso `user` kintamojo kitu objektu.

---

# 7. Naujos savybės pridėjimas

```js
const user = {
    name: "Jonas"
};

user.age = 25;
```

Dabar:

```js
{
    name: "Jonas",
    age: 25
}
```

---

# 8. Savybės ištrynimas

```js
delete user.age;
```

Trumpai:

```text
pridėti  → user.age = 25
keisti   → user.age = 30
ištrinti → delete user.age
```

---

# 9. Metodas objekte

```js
const user = {
    name: "Jonas",

    greet: function() {
        return "Labas!";
    }
};

console.log(user.greet());
```

Svarbu:

```text
user.name    → savybė
user.greet() → metodas
```

Metodas turi `()`, nes jis yra funkcija.

---

# 10. `this`

`this` metodo viduje rodo į objektą, kuris metodą iškvietė.

```js
const user = {
    name: "Jonas",

    greet: function() {
        return "Labas, mano vardas " + this.name;
    }
};

console.log(user.greet());
```

Rezultatas:

```text
Labas, mano vardas Jonas
```

Šitame pavyzdyje:

```text
this = user
this.name = user.name
```

Paprastai galvok:

```text
this = šitas objektas
```

---

# 11. Trumpesnė metodo sintaksė

Vietoj:

```js
const user = {
    greet: function() {
        return "Labas";
    }
};
```

galima:

```js
const user = {
    greet() {
        return "Labas";
    }
};
```

---

# 12. Objektas iš kintamųjų

```js
const userName = "John";
const age = 42;
const loggedIn = true;
```

Ilgesnis variantas:

```js
const user = {
    userName: userName,
    age: age,
    loggedIn: loggedIn
};
```

Trumpiau:

```js
const user = {
    userName,
    age,
    loggedIn
};
```

---

# 13. Kas yra klasė?

Skaidrėse klasė pateikiama kaip **ruošinys objektams kurti**.

```text
class = šablonas
object = konkretus pagal tą šabloną sukurtas daiktas
```

Pvz.:

```text
Klasė: Automobilis
Objektai: BMW, Audi, Ford
```

---

# 14. 4 objektų kūrimo būdai

Pagal skaidres:

```text
1. Object literal
2. new Object()
3. Constructor function
4. Class
```

Beginner lygyje svarbiausias:

```text
Object literal
```

---

# 15. Object literal

```js
const person = {
    firstName: "John",
    lastName: "Doe",
    age: 30
};
```

Tai paprasčiausias objektų kūrimo būdas.

---

# 16. `new Object()`

```js
const person = new Object();

person.firstName = "John";
person.lastName = "Doe";
person.age = 30;
```

Gauname tą patį, ką su object literal, tik daugiau rašymo.

---

# 17. Constructor function

Senesnis būdas kurti daug panašių objektų.

```js
function Person(firstName, lastName, age) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
}
```

Tada:

```js
const person1 = new Person("Jonas", "Jonaitis", 25);
const person2 = new Person("Petras", "Petraitis", 30);
```

Galvok:

```text
Person  → šablonas
person1 → konkretus objektas
person2 → kitas objektas
```

---

# 18. `class`

```js
class User {
    constructor(name) {
        this.name = name;
    }

    sayHi() {
        return "Labas, " + this.name;
    }
}

const user = new User("Jonas");

console.log(user.sayHi());
```

`constructor()` suveikia kuriant objektą su `new`.

```js
new User("Jonas")
```

`"Jonas"` nueina į:

```js
constructor(name)
```

---

# 19. Prototype – ką reikia suprasti pradžiai?

Objektai gali paveldėti savybes ir metodus per prototipus.

Beginner lygyje užtenka:

```text
Objektas gali turėti savo savybes,
bet dalį metodų gali gauti iš prototipo.
```

Konsolėje gali matytis:

```text
[[Prototype]]
```

ar senesniuose pavyzdžiuose:

```text
__proto__
```

Nebūtina iškart iškalti viso prototipų mechanizmo.

---

# 20. `Object.keys()`

Grąžina objekto **savybių pavadinimus** kaip masyvą.

```js
const user = {
    name: "Jonas",
    age: 25,
    city: "Vilnius"
};

console.log(Object.keys(user));
```

Rezultatas:

```js
["name", "age", "city"]
```

Objekto savybių kiekis:

```js
Object.keys(user).length
```

Rezultatas:

```text
3
```

---

# 21. `Object.values()`

Grąžina objekto reikšmes:

```js
console.log(Object.values(user));
```

Rezultatas:

```js
["Jonas", 25, "Vilnius"]
```

Atmintinė:

```text
Object.keys()   → key
Object.values() → value
```

---

# 22. `Object.keys()` su ciklu

```js
const keys = Object.keys(user);

for (let key of keys) {
    console.log(key);
}
```

Jei reikia ir reikšmės:

```js
for (let key of keys) {
    console.log(key, user[key]);
}
```

Čia `user[key]` labai svarbu, nes `key` yra kintamasis.

---

# 23. `for...in` su objektu

```js
const user = {
    name: "Jonas",
    age: 25
};

for (let key in user) {
    console.log(key);
}
```

Reikšmės:

```js
for (let key in user) {
    console.log(user[key]);
}
```

Visa informacija:

```js
for (let key in user) {
    console.log(key + ": " + user[key]);
}
```

---

# 24. `Object.assign()`

Skirtas objektų savybėms kopijuoti arba jungti.

```js
const name = {
    firstName: "Philip",
    lastName: "Fry"
};

const details = {
    job: "Delivery boy",
    employer: "Planet Express"
};

const character = Object.assign({}, name, details);

console.log(character);
```

Pirmas `{}` – naujas tuščias objektas, į kurį kopijuojamos savybės.

---

# 25. Spread `...` su objektais

```js
const circle = {
    radius: 10
};

const coloredCircle = {
    ...circle,
    color: "black"
};
```

Gauname:

```js
{
    radius: 10,
    color: "black"
}
```

Galvok:

```text
...circle = paimk visas circle savybes ir įdėk čia
```

---

# 26. Objektų sujungimas su spread

```js
const circle = {
    radius: 10
};

const style = {
    color: "red"
};

const result = {
    ...circle,
    ...style
};
```

Rezultatas:

```js
{
    radius: 10,
    color: "red"
}
```

Jeigu abi savybės vienodu vardu, vėliau parašyta reikšmė perrašo ankstesnę.

---

# 27. Spread perduodant funkcijai argumentus

```js
const numbers = [1, 3, 5, 7];

function addNumbers(a, b, c, d) {
    return a + b + c + d;
}

console.log(addNumbers(...numbers));
```

`...numbers` išskaido:

```text
[1, 3, 5, 7]
```

į:

```text
1, 3, 5, 7
```

---

# 28. Rest `...`

```js
function showNumbers(...numbers) {
    console.log(numbers);
}

showNumbers(1, 2, 3, 4);
```

Rezultatas:

```js
[1, 2, 3, 4]
```

Rest surenka daug argumentų į vieną masyvą.

Atmintinė:

```text
SPREAD → išskaido
REST   → surenka
```

---

# 29. `Object.create()`

Sukuria naują objektą, susietą su kitu objektu kaip prototipu.

```js
const worker = {
    type: "hourly",

    showType() {
        return this.type;
    }
};

const barista = Object.create(worker);

barista.position = "barista";
```

`barista` savo objekte turi `position`, bet gali pasiekti ir paveldėtą:

```js
barista.type
barista.showType()
```

---

# 30. Destruktūrizavimas

Turime:

```js
const user = {
    name: "Jonas",
    age: 25,
    city: "Vilnius"
};
```

Be destructuring:

```js
let name = user.name;
let age = user.age;
let city = user.city;
```

Su destructuring:

```js
let { name, age, city } = user;
```

Tai objekto savybių **išpakavimas į atskirus kintamuosius**.

Svarbu: vardai turi sutapti su objekto key.

---

# 31. Objektas vs masyvas

## Masyvas

```js
const fruits = ["apple", "banana", "orange"];
```

Pasiekiame pagal indeksą:

```js
fruits[0];
```

## Objektas

```js
const user = {
    name: "Jonas",
    age: 25
};
```

Pasiekiame pagal key:

```js
user.name;
```

Trumpai:

```text
Array  → indeksai 0, 1, 2...
Object → key: name, age, city...
```

---

# 32. Masyvas objektų

Labai dažnas realus variantas:

```js
const users = [
    { name: "Jonas", age: 25 },
    { name: "Petras", age: 30 }
];
```

Pirmas objektas:

```js
users[0]
```

Pirmo vartotojo vardas:

```js
users[0].name
```

Mąstymas:

```text
users         → visas masyvas
users[0]      → pirmas objektas
users[0].name → pirmo objekto name
```

---

# 33. Ciklas per masyvą objektų

```js
for (let user of users) {
    console.log(user.name);
}
```

Čia vienoje vietoje susijungia:

```text
masyvas + objektai + for...of
```

---

# 34. Dažniausios beginner klaidos

## Supainiojamas `:` ir `=`

Objekto kūrimo metu:

```js
const user = {
    name: "Jonas"
};
```

naudojame `:`.

Keičiant:

```js
user.name = "Petras";
```

naudojame `=`.

## Metodas be `()`

```js
user.greet
```

reiškia pačią funkciją.

```js
user.greet()
```

ją paleidžia.

## `user[key]` ir `user.key`

Jei:

```js
let key = "name";
```

reikia:

```js
user[key]
```

`user.key` ieškotų savybės tiesiog pavadintos `"key"`.

---

# 35. Tipinė beginner užduotis

> Sukurk student objektą su name, age ir course. Pakeisk course ir išvesk studento vardą.

```js
const student = {
    name: "Jonas",
    age: 25,
    course: "JavaScript"
};

student.course = "Java";

console.log(student.name);
```

Išskaidymas:

```text
sukurti objektą → { }
savybės         → key: value
keisti          → student.course = ...
paimti          → student.name
```

---

# 36. Dar viena tipinė užduotis

> Suskaičiuok, kiek savybių turi objektas.

```js
const car = {
    brand: "BMW",
    model: "X5",
    year: 2020
};

let count = Object.keys(car).length;

console.log(count); // 3
```

---

# 37. Greita objektų atmintinė

```js
const user = {
    name: "Jonas",
    age: 25
};
```

Paimti:

```js
user.name
user["name"]
```

Pakeisti:

```js
user.age = 30;
```

Pridėti:

```js
user.city = "Vilnius";
```

Ištrinti:

```js
delete user.age;
```

Key:

```js
Object.keys(user);
```

Values:

```js
Object.values(user);
```

Kopija su spread:

```js
const copy = { ...user };
```

Destructuring:

```js
const { name, age } = user;
```

---

# 38. Kas svarbiausia iš šitos temos?

Jei visa tema atrodo sunki, pirmiausia mokėk:

```text
1. Kas yra object
2. key ir value
3. user.name
4. user["name"]
5. pridėti / pakeisti / delete
6. metodas objekte
7. this
8. Object.keys()
9. Object.values()
10. spread {...obj}
11. destructuring
```

Antram etapui:

```text
constructor function
class
prototype
Object.create()
Object.assign()
rest / spread skirtumas
```

---

# 39. Mini žemėlapis

```text
OBJECT
│
├── Properties
│   ├── name
│   ├── age
│   └── city
│
├── Methods
│   └── greet()
│
├── Pasiekti
│   ├── user.name
│   └── user["name"]
│
├── Keisti
│   ├── user.age = 30
│   ├── user.city = "Vilnius"
│   └── delete user.age
│
├── Object metodai
│   ├── Object.keys()
│   ├── Object.values()
│   ├── Object.assign()
│   └── Object.create()
│
├── Spread / Rest
│   └── ...
│
├── Destructuring
│   └── const { name, age } = user
│
└── Kūrimui
    ├── object literal
    ├── new Object()
    ├── constructor function
    └── class
```

---

# 40. Kaip mokytis objektus

Nereikia visko kalti vienu metu.

Pirma:

```js
const user = {
    name: "Jonas",
    age: 25
};

console.log(user.name);

user.age = 30;
user.city = "Vilnius";

delete user.age;
```

Kai šitas tampa aišku, tada:

```js
Object.keys()
Object.values()
for...in
```

Po to:

```js
spread
destructuring
```

Ir tik tada giliau:

```js
class
prototype
Object.create()
```

Taip objektų tema daug lengviau susidėlioja.
