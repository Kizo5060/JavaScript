# 23 pamoka – JavaScript DOM (I dalis)

> Šitas konspektas išplėstas taip, kad DOM temą būtų lengviau suprasti ir tiems, kurie pradėjo nuo 0.  
> <span style="color:red"><b>Raudonai pažymėtos vietos – tos, kurias verta ypač gerai suprasti ir atsiminti.</b></span>

---

# 1. Kas yra DOM?

**DOM** reiškia **Document Object Model**. Tai būdas JavaScript pasiekti HTML elementus, keisti puslapio turinį ir stilių bei reaguoti į vartotojo veiksmus. 

```text
HTML → naršyklė → DOM → JavaScript gali keisti DOM
```

Pvz. HTML:

```html
<h1 id="title">Labas</h1>
```

JavaScript:

```js
const title = document.getElementById("title");
title.textContent = "Sveiki!";
```

<span style="color:red"><b>Svarbiausia mintis:</b> HTML aprašo puslapio struktūrą, o DOM leidžia JavaScript su ta struktūra dirbti.</span>

---

# 2. HTML ir DOM nėra tas pats

HTML yra pradinis dokumento kodas. Naršyklė iš jo sukuria **DOM medį**.

```text
document
└── html
    ├── head
    └── body
        ├── h1
        │   └── "Labas"
        └── p
            └── "Tekstas"
```

HTML elementai DOM'e tampa **mazgais (nodes)**.

<span style="color:red"><b>DOM nėra tiesiog pats HTML tekstas. Tai naršyklės atmintyje sukurta dokumento struktūra.</b></span>

---

# 3. `window` ir `document`

Kai JavaScript veikia naršyklėje, aukščiausiame lygyje yra `window`.

```text
window
├── document
├── navigator
├── screen
├── location
├── history
└── ...
```

DOM temoje svarbiausias yra:

```js
document
```

`document` reiškia atidarytą HTML dokumentą.

<span style="color:red"><b>DOM užduotyse labai dažnai viskas prasideda nuo `document`.</b></span>

---

# 4. DOM mazgai

Dažniausiai dirbame su:

```text
document
HTML elementais (element nodes)
tekstu, tarpais ir Enter (text nodes)
komentarais
```

Pvz.:

```html
<p>Labas</p>
```

- `<p>` – element node
- `Labas` – text node

Net tarpai tarp elementų gali būti DOM text nodes. Komentarai taip pat gali būti DOM mazgai.

---

# 5. Pagrindinė DOM darbo logika

Beveik visos DOM užduotys prasideda taip:

```text
1. SURASK elementą
2. IŠSAUGOK jį kintamajame
3. KAŽKĄ su juo padaryk
```

Pvz.:

```js
const root = document.getElementById("root");
root.style.color = "red";
```

<span style="color:red"><b>Jei nesupranti DOM užduoties, pirmas klausimas: „Kokį HTML elementą turiu surasti?“</b></span>

---

# 6. Elemento radimas pagal `id`

HTML:

```html
<div id="root">Labas</div>
```

JS:

```js
const root = document.getElementById("root");
```

Svarbu: su `getElementById()` nerašome `#`.

```js
document.getElementById("root");
```

ne:

```js
document.getElementById("#root");
```

---

# 7. Elementų radimas pagal tag pavadinimą

HTML:

```html
<p>Labas 1</p>
<p>Viso gero 2</p>
```

JS:

```js
const paragraphs = document.getElementsByTagName("p");
```

Gauname **HTMLCollection**.

```text
HTMLCollection(2) [p, p]
```

Pirmas elementas:

```js
paragraphs[0]
```

Antras:

```js
paragraphs[1]
```

Kiekis:

```js
paragraphs.length
```

<span style="color:red"><b>`getElementsByTagName()` grąžina kolekciją.</b></span>

---

# 8. Elementų radimas pagal klasę

HTML:

```html
<p class="intro">Pirmas</p>
<p class="intro">Antras</p>
```

JS:

```js
const items = document.getElementsByClassName("intro");
```

Pirmas:

```js
items[0]
```

Kiekis:

```js
items.length
```

<span style="color:red"><b>Klasė nėra unikali – tą pačią klasę gali turėti keli elementai.</b></span>

