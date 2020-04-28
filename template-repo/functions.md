BOOTCAMP DAG 2
Dit zijn mijn aantekeningen van alle bronnen, ik heb het zo kort mogelijk proberen voor mezelf te verwoorden om het te kunnen begrijpen. Ik ben niet goed in Javascript en kan het een beetje lezen, dus ik probeer er zoveel mogelijk zo goed mogelijk van op te steken.

-

5.1: FUNCTION BASICS -P P5.JS TUTORIAL
https://www.youtube.com/watch?v=wRHAitGzBrg

Je kunt functions definen of callen. Function moeten modified zijn en reusable. Anders kan je straks niet meer vinden wat je zoek en een ander al helemaal niet.

Bijvoorbeeld bij het maken van een stuiterende bal is het handig om meerdere functies te maken. Bijvoorbeeld: een draw function, een stuiter function en een move function. Zo is het makkelijker bij te houden. Dus niet alles in één functie ondanks het over één object gaat. 

Wil je alle functions bijvoorbeeld activeren doe dan het volgende.

```js
Function bal() {
    Move();
    Display();
    Bounce();
}
```

Define is dus het maken en Calling is het aanroepen van dit. 

-

FUNCTIONS
https://eloquentjavascript.net/03_functions.html

Functies zijn de brood en boter van Javascript. 

```js
const square = function(x) {
  return x * x;
};

console.log(square(12));
// → 144
```

Manier om je paramater te gebruiken. Je kunt ook pas in je console eventueel de parameter invullen.

```js
const makeNoise = function() {
  console.log("Pling!");
};
```

```js
makeNoise();
// → Pling!

const power = function(base, exponent) {
  let result = 1;
  for (let count = 0; count < exponent; count++) {
    result *= base;
  }
  return result;
};

console.log(power(2, 10));
// → 1024
```

Je kunt ook function omdraaien, dit doe je omdat je anders te veel functie namen gaat krijgen. Ze werken inprincipe hetzelfde. 

Bindings en scopes:
Scope is het hele programma. 
Bindings is een stukje. 

```js
let x = 10;
if (true) {
  let y = 20;
  var z = 30;
  console.log(x + y + z);
  // → 60
}
// y is not visible here
console.log(x + z);
// → 40
```

Dit is een goed voorbeeld van het verschil tussen let en var. 
Let kan alleen gezien worden binnen de if en er niet buiten. 
Var kan overal gezien worden.

```js
const halve = function(n) {
  return n / 2;
};

let n = 10;
console.log(halve(100));
// → 50
console.log(n);
// → 10
```

Het antwoord is 50 omdat je de functie uitvoert. 100 / 2 is 50. Bij de tweede wordt alleen de parameter gebruikt, en omdat n 10 is, is het antwoord ook 10. 
