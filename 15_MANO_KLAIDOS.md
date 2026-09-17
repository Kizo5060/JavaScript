# Mano klaidos

#js #klaidos

Čia rašyk klaidas, kurias jau padarei. Jos labai naudingos mokantis.

## Šablonas

### Klaida
```js
// įklijuok kodą
```

### Ką rodė terminalas?
```text
klaidos tekstas
```

### Kodėl taip nutiko?
Parašyk savo žodžiais.

### Kaip pataisiau?
```js
// teisingas kodas
```

---

## Pavyzdys — terminalo aplankas

Buvau:

```text
C:\Users\...\js\funkcijos>
```

Bandžiau:

```powershell
cd ciklai
```

Bet `ciklai` buvo ne `funkcijos` viduje, o šalia.

Sprendimas:

```powershell
cd ..\ciklai
```

`..` = vienas aplankas atgal.

---

## Pavyzdys — funkcija neiškviečiama

```js
function hello() {
    console.log("Labas");
}
```

Vien funkcijos sukūrimo neužtenka.

Reikia:

```js
hello();
```
