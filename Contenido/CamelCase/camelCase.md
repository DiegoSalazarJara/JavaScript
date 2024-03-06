
# Camel case

Camel case es una forma de escribir frases sin espacios, en la que la primera letra de cada palabra va en mayúscula, salvo la primera letra de toda la palabra compuesta, que puede ir en mayúscula o minúscula.
 
- El nombre proviene de la similitud de las mayúsculas con las jorobas del lomo de un camello. 

- A menudo se estiliza como **camelCase** para recordar al lector su aspecto.

## Ejemplos

- `nombreDeVariable`
- `nombreDeFuncion`
- `nombreDeClase`
- `nombreDeMetodo`

```js
let nombreDeVariable = "Hola mundo";

let nombreDeFuncion = function() {
  return "Hola mundo";
};

let nombreDeClase = class {
  constructor() {
    this.nombreDeMetodo = function() {
      return "Hola mundo";
    };
  }
};

console.log(nombreDeVariable);
```

## Reglas

- La primera letra de la primera palabra puede ser mayúscula o minúscula.

- La primera letra de cada palabra subsiguiente debe ser mayúscula.

- No se permiten espacios ni caracteres especiales.

Camel case es la convención más popular en JavaScript, Java y otros lenguajes.