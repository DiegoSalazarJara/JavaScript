
# Conversión de tipo automática

JavaScript tiende a salirse de su camino para aceptar casi cualquier programa que le demos, incluso programas que hacen cosas extrañas.

Esto es bien demostrado por las siguientes expresiones:

```js
console.log(8 * null);
// -> 0
console.log("5" - 1);
// -> 4
console.log("5" + 1);
// -> 51
console.log("cinco" * 2);
// -> NaN
console.log(false == 0);
// -> true
```

Cuando un operador es aplicado al tipo de valor "incorrecto", JavaScript silenciosamente convertirá ese valor al tipo que necesita, utilizando una seria de reglas que frecuentemente no dan el resultado que quisieras o esperarías.

Esto es llamado *coerción de tipo*. Cuando algo que no se traduce a un número en una manera obvia (tal como "cinco" o undefined) es convertido a un número, obtenemos el valor NaN.

Otros ejemplos:

```js
console.log(null == undefined);
// -> true
console.log(null == 0);
// -> false
```
