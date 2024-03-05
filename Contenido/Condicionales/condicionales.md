
# Condicionales 💻

Los condicionales son estructuras de control que permiten tomar decisiones en un programa. Estas decisiones se toman a partir de la evaluación de una expresión lógica, que puede ser verdadera o falsa. En JavaScript, los condicionales se implementan a través de las estructuras `if`, `else if` y `else`.

## Estructura `if`

La estructura `if` permite ejecutar un bloque de código si una condición es verdadera. La sintaxis es la siguiente:

```js
if (condicion) {
  // Bloque de código
}
```

Ejecutemos un ejemplo:

```js
let numero = 5;

if (numero > 0) {
  console.log("El número es positivo");
}
```

## Estructura `if`...`else`

La estructura `if`...`else` permite ejecutar un bloque de código si una condición es verdadera y otro bloque si la condición es falsa. La sintaxis es la siguiente:

```js
if (condicion) {
  // Bloque de código si la condición es verdadera
} else {
  // Bloque de código si la condición es falsa
}
```

Ejecutemos un ejemplo:

```js
let numero = -5;

if (numero > 0) {
  console.log("El número es positivo");
} else {
  console.log("El número es negativo");
}
```

## Estructura `if`...`else if`...`else`

La estructura `if`...`else if`...`else` permite evaluar múltiples condiciones. La sintaxis es la siguiente:

```js
if (condicion1) {
  // Bloque de código si la condición 1 es verdadera
} else if (condicion2) {
  // Bloque de código si la condición 2 es verdadera
} else {
  // Bloque de código si ninguna de las condiciones anteriores es verdadera
}
```

Ejecutemos un ejemplo:

```js
let numero = 0;

if ( numero > 0){
    console.log("El número es positivo");
} else if (numero < 0){
    console.log("El número es negativo");
} else {
    console.log("El numero es 0");
}
```

## Operador ternario `?`

El operador ternario `?` es una forma abreviada de escribir una estructura `if`...`else`. La sintaxis es la siguiente:

```js
condicion ? expresion1 : expresion2
```

Ejecutemos un ejemplo:

```js
let numero = 5;
let mensaje = numero > 0 ? "El número es positivo" : "El número es negativo";
console.log(mensaje); // El número es positivo
```

## `Switch`

La estructura `switch` permite evaluar una expresión y ejecutar un bloque de código dependiendo del valor de la expresión. La sintaxis es la siguiente:

```js
switch (expresion) {
  case valor1:
    // Bloque de código si la expresión es igual a valor1
    break;
  case valor2:
    // Bloque de código si la expresión es igual a valor2
    break;
  default:
    // Bloque de código si la expresión no es igual a ninguno de los valores anteriores
}
```

Ejecutemos un ejemplo:

```js
let dia = "lunes";

switch (dia) {
  case "lunes":
    console.log("Hoy es lunes");
    break;
  case "martes":
    console.log("Hoy es martes");
    break;
  default:
    console.log("Hoy es otro día");
}
```
