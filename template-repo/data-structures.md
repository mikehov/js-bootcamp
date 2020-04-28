BOOTCAMP DAG 3
Dit zijn mijn aantekeningen van alle bronnen, ik heb het zo kort mogelijk proberen voor mezelf te verwoorden om het te kunnen begrijpen. Ik ben niet goed in Javascript en kan het een beetje lezen, dus ik probeer er zoveel mogelijk zo goed mogelijk van op te steken.
freecodecamp link: https://www.freecodecamp.org/mikehov

-

7.1: WHAT IS AN ARRAY? - P5.JS TUTORIAL
https://www.youtube.com/watch?v=VIQoUghHSxU

Een array is een lijst met waardes.
```js
let geenArray = 4;
let welArray = [4, 8, 2, 3];
```

Ook heb je objecten, dit lijkt op een array.
```js
let objecten = {
    x: 5,
    y: 7,
    z: true
}
```

Ze lijken heel erg op elkaar, maar vooral de volgorde is het gene wat belangrijk is. 

-

2.3: JAVASCRIPT OBJECTS - P5.JS Tutorial
https://www.youtube.com/watch?v=-e5h4IGKZRY

Inplaats van het neerzetten van drie variablen kun je ook een object neerzetten dat werkt als een soort container. Dan heb je maar één variabel nodig. Hieronder zie je een object met daarin data over het object.
```js
var cirkel = {
    x: 4,
    y: 5,
    diameter: 6
};
```

Het probleem met objecten is dat je niet meer kunt verwijzen naar de x, y of diameter omdat deze binnen het object zitten. Dit kun je doen door te syntaxen. Inplaats van x, y of diameter gebruik je: cirkel.x, cirkel.y en cirkel.diameter. Dit is handig want dit zorgt voor minder dubbele code en je krijgt minder verschillende namen.

-

DATA STRUCTURES: OBJECTS AND ARRAYS
https://eloquentjavascript.net/04_data.html

Je kunt ook iets uit de array pakken maar dan -1. 
```js
let listOfNumbers = [2, 3, 5, 7, 11];
console.log(listOfNumbers[2]);
// → 5
console.log(listOfNumbers[0]);
// → 2
console.log(listOfNumbers[2 - 1]);
// → 3
```

```js
let doh = "Doh";
console.log(typeof doh.toUpperCase);
// → function
console.log(doh.toUpperCase());
// → DOH
```

Wat pop in dit geval doet is dat hij de laatste weg haalt. 
```js
let sequence = [1, 2, 3];
sequence.push(4);
sequence.push(5);
console.log(sequence);
// → [1, 2, 3, 4, 5]
console.log(sequence.pop());
// → 5
console.log(sequence);
// → [1, 2, 3, 4]
```

```js
let day1 = {
  squirrel: false,
  events: ["work", "touched tree", "pizza", "running"]
};
console.log(day1.squirrel);
// → false
console.log(day1.wolf);
// → undefined
day1.wolf = false;
console.log(day1.wolf);
// → false
```

Object 1 en 3 zijn niet gelijk. 1 en 2. Dit komt omdat er niet wordt gekeken naar de value, er wordt zeerwaarschijnlijk gekeken naar de ID waardoor 1 en 3 niet hetzelfde zijn. Als je object1.value zou typen zou deze wel true.  
```js
let object1 = {value: 10};
let object2 = object1;
let object3 = {value: 10};

console.log(object1 == object2);
// → true
console.log(object1 == object3);
// → false

object1.value = 15;
console.log(object2.value);
// → 15
console.log(object3.value);
// → 10
```

Een Array Loop.
```js
for (let i = 0; i < JOURNAL.length; i++) {
  let entry = JOURNAL[i];
  // Do something with entry
}
```