---

# 9. `querySelector()`

`querySelector()` leidžia naudoti CSS selektorius.

```js
document.querySelector("#root");
document.querySelector(".intro");
document.querySelector("p");
```

`querySelector()` grąžina **pirmą rastą elementą**.

---

# 10. `querySelectorAll()`

Jei reikia visų atitikimų:

```js
document.querySelectorAll("p");
document.querySelectorAll(".intro");
```

Gauname kolekciją (NodeList).

---

# 11. Kada kurį naudoti?

```text
getElementById("root")     → pagal konkretų ID
querySelector("#root")     → pirmas pagal CSS selektorių
querySelectorAll(".item")  → visi pagal CSS selektorių
```

---

# 12. Turinys – `innerHTML`

HTML:

```html
<p id="p1">Hello World!</p>
```

JS:

```js
document.getElementById("p1").innerHTML = "New text!";
```

`=` perrašo turinį.

```js
document.getElementById("p1").innerHTML += " New text!";
```

`+=` papildo.

<span style="color:red"><b>`innerHTML` gali įdėti ir HTML kodą, ne tik tekstą.</b></span>

---

# 13. `textContent`

Kai norime pakeisti paprastą tekstą:

```js
root.textContent = "Naujas tekstas!";
```

Trumpai:

```text
innerHTML   → gali interpretuoti HTML
textContent → paprastas tekstas
```

---

# 14. HTML atributai

Pvz.:

```html
<img src="logo.png" alt="Logo" id="logo">
```

Atributai:

```text
src
alt
id
```

Kitas pavyzdys:

```html
<a href="https://google.com" target="_blank">Google</a>
```

Atributai:

```text
href
target
```

---

# 15. `setAttribute()`

Prideda arba pakeičia atributą.

```js
const button = document.getElementById("myBtn");
button.setAttribute("class", "click-btn");
button.setAttribute("disabled", "");
```

---

# 16. `getAttribute()`

Paima atributo reikšmę.

```js
const link = document.getElementById("myLink");
console.log(link.getAttribute("href"));
console.log(link.getAttribute("target"));
```

---

# 17. `removeAttribute()`

Pašalina atributą:

```js
link.removeAttribute("href");
```

Atmintinė:

```text
setAttribute()    → pridėti / pakeisti
getAttribute()    → gauti
removeAttribute() → pašalinti
```

---

# 18. Kai kuriuos atributus galima keisti tiesiogiai

Pvz. paveikslėlio `src`:

```js
document.getElementById("myImage").src = "landscape.jpg";
```

Taip galima dirbti ir su:

```js
img.src
input.value
link.href
```

---

# 19. CSS keitimas per DOM

```js
root.style.color = "red";
root.style.backgroundColor = "lightblue";
root.style.fontSize = "50px";
root.style.display = "none";
root.style.borderRadius = "20px";
```

---

# 20. CSS savybės JS rašomos camelCase

CSS:

```css
background-color
font-size
border-radius
```

JS:

```js
backgroundColor
fontSize
borderRadius
```

<span style="color:red"><b>JS stiliaus savybėse nenaudojame `-`, rašome camelCase.</b></span>

---

# 21. Keli CSS stiliai vienu metu

```js
div.style.cssText = "color: blue; background: white;";
```

arba:

```js
div.setAttribute("style", "color: blue; background: white;");
```

---

# 22. `className`

```js
console.log(element.className);
```

Parodo dabartinę klasę.

Galima perrašyti:

```js
element.className = "newClass";
```

<span style="color:red"><b>`className = ...` perrašo esamas klases.</b></span>

---

# 23. `classList`

Pridėti klasę:

```js
element.classList.add("active");
```

Pašalinti:

```js
element.classList.remove("active");
```

Perjungti:

```js
element.classList.toggle("active");
```

`toggle()`:

```text
jei klasės nėra → prideda
jei yra → pašalina
```

---

# 24. DOM įvykiai

JavaScript gali reaguoti į vartotojo veiksmus.

Pvz.:

```text
click
dblclick
mousemove
mouseover
touchstart
keyup
focus
change
submit
scroll
resize
```

Paprasčiau:

