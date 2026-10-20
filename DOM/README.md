# js_avanzado

# Tema 5: Uso del DOM (Document Object Model)

**Especialidad:** Sistemas
**Lenguaje:** JavaScript

---

##  1. ¿Qué es el DOM?

El DOM (*Document Object Model*), o Modelo de Objetos del Documento, es una representación de una página web en forma de árbol de objetos. Permite que JavaScript acceda a los elementos HTML, los modifique, cree nuevos elementos o elimine los existentes.

Por ejemplo, JavaScript puede cambiar el texto de un título sin necesidad de volver a escribir toda la página.

```html
<h1 id="titulo">Hola, mundo</h1>
```

```javascript
document.getElementById("titulo").textContent = "Hola, compañeros";
```

**Resultado:** el título cambia de «Hola, mundo» a «Hola, compañeros».

### Estructura del DOM

El siguiente esquema representa cómo se organizan los elementos de una página web:

```text
document
   |
  html
 / \
head body
 | / | \
title h1 p button
```

* `document`: representa el documento completo.
* `html`: es el elemento principal de la página.
* `head`: contiene información de la página.
* `body`: contiene el contenido de la página.
* `h1`, `p` y `button`: son ejemplos de elementos HTML.

---

## 2. ¿Para qué sirve el DOM?

El DOM permite que una página web sea interactiva y responda a las acciones de los usuarios.

Sus principales funciones son:

* Cambiar textos y títulos.
* Modificar colores, tamaños y estilos.
* Obtener información escrita en campos de texto.
* Responder a eventos, como hacer clic en un botón.
* Crear nuevos elementos.
* Eliminar elementos existentes.
* Actualizar el contenido sin recargar toda la página.

###  En pocas palabras

* **HTML:** crea la estructura de la página.
* **CSS:** define su apariencia.
* **JavaScript:** utiliza el DOM para interactuar con sus elementos y modificarlos.

---

## 3. Conceptos principales del DOM

### Nodo

Es cada unidad que forma parte del documento, como un elemento HTML, un texto o un comentario.

### Padre

Es el elemento que contiene directamente a otro elemento.

### Hijo

Es el elemento que está contenido directamente dentro de otro.

### Hermano

Es un nodo que comparte el mismo padre con otro nodo.

###  Ejemplo de relaciones entre elementos

```text
        div (padre)
        / \
    p (hijo) span (hijo)
       | |
   Texto 1 Texto 2
```

En este ejemplo, `div` es el padre de `p` y `span`. Estos dos elementos son hijos de `div` y hermanos entre sí.

---

## 4. Métodos y propiedades más importantes

| Método o propiedad | ¿Para qué sirve? | Ejemplo |
| -------------------- | ----------------------------------------------------------------- | ------------------------------------------ |
| `getElementById()` | Busca un elemento por su identificador. | `document.getElementById("titulo")` |
| `querySelector()` | Selecciona el primer elemento que coincide con un selector CSS. | `document.querySelector("p")` |
| `querySelectorAll()` | Selecciona todos los elementos que coinciden con un selector CSS. | `document.querySelectorAll("p")` |
| `textContent` | Permite leer o cambiar el texto. | `titulo.textContent = "Hola"` |
| `style` | Permite modificar estilos directamente. | `titulo.style.color = "red"` |
| `createElement()` | Crea un elemento nuevo. | `document.createElement("li")` |
| `appendChild()` | Agrega un nodo dentro de otro. | `lista.appendChild(item)` |
| `remove()` | Elimina un elemento. | `item.remove()` |
| `addEventListener()` | Permite responder a eventos. | `boton.addEventListener("click", funcion)` |

**Consejo para recordar:** con el DOM podemos seleccionar, modificar, crear, agregar y eliminar elementos.

---

##  5. Ejemplo práctico: cambiar un título

Vamos a crear una página que cambie el texto y el color de un título al presionar un botón.

### Archivo `index.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Ejemplo DOM</title>
</head>
<body>

    <h1 id="titulo">¡Hola, compañeros!</h1>

    <button id="boton">Cambiar título</button>

    <script src="script.js"></script>
</body>
</html>
```

### Archivo `script.js`

```javascript
const titulo = document.getElementById("titulo");
const boton = document.getElementById("boton");

boton.addEventListener("click", function() {
    titulo.textContent = "¡Estamos aprendiendo DOM!";
    titulo.style.color = "purple";
});
```

###  ¿Cómo funciona?

1. `getElementById("titulo")` selecciona el título.
2. `getElementById("boton")` selecciona el botón.
3. `addEventListener("click", ...)` detecta cuándo se hace clic.
4. `textContent` cambia el texto.
5. `style.color` cambia el color a morado.

**Resultado esperado:** al presionar el botón, el título cambia de texto y se vuelve morado.

### ¿Cómo ejecutarlo?

1. Crea una carpeta llamada `tema5-dom`.
2. Guarda los archivos `index.html` y `script.js` dentro de ella.
3. Abre `index.html` en tu navegador.
4. Presiona el botón y observa el cambio.

No necesitas instalar bibliotecas adicionales.

---

## Otro ejemplo: crear una lista con el DOM

Este ejemplo demuestra cómo crear un elemento nuevo y agregarlo a una lista.

```html
<h2>Mis materias favoritas</h2>
<ul id="lista"></ul>

<script>
const lista = document.getElementById("lista");

const materia = document.createElement("li");
materia.textContent = "Matemáticas";

lista.appendChild(materia);
</script>
```

### ¿Qué hace cada instrucción?

1. `getElementById()` encuentra la lista.
2. `createElement("li")` crea un elemento de lista.
3. `textContent` le asigna el texto «Matemáticas».
4. `appendChild()` agrega el elemento a la lista.

**Resultado:** aparece una lista con la materia Matemáticas.



## Ventajas del DOM

* Facilita la creación de páginas web interactivas.
* Permite actualizar el contenido sin recargar toda la página.
* Ayuda a responder a las acciones del usuario.
* Permite crear y eliminar elementos dinámicamente.
* Facilita la manipulación de la estructura y el contenido HTML mediante JavaScript.

---

## Conclusión

El DOM es una herramienta fundamental para el desarrollo web con JavaScript porque permite interactuar con los elementos de una página. Gracias a él, podemos cambiar textos, modificar estilos, responder a eventos y crear contenido dinámico.

Aprender a utilizar el DOM es importante para desarrollar páginas web más interactivas, funcionales y fáciles de usar.

---

## Fuentes de consulta

1. MDN Web Docs. *Document Object Model (DOM).*
   https://developer.mozilla.org/es/docs/Web/API/Document_Object_Model

2. MDN Web Docs. *Anatomía del árbol DOM.*
   https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Anatomy_of_the_DOM

3. MDN Web Docs. *Introducción a la manipulación del DOM.*
   https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/DOM_scripting


