## Tipos de datos primitivos 💡

Los tipos de datos primitivos se caracterizan por ser valores más básicos y simples que se pueden asignar a una variable, esto quiere decir que son **datos que se pasan por valor**.

### Number

El tipo **number** representa tanto números enteros como de punto flotante.

Además de los números comunes, existen los llamados **valores numéricos especiales** que también pertenecen a este tipo de datos: `Infinity`, `-Infinity` y `NaN`.

- `Infinity`: Representa el infinito matemático `∞`. Es un valor especial que es mayor que cualquier número.
    - Podemos obtenerlo como resultado de la división por cero:
    ```js
    const num = 1 / 0;
    console.log(num) // Infinity
    
    const numero = Infinity;
    console.log(numero); // Infinity
    ```
- `NaN`: Representa un error de cálculo. Es el resultado de una operación matemática incorrecta o indefinida.
    - Un ejemplo claro es dividir un string con un número:
    ```js
    const num = "no es un número" / 2;
    console.log(num) // NaN
    ```
- `-Infinity`: Representa el infinito negativo matemático `-∞`.
    - Un ejemplo claro es definir la variable como `-Infinity`:
    ```js
    const num = -Infinity;
    console.log(num) // -Infinity
    ```
### BigInt

En JavaScript, el tipo **number** no puede representar de forma segura valores enteros mayores que `2^53-1`.

Para ser realmente precisos, el tipo de dato **number** puede almacenar enteros muy grandes `hasta 1.7976931348623157 * 10308`, pero fuera del rango de enteros seguros `±(253-1)` habrá un error de precisión, porque no todos los dígitos caben en el almacén fijo de 64-bit. Así que es posible que se almacene un valor **aproximado**.

Por ejemplo, estos dos números (justo por encima del rango seguro) son iguales:

```js
console.log(9007199254740991 + 1); // 9007199254740992
console.log(9007199254740991 + 2); // 9007199254740992
```

### String

Un **string** en JavaScript es una cadena de caracteres y debe colocarse entre comillas.

```js
let str = "Hola";
let str2 = 'Las comillas simples también están bien';
let phrase = `${str}, como estas?`
```

En JavaScript, hay 3 tipos de comillas:

1. Comillas dobles: **" "**.
2. Comillas simples: **' '**.
3. Backticks (comillas invertidas): **``**

Las comillas dobles y simples son comillas "sencillas". No hay diferencia entre ellas en JavaScript.

Los backtick son comillas de "funcionalidad extendida". Nos permiten incrustar variables y expresiones en una cadena de caracteres encerrándolas en `${...}`.

### Boolean

El tipo **boolean** tiene sólo dos valores posibles: `true` o `false`.

Este tipo se utiliza comúnmente para almacenar valores de sí/no:
- true significa "sí, correcto, verdadero".
- false significa "no, incorrecto, falso".

Por ejemplo:

```js
// Asignar valores booleanos a variables
let esVerdadero = true;
let esFalso = false;

// Usar valores booleanos en expresiones condicionales
if (esVerdadero) {
  console.log("Es verdadero");
} else {
  console.log("No es verdadero");
}

if (esFalso) {
  console.log("Es falso");
} else {
  console.log("No es falso");
}

// Operaciones booleanas
let resultadoAND = true && false; // AND lógico
console.log(resultadoAND); // Output: false

let resultadoOR = true || false; // OR lógico
console.log(resultadoOR); // Output: true

let resultadoNOT = !true; // NOT lógico
console.log(resultadoNOT); // Output: false

```
### Null

El valor especial `null` no pertenece a ninguno de los tipos descritos anteriormente.

Forma un tipo propio separado que contiene sólo el valor `null`:

```js
let age = null;
```

En JavaScript, `null` no es una "referencia a un objeto inexistente" o un "puntero nulo" como en otros lenguajes. Es sólo un **valor especial que representa "nada", "vacío" o "valor desconocido"**.
### Undefined

El significado de `undefined` es "valor no asignado". Si una variable es declarada, pero no asignada, entonces su valor es `undefined`:

```js
let age;

console.log(age); // undefined
```

Otro ejemplo:

```js
let age = 25;

age = undefined; // cambiamos el valor a undefined

console.log(age); //undefined
```

No se recomienda hacer eso de cambiar un valor a `undefined`, para eso esta el `null`.

### Symbol

El tipo de dato `symbol` se usa para identificar objetos de forma única.

Ejemplo:

```js
const simbol1 = Symbol('Simbolo 1');

const simbol2 = Symbol('Simbolo 2');

console.log(simbolo1 === simbolo2); // Output: false

// Utilización de símbolos como propiedades de un objeto
const MY_KEY = Symbol();
let objeto = {};

objeto[MY_KEY] = 'Valor asignado al símbolo';

console.log(objeto[MY_KEY]); // Output: Valor asignado al símbolo

```

## Tipos de datos no primitivos 💡

Los tipos de datos no primitivos en **JavaScript** se caracterizan por ser valores que se pasan por referencia en lugar de por valor. Esto significa que, cuando asignas un valor no primitivo a una variable, la variable no almacena directamente el valor, sino una referencia a la ubicación en la memoria donde se encuentra el valor.

### Object

Los objetos en JavaScript son colecciones de pares clave-valor. Pueden contener propiedades y métodos, donde cada propiedad es una asociación entre un nombre (cadena) y un valor. Los objetos se utilizan para representar entidades complejas y estructuradas en JavaScript.

```js
// Ejemplo de un objeto representando un estudiante
let estudiante = {
  nombre: "Diego",
  edad: 20,
  carrera: "Ingeniería de ejecución en computación e informática",
  universidad: "Universidad del Bío-Bío"
};

console.log(estudiante) 
/* Output: 
{ nombre: 'Diego', 
  edad: 20, 
  carrera: 'Ingeniería de ejecución en computación e informática', 
  universidad: 'Universidad del Bío-Bío' 
}
*/
console.log(estudiante.nombre); // Output: Diego
console.log(estudiante.edad); // Output: 20
console.log(estudiante.carrera); // Output: Ingeniería de ejecución en computación e informática
console.log(estudiante.universidad); // Output: Universidad del Bío-Bío
console.log(typeof estudiante); // Output: object
```

### Array

Los arrays en JavaScript son objetos especiales que almacenan una lista ordenada de elementos. Pueden contener valores de cualquier tipo de datos, incluyendo otros arrays u objetos. Los arrays se utilizan para almacenar colecciones de datos relacionados.

```js
let numeros = [1, 2, 3, 4, 5];

console.log(numeros[2]); // Output: 3
console.log(typeof numeros); // Output: object 
console.log(numeros instanceof Array); // Output: true 

```
- El `console.log(typeof numeros);` devuelve `object` porque en JavaScript, los arreglos son considerados objetos.

- El `console.log(numeros instanceof Array);` devuelve `true` porque la variable `numeros` es un arreglo. El instanceof se utiliza para comprobar si un objeto pertenece a una determinada clase o tipo.

### Function

Las funciones en JavaScript son objetos especiales que pueden ser llamados para realizar una tarea específica o para calcular un valor. Pueden aceptar parámetros y devolver un resultado. Las funciones se utilizan para modularizar y reutilizar código.

```js
// Ejemplo de una función que suma dos números
function sumar(a, b) {
  return a + b;
}

console.log(sumar(3, 5)); // Output: 8
```


### Date

El objeto Date en JavaScript se utiliza para trabajar con fechas y horas. Permite la creación, manipulación y formateo de fechas y horas.

```js
// Ejemplo de creación de un objeto Date
let fechaActual = new Date();

console.log(fechaActual); // Output: 2024-03-05T00:14:33.114Z
```

### Regexp

Los objetos RegExp en JavaScript se utilizan para trabajar con expresiones regulares, que son patrones utilizados para hacer coincidir combinaciones de caracteres en cadenas de texto.

```js
// Ejemplo de creación de una expresión regular para validar correos electrónicos
let expresionRegular = /^[^\s@]+@[^\s@]+\.[^\s@]+$/; 

console.log(expresionRegular.test("diego@gmail.com")); // Output: true
```

Esta expresión regular se utiliza para validar direcciones de correo electrónico.

- `^`: Este símbolo denota el comienzo de la cadena.
- `[^\s@]+`: Este grupo busca uno o más caracteres que no sean espacios en blanco (\s) ni el símbolo "@".
- `@`: Este símbolo representa el carácter "@".
- `[^\s@]+`: Este grupo busca uno o más caracteres que no sean espacios en blanco (\s) ni el símbolo "@".
- `\.`: Este es el punto literal ".". Se debe utilizar \ para escaparlo ya que en las expresiones regulares el punto se interpreta como "cualquier carácter".
- `[^\s@]+`: Este grupo busca uno o más caracteres que no sean espacios en blanco (\s) ni el símbolo "@".
- `$`: Este símbolo denota el final de la cadena.