```text
įvykis = kažkas atsitiko puslapyje
```

---

# 25. `onclick`

```js
document.getElementById("myBtn").onclick = displayDate;
```

Funkcija:

```js
function displayDate() {
    document.getElementById("demo").innerHTML = Date();
}
```

<span style="color:red"><b>Čia funkcijos vardą perduodame be `()` – `displayDate`, ne `displayDate()`.</b></span>

---

# 26. Inline `onclick`

```html
<button onclick="document.getElementById('id1').style.color='red'">
    Click Me
</button>
```

Veikia, bet vėliau skaidrėse rodomas modernesnis būdas – `addEventListener()`.

---

# 27. `onload`

`onload` suveikia, kai puslapis užsikrauna.

```html
<body onload="checkCookies()">
```

Skaidrėse su `navigator.cookieEnabled` tikrinama, ar įjungti cookies.

---

# 28. `onchange`

```html
<input type="text" id="fname" onchange="myFunction()">
```

Svarbi vieta:

```js
document.getElementById("fname").value
```

`value` = input laukelyje įvesta reikšmė.

---

# 29. `onmouseover` ir `onmouseout`

```text
onmouseover → pelė užvažiuoja ant elemento
onmouseout  → pelė išeina nuo elemento
```

---

# 30. `onfocus`

Suveikia, kai elementas gauna fokusą.

```html
<input type="text" onfocus="myFunction(this)">
```

```js
function myFunction(x) {
    x.style.background = "yellow";
}
```

---

# 31. `onblur`

Suveikia, kai elementas praranda fokusą.

```text
paspaudei į input
↓
įvedei tekstą
↓
paspaudei kitur
↓
onblur
```

---

# 32. `addEventListener()`

Skaidrėse jis pateikiamas kaip šiuolaikinis būdas dirbti su įvykiais.

HTML:

```html
<button id="myBtn">Try it</button>
```

JS:

```js
document
    .getElementById("myBtn")
    .addEventListener("click", myFunction);

function myFunction() {
    alert("Hello World!");
}
```

Skaitome:

```text
surask myBtn
↓
klausyk click
↓
kai paspaus → paleisk myFunction
```

<span style="color:red"><b>Labai svarbi DOM schema: ELEMENTAS + EVENTAS + FUNKCIJA.</b></span>

---

# 33. `event`

Event funkcija gali gauti specialų objektą `event`.

```js
document.body.addEventListener("click", function(event) {
    console.log(event);
});
```

`event` turi informaciją apie įvykį.

---

# 34. `event.target`

`event.target` parodo, ant kurio HTML elemento realiai įvyko eventas.

```js
document.body.addEventListener("click", function(event) {
    console.log(event.target);
});
```

<span style="color:red"><b>`event.target` = konkretus elementas, ant kurio įvyko paspaudimas ar kitas eventas.</b></span>

---

# 35. `preventDefault()`

```js
event.preventDefault();
```

Sustabdo numatytą naršyklės veiksmą, pvz. formos automatinį išsiuntimą.

---

# 36. `matches()`

```js
document.addEventListener("click", function(event) {
    if (event.target.matches("#my-button")) {
        console.log("Mygtukas paspaustas");
    }
});
```

Čia tikriname, ar paspaustas elementas atitinka `#my-button`.

---

# 37. Pilnas DOM pavyzdys – tekstas

HTML:

```html
<button id="btn">Keisti tekstą</button>
<p id="text">Senas tekstas</p>
```

JS:

```js
const button = document.getElementById("btn");
const text = document.getElementById("text");

button.addEventListener("click", function() {
    text.textContent = "Naujas tekstas";
});
```

Kas vyksta:

```text
1. Randam button
2. Randam p
3. Klausom click
4. Paspaudus paleidžiama funkcija
5. Funkcija pakeičia tekstą
```

---

# 38. Pilnas DOM pavyzdys – CSS

HTML:

```html
<button id="btn">Keisti spalvą</button>
<div id="box">Dėžė</div>
```

JS:

```js
const button = document.getElementById("btn");
const box = document.getElementById("box");

button.addEventListener("click", function() {
    box.style.backgroundColor = "red";
});
```

---

