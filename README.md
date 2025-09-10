# Apuntes-web
Etiquetas con atributos HTML/CSS/JS

# Apuntes rápidos de HTML, CSS y JavaScript
## 📎 Descargas
- [Apunte HTML](./apuntes/atributos_html.pdf)
- [Apunte CSS](./apuntes/atributos_css.pdf)
- [Apunte JS](./apuntes/atributos_js.pdf)

# 📘 Guía rápida de HTML, CSS y JavaScript con ejemplos

Este README contiene una tabla resumen y ejemplos prácticos de **HTML, CSS y JavaScript**.  
Sirve como apunte personal y guía rápida durante el desarrollo.

---

## 🏷️ HTML con ejemplos

| Etiqueta        | Atributos principales | Ejemplo |
|-----------------|------------------------|---------|
| `<a>`           | href, target, title    | `<a href="https://google.com" target="_blank">Google</a>` |
| `<img>`         | src, alt, width, height| `<img src="foto.jpg" alt="Descripción" width="200">` |
| `<input>`       | type, name, placeholder| `<input type="text" name="usuario" placeholder="Escribe tu nombre">` |
| `<button>`      | type, disabled         | `<button type="submit">Enviar</button>` |
| `<section>`     | id, class              | `<section id="intro" class="fondo">Contenido</section>` |

---

## 🎨 CSS con ejemplos

| Propiedad       | Valores principales / Ejemplo       | Ejemplo |
|-----------------|--------------------------------------|---------|
| color           | red, #ff0000, rgb(255,0,0)          | `p { color: red; }` |
| background      | url(img.jpg), #333                  | `body { background: #333; }` |
| margin / padding| px, %, auto                         | `div { margin: 20px; padding: 10px; }` |
| border          | 1px solid black                     | `img { border: 2px solid blue; }` |
| display         | flex, grid                          | `.contenedor { display: flex; }` |
| flexbox         | justify-content, align-items        | `.caja { display: flex; justify-content: center; }` |
| grid            | grid-template-columns, gap          | `.grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }` |

---

## ⚡ JavaScript con ejemplos

| Concepto        | Ejemplo | Descripción |
|-----------------|---------|-------------|
| Variable        | `let edad = 25; const nombre = "Ana";` | Guardar datos |
| Condicional     | `if (edad >= 18) { console.log("Mayor de edad"); }` | Ejecutar según condición |
| Bucle for       | `for (let i=0; i<5; i++){ console.log(i); }` | Repetición controlada |
| Función         | `function suma(a,b){ return a+b; }` | Bloque reutilizable |
| Arrow function  | `const cuadrado = x => x*x;` | Sintaxis corta de función |
| Array           | `let nums = [1,2,3]; nums.push(4);` | Lista de valores |
| Método map      | `[1,2,3].map(x => x*2);` | Operar sobre un array |
| DOM             | `document.getElementById("titulo").innerText = "Hola!";` | Cambiar HTML desde JS |
| Evento          | `btn.addEventListener("click", ()=>alert("Hola"));` | Responder a usuario |
| Promesa / Fetch | `fetch("data.json").then(r=>r.json()).then(d=>console.log(d));` | Código asincrónico |

---

