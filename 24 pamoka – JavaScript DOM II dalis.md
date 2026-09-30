# 24 pamoka – JavaScript DOM (II dalis)

> Šitas konspektas išplėstas taip, kad būtų galima mokytis nuo nulio ir suprasti, kas vyksta su DOM elementais.
>
> <span style="color:red"><b>Raudonai pažymėtos vietos – tos, kurias verta ypač gerai suprasti prieš atsiskaitymą.</b></span>

---

# 1. DOM II dalies esmė

Pirmoje DOM dalyje daugiausia mokėmės:

```text
surasti elementą
keisti jo tekstą
keisti stilių
keisti klases
reaguoti į eventus
```

DOM II dalyje žengiam toliau:

```text
kurti naujus elementus
pridėti juos į puslapį
įterpti prieš kitą elementą
šalinti elementus
pakeisti vieną elementą kitu
naviguoti DOM medžiu
dirbti su formomis
```

<span style="color:red"><b>Svarbiausia mintis: JS gali ne tik pakeisti jau egzistuojantį HTML, bet ir pats kurti naują HTML struktūrą vykdymo metu.</b></span>

---

# 2. `createTextNode()`

Sukuria tekstinį DOM mazgą:

```js
const node = document.createTextNode("This is new.");
```

Svarbu:

```text
tekstas dar nėra matomas puslapyje
```

Jis tik sukurtas atmintyje.

---

# 3. `createElement()`

Sukuria naują HTML elementą:

```js
const para = document.createElement("p");
```

Tai sukuria:

```html
<p></p>
```

bet dar jo neįdeda į puslapį.

Kiti pavyzdžiai:

```js
document.createElement("div");
document.createElement("button");
document.createElement("li");
document.createElement("span");
```

<span style="color:red"><b>`createElement()` sukuria elementą, bet jo automatiškai neįdeda į puslapį.</b></span>

---

# 4. `appendChild()`

Turime:

```js
const para = document.createElement("p");
const node = document.createTextNode("This is new.");
```

Sujungiame:

```js
para.appendChild(node);
```

Gauname:

```html
<p>This is new.</p>
```

Bendra schema:

```js
parent.appendChild(child);
```

Tai reiškia:

```text
parent = į kur dedu
child = ką dedu
```

<span style="color:red"><b>`parent.appendChild(child)` – tėvas gauna vaiką.</b></span>

---

# 5. Pilnas elemento sukūrimas

```js
const para = document.createElement("p");
const node = document.createTextNode("This is new.");

para.appendChild(node);

const element = document.getElementById("div1");

element.appendChild(para);
```

Žingsniai:

```text
1. Sukuriu <p>
2. Sukuriu tekstą
3. Tekstą įdedu į <p>
4. Randu div1
5. <p> įdedu į div1
```

Tik po paskutinio žingsnio elementas tampa matomas puslapyje.

<span style="color:red"><b>Sukurti ≠ parodyti. Parodytas bus tik prijungus prie DOM.</b></span>

---

# 6. `insertBefore()`

Jei reikia įterpti naują elementą ne į pabaigą, o prieš kitą:

```js
parent.insertBefore(newElement, existingElement);
```

Pvz.:

```js
element.insertBefore(para, child);
```

reiškia:

```text
element = parent
para = naujas elementas
child = prieš kurį įterpiam
```

---

# 7. `insertBefore()` pavyzdys

HTML:

```html
<div id="div1">
    <p id="p1">Pirmas</p>
    <p id="p2">Antras</p>
</div>
```

JS:

```js
const para = document.createElement("p");
const node = document.createTextNode("Naujas");

para.appendChild(node);

const parent = document.getElementById("div1");
const child = document.getElementById("p1");

parent.insertBefore(para, child);
```

Rezultatas:

```html
<div id="div1">
    <p>Naujas</p>
    <p id="p1">Pirmas</p>
    <p id="p2">Antras</p>
</div>
```

---

# 8. `remove()`

Pašalina konkretų elementą iš DOM:

```js
const element = document.getElementById("p1");

element.remove();
```

<span style="color:red"><b>`remove()` pašalina patį elementą iš DOM.</b></span>

---

# 9. `replaceChild()`

Pakeičia seną elementą nauju:

```js
parent.replaceChild(newChild, oldChild);
```

Svarbu eiliškumas:

```text
newChild = kuo keičiam
oldChild = ką keičiam
```

<span style="color:red"><b>`replaceChild(new, old)` – NAUJAS, SENAS.</b></span>

---

# 10. Pilnas `replaceChild()` pavyzdys

```js
const parent = document.getElementById("div1");
const child = document.getElementById("p1");

const para = document.createElement("p");
const node = document.createTextNode("This is new.");

para.appendChild(node);

parent.replaceChild(para, child);
```

Kas įvyko:

```text
suradom parent
suradom seną elementą
sukūrėm naują
įdėjom tekstą
pakeitėm seną nauju
```

---

# 11. Kombinuotas DOM pavyzdys

HTML:

```html
<div id="container"></div>
```

JS:

```js
const container = document.querySelector("#container");

const content = document.createElement("div");

content.classList.add("content");

content.textContent = "This is the glorious text-content!";

container.appendChild(content);
```

Čia susijungia:

```text
querySelector
createElement
classList.add
textContent
appendChild
```

---

# 12. Kaip skaityti tą kodą

```js
const container = document.querySelector("#container");
```

→ surandam elementą.

```js
const content = document.createElement("div");
```

→ sukuriam naują div.

```js
content.classList.add("content");
```

→ pridedam klasę.

```js
content.textContent = "Tekstas";
```

→ įrašom tekstą.

```js
container.appendChild(content);
```

→ prijungiam naują div prie DOM.

---

# 13. Navigavimas DOM medžiu

DOM yra medis.

Elementai turi ryšius:

```text
parent
child
sibling
```

Pvz.:

```html
<ul>
    <li>Pirmas</li>
    <li>Antras</li>
    <li>Trečias</li>
</ul>
```

Čia:

```text
ul = parent
li = children
li šalia li = siblings
```

---

# 14. `parentNode`

```js
element.parentNode
```

grąžina tėvinį mazgą.

Jei `li` yra `ul` viduje:

```text
parentNode = ul
```

---

# 15. `childNodes`

```js
element.childNodes
```

grąžina visus vaikinius mazgus, įskaitant:

```text
HTML elementus
text nodes
tarpus
Enter
komentarus
```

Todėl kartais gaunam `#text`.

---

# 16. `children`

Kai reikia tik HTML elementų:

```js
element.children
```

Tai patogiau, nes ignoruojami whitespace text nodes.

---

# 17. `firstChild` ir `lastChild`

```js
element.firstChild
element.lastChild
```

ima pirmą ir paskutinį DOM mazgą.

Bet tai gali būti ir text node.

---

# 18. `previousSibling` ir `nextSibling`

```js
element.previousSibling
element.nextSibling
```

naviguoja tarp DOM mazgų.

Bet gali grąžinti:

```text
#text
```

jei tarp elementų yra tarpai ar Enter.

---

# 19. `previousElementSibling` ir `nextElementSibling`

Kai reikia tik HTML elementų:

```js
element.previousElementSibling
element.nextElementSibling
```

<span style="color:red"><b>Jei reikia tik HTML elementų, dažnai saugiau naudoti `previousElementSibling` / `nextElementSibling`.</b></span>

---

# 20. `nodeName`

```js
element.nodeName
```

grąžina mazgo vardą kaip string.

Pvz.:

```text
H1
P
DIV
#text
```

`nodeName` yra read-only.

---

# 21. Kodėl `previousSibling` gali būti `#text`?

HTML:

```html
<div>
    <h1 id="title">Heading</h1>
</div>
```

Tarp `<div>` ir `<h1>` yra Enter ir tarpai.

DOM tai gali laikyti text node.

Todėl:

```js
title.previousSibling.nodeName
```

gali grąžinti:

```text
#text
```

Tai normalu.

---

# 22. Mini DOM medžio logika

```text
BODY
│
├── DIV
│   ├── H1
│   ├── P
│   └── BUTTON
│
└── FOOTER
```

Jei esam ties `P`:

```text
parentNode → DIV
previousElementSibling → H1
nextElementSibling → BUTTON
```

---

# 23. Darbas su formomis

HTML:

```html
<form id="signup">
    <input name="name">
    <input name="email">
    <button type="submit">Send</button>
</form>
```

JS:

```js
const form = document.getElementById("signup");
```

---

# 24. `submit` eventas

Forma pagal nutylėjimą daro:

```text
submit
↓
siunčia formą
↓
puslapis gali persikrauti
```

Jei norime sustabdyti automatinį veiksmą:

```js
form.addEventListener("submit", function(event) {
    event.preventDefault();
});
```

<span style="color:red"><b>`event.preventDefault()` sustabdo numatytą formos submit veiksmą.</b></span>

---

# 25. Kodėl `preventDefault()` svarbus?

Jis reikalingas, kai norime:

```text
patikrinti laukus
rodyti klaidas
surinkti duomenis su JS
siųsti duomenis kitu būdu
```

---

# 26. Formos laukų pasiekimas

Per formą:

```js
form.elements[1]
```

pagal indeksą.

Arba:

```js
form.elements["email"]
```

pagal `name`.

---

# 27. `.value`

Jei turime:

```html
<input id="age" type="text">
```

JS:

```js
const age = document.getElementById("age").value;
```

Tai paima žmogaus įvestą reikšmę.

<span style="color:red"><b>Elementas ir jo `.value` nėra tas pats.</b></span>

Pvz.:

```js
const input = document.getElementById("age");
```

→ pats input elementas.

```js
const value = input.value;
```

→ jo reikšmė.

---

# 28. Formos reikšmių pavyzdys

```js
const form = document.getElementById("signup");

const name = form.elements["name"];
const email = form.elements["email"];

const fullName = name.value;
const emailAddress = email.value;
```

---

# 29. DOM II loginė schema

## Kūrimas

```text
createElement
↓
createTextNode / textContent
↓
appendChild
```

## Įterpimas