# 39. Kaip atpažinti DOM užduotį?

Jei sako „surask pagal ID“:

```js
document.getElementById(...)
```

Jei sako „surask visus p“:

```js
document.getElementsByTagName("p")
```

arba:

```js
document.querySelectorAll("p")
```

Jei sako „pakeisk tekstą“:

```js
element.textContent = ...
```

Jei sako „pakeisk spalvą“:

```js
element.style.color = ...
```

Jei sako „pridėk klasę“:

```js
element.classList.add(...)
```

Jei sako „kai paspaudžia“:

```js
element.addEventListener("click", ...)
```

---

# 40. Dažniausios beginner klaidos

## `getElementById()` su `#`

Blogai:

```js
document.getElementById("#root");
```

Gerai:

```js
document.getElementById("root");
```

Bet su `querySelector()`:

```js
document.querySelector("#root");
```

## Kolekcija ir vienas elementas

```js
document.getElementById("root")
```

→ vienas elementas.

```js
document.getElementsByTagName("p")
```

→ kolekcija.

## Pamirštamas `.style`

Blogai:

```js
root.color = "red";
```

Gerai:

```js
root.style.color = "red";
```

## CSS savybė su `-`

Blogai:

```js
root.style.background-color = "red";
```

Gerai:

```js
root.style.backgroundColor = "red";
```

---

# 41. Greita atmintinė

## Rasti elementą

```js
document.getElementById("id")
document.getElementsByTagName("p")
document.getElementsByClassName("class")
document.querySelector("#id")
document.querySelector(".class")
document.querySelectorAll(".class")
```

## Turinys

```js
element.innerHTML
element.textContent
input.value
```

## Atributai

```js
element.setAttribute(...)
element.getAttribute(...)
element.removeAttribute(...)
```

## Stilius

```js
element.style.color
element.style.backgroundColor
element.style.fontSize
element.style.display
element.style.borderRadius
```

## Klasės

```js
element.className
element.classList.add(...)
element.classList.remove(...)
element.classList.toggle(...)
```

## Eventai

```text
onclick
onload
onchange
onmouseover
onmouseout
onfocus
onblur
```

Moderniau:

```js
element.addEventListener("click", function() {
});
```

## Event objektas

```js
event.target
event.preventDefault()
event.target.matches(...)
```

---

# 42. Svarbiausias DOM šablonas atsiskaitymui

```js
const element = document.getElementById("id");

element.addEventListener("click", function() {
    element.textContent = "Naujas tekstas";
});
```

Jame yra:

```text
document
↓
elemento paieška
↓
event listener
↓
funkcija
↓
DOM pakeitimas
```

<span style="color:red"><b>Jei supranti šitą grandinę, jau supranti didelę DOM I dalies dalį.</b></span>

---

# 43. Mini DOM žemėlapis

```text
DOM
│
├── document
│
├── elementų paieška
│   ├── getElementById
│   ├── getElementsByTagName
│   ├── getElementsByClassName
│   ├── querySelector
│   └── querySelectorAll
│
├── turinys
│   ├── innerHTML
│   ├── textContent
│   └── value
│
├── atributai
│   ├── setAttribute
│   ├── getAttribute
│   └── removeAttribute
│
├── CSS
│   └── element.style...
│
├── klasės
│   ├── className
│   └── classList
│
└── eventai
    ├── click
    ├── change
    ├── focus
    ├── blur
    ├── mouseover
    ├── load
    ├── addEventListener
    └── event.target
```

---

# 44. Ką tikrai verta išmokti pirmiausia?

<span style="color:red"><b>1. `document.getElementById()`</b></span>

<span style="color:red"><b>2. `querySelector()` ir `querySelectorAll()`</b></span>

<span style="color:red"><b>3. `textContent` / `innerHTML`</b></span>

<span style="color:red"><b>4. `.style` ir camelCase</b></span>

<span style="color:red"><b>5. `classList.add/remove/toggle`</b></span>

<span style="color:red"><b>6. `addEventListener("click", ...)`</b></span>

<span style="color:red"><b>7. `event.target`</b></span>

Jei šitie dalykai tampa aiškūs, visa likusi DOM I dalis pradeda daug lengviau dėliotis.
