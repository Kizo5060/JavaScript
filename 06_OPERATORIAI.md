# 06 – Operatoriai

## Aritmetiniai operatoriai

```js
+   sudėtis
-   atimtis
*   daugyba
/   dalyba
%   liekana
**  kėlimas laipsniu
```

Pvz.:

```js
10 % 2 // 0
```

Todėl `%` dažnai naudojamas tikrinant lyginį skaičių:

```js
if (number % 2 === 0) {
    console.log("Lyginis");
}
```

## Priskyrimo operatoriai

```js
let x = 5;

x += 2; // x = x + 2
x -= 2;
x *= 2;
x /= 2;
```

## Palyginimo operatoriai

```js
>    daugiau
<    mažiau
>=   daugiau arba lygu
<=   mažiau arba lygu
===  griežtai lygu
!==  griežtai nelygu
```

Pvz.:

```js
5 === 5   // true
5 === "5" // false
```

## `==` ir `===`

Beginner lygyje saugiausia įprasti naudoti:

```js
===
```

Nes jis tikrina ir reikšmę, ir tipą.

## Loginiai operatoriai

### AND `&&`

Abi sąlygos turi būti `true`.

```js
age >= 18 && hasTicket
```

### OR `||`

Užtenka bent vienos `true`.

```js
isAdmin || isOwner
```

### NOT `!`

Apverčia boolean reikšmę:

```js
!true  // false
!false // true
```

## `++` ir `--`

```js
count++;
count--;
```

Dažnai naudojama cikluose.
