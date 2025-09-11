# 📚 Apunte JavaScript --- Clase: Variables, Scope y Features Modernas

## 1. let y const

-   **let**: declara variables re-asignables, con scope de bloque
    (`{}`).
-   **const**: no se puede re-asignar, pero si es objeto/array, sus
    valores internos sí se pueden modificar.

``` js
let edad = 20;
edad = 21; // ✔ permitido

const nombre = "Pablo";
// nombre = "Juan"; ❌ error
```

------------------------------------------------------------------------

## 2. Scope global y local

-   **Global**: accesible desde cualquier parte.
-   **Local**: solo dentro de `{}` o función.

``` js
let global = "afuera";

function test() {
  let local = "adentro";
  console.log(global); // ✔
  console.log(local);  // ✔
}
console.log(local); // ❌ error
```

------------------------------------------------------------------------

## 3. Hoisting

-   JS "mueve" declaraciones arriba.
-   **var**: queda `undefined`.
-   **let** y **const**: quedan en Temporal Dead Zone.

``` js
console.log(a); // undefined
var a = 5;

console.log(b); // ❌ error
let b = 10;
```

------------------------------------------------------------------------

## 4. Objetos literales

Definir objetos con `{ clave: valor }`.

``` js
const persona = {
  nombre: "Pablo",
  edad: 30,
  saludar() {
    return `Hola, soy ${this.nombre}`;
  }
};
```

------------------------------------------------------------------------

## 5. Propiedad dinámica

Usar corchetes `[]` para definir nombre de propiedad.

``` js
const clave = "color";
const auto = {
  marca: "Ford",
  [clave]: "rojo"
};
```

------------------------------------------------------------------------

## 6. Template literals

Strings con backticks (`` ` ``). Permiten interpolación `${ }` y
multilínea.

``` js
const nombre = "Pablo";
const saludo = `Hola ${nombre},
¿cómo va todo?`;
```

------------------------------------------------------------------------

## 7. Escape sequence

Caracteres especiales: - `\n` salto de línea - `\t` tabulación - `\"`
comillas dobles - `\\` barra invertida

``` js
console.log("Hola\nMundo");
```

------------------------------------------------------------------------

## 8. Destructuring

Extraer valores de arrays u objetos.

``` js
const [a, b] = [1, 2];
const { nombre, edad } = persona;
```

------------------------------------------------------------------------

## 9. Spread & Rest

-   **Spread (`...`)**: expande arrays/objetos.
-   **Rest (`...`)**: junta valores en array.

``` js
// Spread
const arr = [1,2,3];
const nuevo = [...arr, 4,5];

// Rest
function sumar(...nums) {
  return nums.reduce((a,b) => a+b);
}
sumar(1,2,3,4); // 10
```

------------------------------------------------------------------------

## 10. Asignación por defecto

Dar valores por defecto en destructuring o funciones.

``` js
function saludar(nombre = "invitado") {
  return `Hola ${nombre}`;
}
console.log(saludar()); // Hola invitado
```
