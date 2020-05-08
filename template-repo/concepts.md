###BOOTCAMP DAG 4
Dit zijn mijn aantekeningen van alle bronnen, ik heb het zo kort mogelijk proberen voor mezelf te verwoorden om het te kunnen begrijpen. Ik ben niet goed in Javascript en kan het een beetje lezen, dus ik probeer er zoveel mogelijk zo goed mogelijk van op te steken.
freecodecamp link: https://www.freecodecamp.org/mikehov

-

####BINDINGS AND SCOPES
https://eloquentjavascript.net/03_functions.html#h_XqQR5FlX+8

Elke binding heeft een scope. Scope is het hele programma, de bindings zijn heel globaal. De bindings die zijn gemaakt voor functies of parameters kunnen alleen daarin aangeroepen worden. Bindings roep je aan met "let" of "const", dit kan ook met "var" maar dit is de oude methode.
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

Er zijn global en local bindings. Binnen de andere blokken en functies kun de blokken en functies worden gemaakt, waardoor ze op meerde plekken kunnen worden gegbruikt. Global is overal en local is alleen op die plek, binnen een functie is dus bijvoorbeeld local. 
```js
const hummus = function(factor) {
  const ingredient = function(amount, unit, name) {
    let ingredientAmount = amount * factor;
    if (ingredientAmount > 1) {
      unit += "s";
    }
    console.log(`${ingredientAmount} ${unit} ${name}`);
  };
  ingredient(1, "can", "chickpeas");
  ingredient(0.25, "cup", "tahini");
  ingredient(0.25, "cup", "lemon juice");
  ingredient(1, "clove", "garlic");
  ingredient(2, "tablespoon", "olive oil");
  ingredient(0.5, "teaspoon", "cumin");
};
```

-

####YOU DON'T KNOW JS YET: SCOPE & CLOSURES - 2ND EDITION
https://github.com/getify/You-Dont-Know-JS/blob/2nd-ed/scope-closures/ch4.md

Probeer global scope altijd zoveel mogelijk te vermijden, dit maakt het maken van namen makkelijker. Hier een voorbeeld van een functie in een functie. 
```js
(function wrappingOuterScope(){
    var moduleOne = (function one(){
        // ..
    })();

    var moduleTwo = (function two(){
        // ..

        function callModuleOne() {
            moduleOne.someMethod();
        }

        // ..
    })();
})();
```

```js
var moduleOne = (function one(){
    // ..
})();
```

```js
var moduleTwo = (function two(){
    // ..

    function callModuleOne() {
        moduleOne.someMethod();
    }

    // ..
})();
```

JS exposes its built-ins:
primitives: undefined, null, Infinity, NaN
natives: Date(), Object(), String(), etc.
global functions: eval(), parseInt(), etc.
namespaces: Math, Atomics, JSON
friends of JS: Intl, WebAssembly

The environment hosting the JS engine exposes its own built-ins:
console (and its methods)
the DOM (window, document, etc)
timers (setTimeout(..), etc)
web platform APIs: navigator, history, geolocation, WebRTC, etc.

Dit werkt hetzelfde als met de plus en quotes, alleen nu doe je het met dollar sign.
```js
var studentName = "Kyle";

function hello() {
    console.log(`Hello, ${ studentName }!`);
}

hello();
// Hello, Kyle!
```

```js
global.studentName = "Kyle";

function hello() {
    console.log(`Hello, ${ studentName }!`);
}

hello();
// Hello, Kyle!

module.exports.hello = hello;
```

-

####CLOSURES - PART 5 OF FUNCTIONAL PROGRAMMING IN JAVASCRIPT
https://www.youtube.com/watch?v=CQqwU2Ixu-U

Javascript heeft clossures. Clossures maakt code leesbaaar. 