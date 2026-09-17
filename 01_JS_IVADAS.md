# JavaScript įvadas

#js #pagrindai

## Kas yra JavaScript?
JavaScript yra programavimo kalba, kuri dažnai naudojama puslapių elgesiui valdyti.

Paprasta mintis:

**Vartotojas → veiksmas → puslapio reakcija**

Pavyzdžiai:
- paspaudi mygtuką → atsiranda pranešimas;
- paspaudi „Patinka“ → skaičius padidėja;
- įvedi slaptažodį → patikrinama, ar jis pakankamai stiprus.

## JavaScript ir Java
Tai **skirtingos kalbos**. Panašūs tik pavadinimai.

## Kur gali veikti JS?
- naršyklėje;
- serveryje su Node.js;
- kitose aplinkose, kurios turi JavaScript interpretatorių.

## Paleidimas su Node.js
Terminale:

```powershell
node --version
```

Paleisti failą:

```powershell
node task1.js
```

## Prijungimas prie HTML

```html
<script src="script.js" defer></script>
```

`defer` leidžia pirmiau užsikrauti HTML, o tada vykdyti JS.

Susiję:
- [[02_SINTAKSE_IR_USE_STRICT]]
- [[07_IVESTIS_IR_ISVESTIS]]
