# Mi primer archivo en formato .html

HTML (HyperText Markup Language) es el lenguaje de marcado estándar para crear páginas web. Define la estructura y el contenido de una página mediante etiquetas.

---

## ¿Qué es HTML?

HTML no es un lenguaje de programación, es un **lenguaje de marcado** que estructura el contenido web mediante etiquetas. Cada etiqueta tiene un propósito específico y ayuda al navegador a entender cómo mostrar el contenido.

### Características principales:
- Define la **estructura** de la página (no el diseño)
- Utiliza **etiquetas** entre `< >` para marcar elementos
- Es **semántico**: las etiquetas describen el significado del contenido
- Funciona en **cualquier navegador** (es un estándar web)

---

## Creación del archivo

Para crear un archivo HTML:

1. Abre tu editor de código (VS Code, Sublime, etc.)
2. Crea un nuevo archivo
3. Nómbralo con extensión `.html` (por ejemplo: `index.html`)
4. Comienza a escribir código HTML

**¿Por qué `index.html`?**  
Es la convención para la página principal de un sitio web. Los servidores buscan automáticamente este archivo como página de inicio.

---

## Estructura básica de un documento HTML

Todo documento HTML debe tener esta estructura base:

```html
<!DOCTYPE html>
<html> 
    <head>      
        <title> Mi primer documento html </title>
    </head>
    <body>  
        <h1>Título</h1>
        <h2>Subtítulo 1</h2>
        <p>Petrer</p>
        <img src="petrercastillo.jpg" width="240" height="135" alt="Castillo de Petrer">
        <h2>Subtítulo 2</h2>
        <p>Segundo párrafo</p>
        <a href="hola.html">NO CLICKES AQUÍ!!!</a>
        <h3>Esto es una tabla:</h3>
        <table>
            <tr>
                <th>cabecera 1</th>
                <th>cabecera 2</th>
            </tr>
            <tr>
                <td>hola</td>
                <td>adiós</td>
            </tr>
            <tr>
                <td>adiós</td>
                <td>hola</td>
            </tr>
        </table>
    </body>
</html>
```

---

## Anatomía de un documento HTML

### 1. `<!DOCTYPE html>`
- Declara que este es un documento HTML5
- Debe ser la primera línea del archivo
- No es una etiqueta HTML, es una declaración
- Le dice al navegador qué versión de HTML usar

### 2. `<html>`
- Elemento raíz que contiene todo el documento
- Todo el contenido HTML va dentro de esta etiqueta
- Se abre con `<html>` y se cierra con `</html>`

### 3. `<head>`
- Contiene **metadatos** (información sobre la página)
- No se muestra directamente en el navegador
- Incluye:
  - `<title>`: Título que aparece en la pestaña del navegador
  - `<meta>`: Información sobre codificación, autor, descripción
  - `<link>`: Enlaces a archivos CSS
  - `<script>`: Enlaces a archivos JavaScript

**Ejemplo completo de `<head>`:**
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Sitio Web</title>
    <link rel="stylesheet" href="style.css">
</head>
```

### 4. `<body>`
- Contiene todo el **contenido visible** de la página
- Todo lo que el usuario ve está dentro de `<body>`
- Incluye: textos, imágenes, enlaces, tablas, formularios, etc.

---

## Etiquetas HTML Fundamentales

### Títulos (Headings)

HTML ofrece 6 niveles de títulos, de más importante a menos importante:

```html
<h1>Título Principal</h1>          <!-- El más importante -->
<h2>Subtítulo</h2>
<h3>Sub-subtítulo</h3>
<h4>Título nivel 4</h4>
<h5>Título nivel 5</h5>
<h6>Título nivel 6</h6>             <!-- El menos importante -->
```

**Buenas prácticas:**
- Solo un `<h1>` por página (título principal)
- Usar los headings en orden jerárquico
- No saltarse niveles (no pasar de `<h2>` a `<h4>`)
- Importancia semántica para SEO y accesibilidad

### Párrafos

```html
<p>Este es un párrafo de texto.</p>
<p>Este es otro párrafo separado.</p>
```

Los párrafos automáticamente tienen espacio antes y después.

### Énfasis y formato de texto

```html
<strong>Texto importante (negrita)</strong>
<em>Texto enfatizado (cursiva)</em>
<mark>Texto resaltado</mark>
<small>Texto pequeño</small>
<del>Texto tachado</del>
<ins>Texto insertado (subrayado)</ins>
```

### Saltos de línea y líneas horizontales

```html
<p>Primera línea<br>Segunda línea</p>  <!-- <br> salto de línea -->
<hr>  <!-- Línea horizontal -->
```

---

## Enlaces (Links)

Los enlaces conectan páginas y recursos:

```html
<!-- Enlace a otra página del mismo sitio -->
<a href="otra-pagina.html">Ir a otra página</a>

