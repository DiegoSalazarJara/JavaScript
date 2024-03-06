
# Estilo de codificación 🚀

Nuestro código debe ser lo más limpio y fácil de leer como sea posible.

Ese es en realidad el arte de la programación: tomar una tarea compleja y codificarla de manera correcta y legible para los humanos. Un buen estilo de código ayuda mucho en eso.

## Sintaxis 👨‍💻

![sintaxisCorrecta.png](../images/sintaxisCorrecta.png)

## Llaves 📈

En la mayoría de proyectos de JavaScript las llaves están escritas en estilo "Egipcio" con la llave de apertura en la misma línea que la declaración que la precede.

```js
if (condicion) {
    // Hacer algo
    //...
    //...
}
```

Una construcción de una sola línea, como `if (condicion) haceralgo()`, es un caso límite importante. 

¿Deberíamos usar llaves?

Aquí están las variantes anotadas para que puedas juzgar la legibilidad por ti mismo.

1. Los principiantes a veces hacen eso. ¡Malo! Las llaves no son necesarias:

```js	
if (f == 0) {f = 1}
```

2. Dividir en una línea separada sin llaves. Nunca hagas eso, es fácil cometer un error al agregar nuevas líneas:

```js
if (f == 0)
  f = 1
```

3. Una línea sin llaves: aceptable, si es corta:
    
```js
if (f == 0) f = 1
```

4. La mejor variate:

```js
if (f == 0) {
  f = 1
}
```

Para un código muy breve, se permite una línea `if (condicion) return null`. Pero un bloque de código (la última variante) suele ser más legible.

## Tamaño de línea 📃

A nadie le gusta leer una larga línea horizontal de código. Es una buena práctica dividirlos.

Por ejemplo:

```js
// ` Nos permite dividir la cadena de caracteres en múltiples líneas

let cadena = ` 
    Aquí hay una cadena de texto que es
    bastante larga y que se extiende
    a través de varias líneas en el código.
`;
```

Y para sentencias `if`:

```js
if (
  numero == 3 &&
  nombre == "Juan" &&
  apellido == "Perez"
) {
  // Hacer algo
}
```
La longitud máxima de la línea debe acordarse con el equipo de trabajo. Suele tener 80 o 120 caracteres.

## Indentación (sangría) 📑

Hay dos tipos de indentación:

- Indentación horizontal: 2 o 4 espacios.

Se realiza una sangría horizontal utilizando 2 o 4 espacios o el símbolo de tabulación horizontal. Los espacios son más comunes hoy en día.

Una ventaja de los espacios sobre las tabulaciones es que los espacios permiten configuraciones de sangría más flexibles que el símbolo del tabulador.

Por ejemplo, podemos alinear los argumentos con el paréntesis de apertura, así:

```js
function muyLargaFuncion(
  argumento1,
  argumento2,
  argumento3
) {
  // ...
}
```

```js	
import {
    modulo1,
    modulo2,
    modulo3
} from 'nombre-del-modulo';
```

- Indentanción vertical: Líneas vacías para dividir código en bloques lógicos.

Incluso una sola función a menudo se puede dividir en bloques lógicos. En el siguiente ejemplo, la inicialización de variables, el bucle principal y la devolución de resultados se dividen verticalmente:

```js
function elevado(a, b) {
  let resultado = 1;
  //              <--
  for (let i = 0; i < b; i++) {
    resultado *= a;
  }
  //              <--
  return resultado;
}
```

Insertar una nueva línea extra donde ayude a hacer el código más legible. No debe haber más de nueve líneas de código sin una indentación vertical.

## Punto y coma ✔️

Debe haber un punto y coma después de cada declaración, incluso si se puede omitir.

Hay lenguajes de programación en los que el punto y coma es realmente opcional y rara vez se usa. Sin embargo, en JavaScript, hay casos en los que un salto de línea no se interpreta como un punto y coma, lo que puede llevar a errores.

## Niveles anidados 💡

Intenta evitar anidar el código en demasiados niveles de profundidad.

Algunas veces es buena idea usar la directiva "continue" en un bucle para evitar anidamiento extra.

Por ejemplo, en lugar de añadir un `if` anidado como este:

```js
for (let i = 0; i < 10; i++) {
  if (condicion1) {
    // Hacer algo
    if (condicion2) {
      // Hacer algo
    }
  }
}
```

Podemos escribir:

```js
for (let i = 0; i < 10; i++) {
  if (!condicion1) continue;
  // Hacer algo
  if (!condicion2) continue;
  // Hacer algo <-- Sin nivel extra de anidamiento 
}
```

Algo similar se puede hacer con `if/else` y `return`.

Por ejemplo, las dos construcciones siguientes son idénticas.

Opción 1:

```js
function findUser(user) {
  if (user) {
    let usuario = user;
  } else {
    let usuario = "No se encontró el usuario";
  }
}
```

Opción 2:

```js
function findUser(user) {
  if (user) {
    return user;
  } else {
    return "No se encontró el usuario";
  }
}
```

El segundo es más legible porque el "caso especial" de "no se encontró el usuario" se maneja en un nivel de anidamiento menos.

## Colocación de funciones 👾

Si está escribiendo varias funciones "auxiliares" y el código lo usas, hay tres formas de organizar las funciones.

1. Declarar las funciones antes de usarlas.

```js
// declaración de funciones
function suma(a, b) {
  ...
}

function resta(a, b) {
  ...
}


// el código que las usan
let resultadoSuma = suma();
let resultadoResta = resta();
```

2. Código primero, después las funciones.

```js
// el código que las usan
let resultadoSuma = suma();
let resultadoResta = resta();

// declaración de funciones
function suma(a, b) {
  ...
}

function resta(a, b) {
  ...
}
```

3. Mixto: Una función es declarada donde se usa por primera vez.

La mayoria del tiempo, la segunda variante es preferida.

Eso es porque al leer el código, primero queremos saber qué *hace*. Si el código va primero, entonces queda claro desde el principio. Entonces, tal vez no necesitemos leer las funciones, especialmente si sus nombres son descriptivos y claros.

## Linters 💯

Linters son herramientas que pueden verificar automáticamente el estilo de tu código y hacer sugerencias para mejorarlo.

Lo mejor de ellos es que la comprobación de estilo también puede encontrar algunos errores, como erroes tipográficos en nombres de variables o funciones. Debido a esta característica, se recomienda usar un linter incluso si no desea apegarse a un "estilo de código" en particular.

Los linters más populares para JavaScript son ESLint y JSHint.