# Tarea

* **Track:** _Especialización Front-End_
* **Curso:** _JS Deep Dive: Crea tu propia librería usando JavaScript_
* **Unidad:** _Fundamentos de JS_

***

## OBJETIVO

Leer el código javascript e identificar los siguientes puntos:
* Scope, función global, función local, funciones de callback, function expression, function statement, funciones closures, pila de ejecución (stack execution) y cola de eventos (event queue).

## TEORÍA

#### Scope

El scope es el alcance de una variable, puede ser de dos tipos, global y local. Una variable cuyo scope es global se puede acceder desde cualquier parte del código, una local solo desde la función que la contiene.

Nota: En javascript, la palabra GLOBAL significa Not Inside a Function (Quiere decir que variables o código que no se encuentre dentro de una función es 100% Global).

#### Función global

```javascript
var a = 1; // En ese caso la variable a es una variable global 

function global() {
  console.log(a);
}

global();
console.log(a);
```

#### Función local

```javascript
function local() {
  var a = 2; // En este otro caso, la variable a es local ya que la definimos dentro de la función local().
  console.log(a);
}

local();
console.log(a);
```

#### Funciones de callback
Es una función que se pasa a otra función como un argumento, que luego se invoca dentro de la función externa para completar algún tipo de rutina o acción.

#### Function statement
Una declaración de función define una variable de función nombrada sin requerir asignación de variable.

#### Function expression

Una expresión de función define una función como parte de una sintaxis de expresión mayor (generalmente una asignación de variable). 

```javascript
var greet = function() {
  return 'Hello world';
};
```

#### Funciones closures

Son funciones que manejan variables independientes. En otras palabras, la función definida en el closure "recuerda" el entorno en el que se ha creado.

```javascript
function inicia() {
  var nombre = "Mozilla"; // 'nombre' es una variable local creada por la función 'inicia'
  function muestraNombre() { // 'muestraNombre' es una función interna (un closure)
    alert(nombre); // dentro de esta función usamos una variable declarada en la función padre
  }
  muestraNombre();
}
inicia();  
```



***

## DESARROLLO

Extraer código del archivo app.js y ubicarlo en la sección que corresponde:

#### Scope global (variable global)

```javascript
var $buttonNext = $('#next');
```

#### Scope local (variable local)

```javascript
var regex = /^[0-9]+$/;
var creditCardNumber = soloNumeros(longitud(numberCard));
var arr = [];
var sumaTotal = 0;
```

#### Funciones globales

```javascript
function activeButton() {    
  $buttonNext.attr('disabled', false);
} 
```

#### Funciones locales

```javascript
function soloNumeros(input) {
  var regex = /^[0-9]+$/;
  ...
}

function isValidCreditCard(numberCard) {
  var creditCardNumber = soloNumeros(longitud(numberCard));
    if (creditCardNumber !== undefined) {
      var arr = [];
      var sumaTotal = 0;
      ...
    }
  ...
}
```

#### Funciones de callback

```javascript
function longitud(input) {
  if (input.trim().length === 16) {
    return input;
  }
}

function soloNumeros(input) {
  var regex = /^[0-9]+$/;
  if (regex.test(input)) {
    return input;
  }
}
```

#### Function statement

```javascript
function activeButton() {
  ...
} 

function desactiveButton() {  
  ...
} 

function longitud(input) {
  ...
}

function soloNumeros(input) {
  ...
}

function isValidCreditCard(numberCard) {
  ...
}
```

## BIBLIOGRAFÍA

* https://lms.laboratoria.la/cohorts/lim-2018-01-bc-js-front-end-developer/courses/deep-dive/03-foundations/04-funcs
* https://developer.mozilla.org/en-US/docs/Glossary/Callback_function
* https://developer.mozilla.org/es/docs/Web/JavaScript/Closures
* https://medium.com/@sergiodxa/definiendo-conceptos-closure-y-scope-en-javascript-9081f1e113e6
* https://developer.mozilla.org/es/docs/Web/JavaScript/EventLoop