<!-- Enlace a un sitio externo -->
<a href="https://google.com">Ir a Google</a>

<!-- Enlace que abre en nueva pestaña -->
<a href="https://google.com" target="_blank">Abrir en nueva pestaña</a>

<!-- Enlace a una sección de la misma página -->
<a href="#seccion">Ir a la sección</a>
```

**Atributos importantes:**
- `href`: Destino del enlace (URL o ruta)
- `target="_blank"`: Abre en nueva pestaña
- `title`: Tooltip que aparece al pasar el mouse

---

## Imágenes

```html
<img src="ruta/imagen.jpg" alt="Descripción de la imagen" width="240" height="135">
```

**Atributos importantes:**
- `src`: Ruta de la imagen (puede ser relativa o absoluta)
- `alt`: Texto alternativo (importante para accesibilidad)
- `width` y `height`: Dimensiones en píxeles
- `title`: Tooltip al pasar el mouse

**Tipos de rutas:**
```html
<!-- Ruta relativa (mismo directorio) -->
<img src="imagen.jpg" alt="Foto">

<!-- Ruta relativa (subdirectorio) -->
<img src="imagenes/foto.jpg" alt="Foto">

<!-- Ruta absoluta (URL completa) -->
<img src="https://ejemplo.com/imagen.jpg" alt="Foto">
```

---

## Listas

### Listas no ordenadas (viñetas)

```html
<ul>
    <li>Elemento 1</li>
    <li>Elemento 2</li>
    <li>Elemento 3</li>
</ul>
```

### Listas ordenadas (numeradas)

```html
<ol>
    <li>Primer elemento</li>
    <li>Segundo elemento</li>
    <li>Tercer elemento</li>
</ol>
```

### Listas anidadas

```html
<ul>
    <li>Elemento principal
        <ul>
            <li>Sub-elemento 1</li>
            <li>Sub-elemento 2</li>
        </ul>
    </li>
    <li>Otro elemento principal</li>
</ul>
```

---

## Tablas

Las tablas organizan datos en filas y columnas:

```html
<table>
    <tr>
        <th>Cabecera 1</th>
        <th>Cabecera 2</th>
    </tr>
    <tr>
        <td>Dato 1</td>
        <td>Dato 2</td>
    </tr>
    <tr>
        <td>Dato 3</td>
        <td>Dato 4</td>
    </tr>
</table>
```

**Elementos de una tabla:**
- `<table>`: Contenedor de la tabla
- `<tr>`: Table Row (fila)
- `<th>`: Table Header (cabecera, se muestra en negrita)
- `<td>`: Table Data (celda de datos)

**Tabla más completa:**
```html
<table>
    <thead>
        <tr>
            <th>Nombre</th>
            <th>Edad</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Juan</td>
            <td>25</td>
        </tr>
        <tr>
            <td>María</td>
            <td>30</td>
        </tr>
    </tbody>
</table>
```

---

## Contenedores y Estructura Semántica

### Contenedores genéricos

```html
<div>Contenedor en bloque (ocupa todo el ancho)</div>
<span>Contenedor en línea (solo ocupa lo necesario)</span>
```

### Etiquetas semánticas (HTML5)

```html
<header>Cabecera del sitio o sección</header>
<nav>Navegación principal</nav>
<main>Contenido principal de la página</main>
<section>Sección temática del contenido</section>
<article>Contenido independiente y reutilizable</article>
<aside>Contenido relacionado o secundario</aside>
<footer>Pie de página</footer>
```

**Ventajas de usar etiquetas semánticas:**
- Mejora el **SEO** (posicionamiento en buscadores)
- Mejora la **accesibilidad** (lectores de pantalla)
- Código más **legible** y mantenible
- Estructura más **clara** del documento

**Ejemplo de estructura semántica:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Mi Sitio</title>
</head>
<body>
    <header>
        <h1>Mi Sitio Web</h1>
        <nav>
            <ul>
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#sobre-mi">Sobre mí</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <article>
            <h2>Título del artículo</h2>
            <p>Contenido del artículo...</p>
        </article>
    </main>
    
    <footer>
        <p>&copy; 2025 Mi Sitio Web</p>
    </footer>
</body>
</html>
```

