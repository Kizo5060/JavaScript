# Operatoriai

#js #operatoriai

## Matematiniai

```js
+   // sudėtis
-   // atimtis
*   // daugyba
/   // dalyba
%   // liekana
```

Pavyzdys:

```js
let result = 10 + 5;
console.log(result);
```

## Palyginimo

```js
>    // daugiau
<    // mažiau
>=   // daugiau arba lygu
<=   // mažiau arba lygu
===  // lygu
!==  // nelygu
```

Pavyzdys:

```js
let age = 20;

console.log(age >= 18);
```

Rezultatas:

```text
true
```

## Loginiai

```js
&&   // IR
||   // ARBA
!    // NE
```

Pavyzdys:

```js
let age = 20;
let hasLicense = true;

if (age >= 18 && hasLicense) {
    console.log("Gali vairuoti");
}
```

## `++` ir `--`

```js
let x = 1;

x++;
x--;
```

Dažnai naudojama cikluose.

Susiję:
- [[08_IF_ELSE]]
- [[11_CIKLAI]]