```text
insertBefore
```

## Šalinimas

```text
remove
```

## Pakeitimas

```text
replaceChild
```

## Navigacija

```text
parentNode
childNodes
firstChild
lastChild
previousSibling
nextSibling
```

## Formos

```text
submit
preventDefault
elements
value
```

---

# 30. Dažniausios beginner klaidos

## 1. Sukuria elementą, bet neprideda į DOM

```js
const p = document.createElement("p");
```

ir tikisi, kad jis bus matomas.

Reikia:

```js
parent.appendChild(p);
```

## 2. Supainiojamas parent ir child

Atmintinė:

```text
PARENT gauna CHILD
```

## 3. Sumaišomi `replaceChild()` argumentai

Teisingai:

```js
parent.replaceChild(newChild, oldChild);
```

## 4. `previousSibling` grąžina `#text`

Tai ne klaida.

## 5. Pamirštamas `preventDefault()`

Tada forma gali persikrauti.

## 6. Paimamas input, bet ne jo reikšmė

```js
input.value
```

---

# 31. Greita atmintinė

```js
const p = document.createElement("p");
```

```js
const text = document.createTextNode("Labas");
```

```js
p.appendChild(text);
```

```js
container.appendChild(p);
```

```js
parent.insertBefore(newElement, oldElement);
```

```js
element.remove();
```

```js
parent.replaceChild(newElement, oldElement);
```

```js
element.parentNode
```

```js
element.previousSibling
element.nextSibling
```

```js
element.previousElementSibling
element.nextElementSibling
```

```js
form.addEventListener("submit", function(event) {
    event.preventDefault();
});
```

```js
input.value
```

---

# 32. Vienas pilnas praktinis pavyzdys

HTML:

```html
<form id="task-form">
    <input id="task-input" type="text">
    <button type="submit">Add</button>
</form>

<ul id="task-list"></ul>
```

JS:

```js
const form = document.getElementById("task-form");
const input = document.getElementById("task-input");
const list = document.getElementById("task-list");

form.addEventListener("submit", function(event) {
    event.preventDefault();

    const li = document.createElement("li");

    li.textContent = input.value;

    list.appendChild(li);

    input.value = "";
});
```

Čia susijungia:

```text
form
submit
preventDefault
value
createElement
textContent
appendChild
```

---

# 33. Kaip skaityti tą pavyzdį

```js
const form = document.getElementById("task-form");
```

→ randu formą.

```js
const input = document.getElementById("task-input");
```

→ randu input.

```js
const list = document.getElementById("task-list");
```

→ randu sąrašą.

```js
form.addEventListener("submit", function(event) {
```

→ klausau submit.

```js
event.preventDefault();
```

→ neleidžiu puslapiui persikrauti.

```js
const li = document.createElement("li");
```

→ sukuriu naują `li`.

```js
li.textContent = input.value;
```

→ įdedu žmogaus įvestą tekstą.

```js
list.appendChild(li);
```

→ įdedu `li` į sąrašą.

```js
input.value = "";
```

→ išvalau input.

---

# 34. Ką verta mokėti atsiskaitymui

<span style="color:red"><b>1. `document.createElement()` – sukuria naują HTML elementą.</b></span>

<span style="color:red"><b>2. `appendChild()` – prijungia elementą prie DOM.</b></span>

<span style="color:red"><b>3. `insertBefore()` – įterpia prieš konkretų elementą.</b></span>

<span style="color:red"><b>4. `remove()` – pašalina elementą.</b></span>

<span style="color:red"><b>5. `replaceChild(new, old)` – pakeičia seną elementą nauju.</b></span>

<span style="color:red"><b>6. `parentNode`, `previousSibling`, `nextSibling` – navigacija DOM medžiu.</b></span>

<span style="color:red"><b>7. `event.preventDefault()` – stabdo standartinį formos submit veiksmą.</b></span>

<span style="color:red"><b>8. `input.value` – paima įvestą reikšmę.</b></span>

---

# 35. Mini DOM II žemėlapis

```text
DOM II
│
├── Kūrimas
│   ├── createElement
│   ├── createTextNode
│   └── textContent
│
├── Įdėjimas
│   ├── appendChild
│   └── insertBefore
│
├── Šalinimas
│   └── remove
│
├── Pakeitimas
│   └── replaceChild
│
├── Navigacija
│   ├── parentNode
│   ├── childNodes
│   ├── firstChild
│   ├── lastChild
│   ├── previousSibling
│   ├── nextSibling
│   ├── previousElementSibling
│   └── nextElementSibling
│
└── Formos
    ├── submit
    ├── preventDefault
    ├── form.elements
    └── value
```

---

# 36. Svarbiausia mintis

DOM II dalis moko:

```text
JavaScript gali pats konstruoti puslapį
↓
sukurti elementą
↓
įdėti jį
↓
pakeisti
↓
pašalinti
↓
naviguoti tarp elementų
↓
dirbti su formų duomenimis
```

<span style="color:red"><b>Jei supranti `createElement → textContent → appendChild`, jau turi vieną svarbiausių DOM II pagrindų.</b></span>