---

## Comentarios en HTML

Los comentarios no se muestran en el navegador, solo en el código:

```html
<!-- Esto es un comentario -->
<!-- 
    Los comentarios pueden 
    ocupar múltiples líneas
-->
```

**Usos de los comentarios:**
- Explicar código complejo
- Desactivar temporalmente código
- Dejar notas para otros desarrolladores
- Organizar secciones del código

---

## Atributos Globales

Estos atributos pueden usarse en cualquier etiqueta HTML:

```html
<!-- id: Identificador único -->
<div id="contenedor-principal"></div>

<!-- class: Clase para estilos CSS -->
<p class="texto-destacado"></p>

<!-- style: Estilos CSS inline (no recomendado) -->
<p style="color: red;">Texto rojo</p>

<!-- title: Tooltip al pasar el mouse -->
<abbr title="HyperText Markup Language">HTML</abbr>

<!-- lang: Idioma del contenido -->
<html lang="es"></html>
```

---

## Caracteres Especiales (Entidades HTML)

Algunos caracteres tienen significado especial en HTML y deben codificarse:

```html
&lt;    <!-- < (menor que) -->
&gt;    <!-- > (mayor que) -->
&amp;   <!-- & (ampersand) -->
&quot;  <!-- " (comillas dobles) -->
&copy;  <!-- © (copyright) -->
&reg;   <!-- ® (registrado) -->
&nbsp;  <!-- Espacio no separable -->
```

Ejemplo:
```html
<p>Para escribir &lt;html&gt; usamos entidades HTML</p>
<!-- Se muestra: Para escribir <html> usamos entidades HTML -->
```

---

## Buenas Prácticas HTML

1. **Indentación consistente**: Usa 2 o 4 espacios para anidar elementos
   ```html
   <div>
       <p>Párrafo dentro de div</p>
   </div>
   ```

2. **Cierra todas las etiquetas**: Aunque HTML5 es flexible, cierra siempre
   ```html
   <!-- Correcto -->
   <p>Texto</p>
   
   <!-- Evitar (aunque funcione) -->
   <p>Texto
   ```

3. **Usa minúsculas** para etiquetas y atributos
   ```html
   <!-- Recomendado -->
   <div class="contenedor"></div>
   
   <!-- Evitar -->
   <DIV CLASS="contenedor"></DIV>
   ```

4. **Comillas en atributos**: Usa siempre comillas dobles
   ```html
   <img src="imagen.jpg" alt="Descripción">
   ```

5. **Estructura semántica**: Usa etiquetas que describan el contenido
   ```html
   <!-- Mejor -->
   <nav>...</nav>
   
   <!-- Evitar -->
   <div class="navegacion">...</div>
   ```

6. **Alt en imágenes**: Siempre incluye texto alternativo
   ```html
   <img src="logo.png" alt="Logo de la empresa">
   ```

7. **Jerarquía de headings**: No te saltes niveles
   ```html
   <!-- Correcto -->
   <h1>Título</h1>
   <h2>Subtítulo</h2>
   <h3>Sub-subtítulo</h3>
   
   <!-- Evitar -->
   <h1>Título</h1>
   <h4>Subtítulo</h4>
   ```

---

## Validación HTML

Es importante validar tu HTML para asegurarte de que cumple los estándares:

- [W3C Markup Validation Service](https://validator.w3.org/)
- Extensiones de VS Code para validación en tiempo real
- Herramientas de desarrollo del navegador (F12)

---

## Visualizar tu HTML

Para ver tu página HTML:

1. **Directamente**: Abre el archivo `.html` con tu navegador
   - Click derecho → Abrir con → Navegador
   - O arrastra el archivo al navegador

2. **Con Live Server** (recomendado para desarrollo):
   - Extensión de VS Code
   - Actualización automática al guardar cambios
   - Servidor local profesional

3. **Inspeccionar elementos**:
   - F12 o Click derecho → Inspeccionar
   - Ver la estructura del documento
   - Depurar problemas

---