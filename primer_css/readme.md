# Mi primer archivo .css

CSS (Cascading Style Sheets) es el lenguaje que usamos para dar estilo y formato a nuestras páginas HTML. Mientras que HTML define la estructura y el contenido, CSS define cómo se ve ese contenido.

---

## ¿Qué es CSS?

CSS permite controlar:
- **Colores** de texto y fondos
- **Tipografía** (fuentes, tamaños, espaciado)
- **Espaciado** (márgenes, padding)
- **Posicionamiento** de elementos
- **Efectos visuales** (sombras, bordes, transiciones)

---

## Vincular CSS a HTML

Existen tres formas de aplicar CSS a un documento HTML:

### 1. CSS Inline (en línea)
Directamente en el elemento HTML usando el atributo `style`:
```html
<p style="color: red; font-size: 20px;">Este es un párrafo rojo</p>
```

### 2. CSS Interno
Dentro del `<head>` usando la etiqueta `<style>`:
```html
<head>
    <style>
        p {
            color: red;
            font-size: 20px;
        }
    </style>
</head>
```

### 3. CSS Externo (Recomendado)
En un archivo separado `.css`, vinculado con `<link>`:
```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

**¿Por qué es mejor usar CSS externo?**
- Separa el contenido del diseño
- Reutilizable en múltiples páginas
- Más fácil de mantener
- Mejor rendimiento (el navegador puede cachear el archivo)

---

## Sintaxis Básica de CSS

```css
selector {
    propiedad: valor;
    otra-propiedad: otro-valor;
}
```

**Ejemplo:**
```css
h1 {
    color: green;
    font-size: 32px;
    text-align: center;
}
```

### Partes de una regla CSS:

- **Selector**: Indica QUÉ elementos se van a estilizar (`h1`, `p`, `.clase`, `#id`)
- **Propiedad**: Indica QUÉ aspecto se va a modificar (`color`, `font-size`, etc.)
- **Valor**: Indica CÓMO se va a modificar (`green`, `32px`, etc.)
- **Declaración**: Conjunto de propiedad + valor
- **Bloque de declaraciones**: Todo lo que va entre `{ }`

---

## Selectores Básicos

### 1. Selector de Etiqueta
Selecciona todos los elementos de ese tipo:
```css
p {
    color: red;
}
```
Afecta a **todos** los `<p>` del documento.

### 2. Selector de Clase
Selecciona elementos con una clase específica (se define con `.`):
```css
.destacado {
    background-color: yellow;
}
```
```html
<p class="destacado">Este párrafo está destacado</p>
```

### 3. Selector de ID
Selecciona un elemento único con un ID específico (se define con `#`):
```css
#titulo-principal {
    color: blue;
    font-size: 48px;
}
```
```html
<h1 id="titulo-principal">Título Principal</h1>
```

**Importante:** Los IDs deben ser únicos en la página, mientras que las clases pueden repetirse.

### 4. Selector Universal
Selecciona todos los elementos:
```css
* {
    margin: 0;
    padding: 0;
}
```

---

## Propiedades Comunes de CSS

### Colores

```css
p {
    color: red;                    /* Color del texto */
    background-color: lightblue;   /* Color de fondo */
}
```

**Formas de definir colores:**
- Nombres: `red`, `blue`, `green`
- Hexadecimal: `#ff0000`, `#0000ff`
- RGB: `rgb(255, 0, 0)`
- RGBA: `rgba(255, 0, 0, 0.5)` (con transparencia)

### Tipografía

```css
h1 {
    font-family: Arial, sans-serif;  /* Tipo de fuente */
    font-size: 24px;                 /* Tamaño */
    font-weight: bold;               /* Grosor */
    font-style: italic;              /* Estilo */
    text-align: center;              /* Alineación */
    text-decoration: underline;      /* Decoración */
}
```

### Espaciado

```css
div {
    margin: 20px;       /* Espacio exterior */
    padding: 10px;      /* Espacio interior */
    border: 1px solid black;  /* Borde */
}
```

**El Box Model:**
```
┌─────────────────────────┐
│       Margin            │
│  ┌──────────────────┐   │
│  │    Border        │   │
│  │  ┌───────────┐   │   │
│  │  │  Padding  │   │   │
│  │  │  ┌─────┐  │   │   │
│  │  │  │Cont.│  │   │   │
│  │  │  └─────┘  │   │   │
│  │  └───────────┘   │   │
│  └──────────────────┘   │
└─────────────────────────┘
```

### Dimensiones

```css
img {
    width: 200px;      /* Ancho fijo */
    height: 150px;     /* Alto fijo */
}

div {
    width: 50%;        /* Ancho relativo */
    max-width: 800px;  /* Ancho máximo */
    min-height: 200px; /* Alto mínimo */
}
```

---

## Ejemplo Completo: style.css

Aquí está el archivo `style.css` del proyecto explicado:

```css
/* Estilo para todos los párrafos */
p {
    color: red;                    /* Texto rojo */
    background-color: aquamarine;  /* Fondo color agua */
    text-align: center;            /* Texto centrado */
}

/* Estilo para todos los h1 */
h1 {
    color: green;                  /* Texto verde */
}

/* Estilo para todos los h2 */
h2 {
    color: brown;                  /* Texto marrón */
}
```

### ¿Cómo se aplica?

Cuando vinculas este archivo CSS al HTML con:
```html
<link rel="stylesheet" href="style.css">
```

El navegador:
1. Lee el HTML
2. Descarga el CSS
3. Aplica los estilos según los selectores
4. Renderiza la página con los estilos aplicados

---

## Cascada y Especificidad

CSS significa "Cascading" (en cascada) porque los estilos se aplican de forma jerárquica:

### Orden de prioridad (de menor a mayor):
1. Estilos del navegador (por defecto)
2. CSS externo
3. CSS interno (`<style>`)
4. CSS inline (`style=""`)
5. `!important` (evitar usar)

### Especificidad:
Cuando varios selectores apuntan al mismo elemento, gana el más específico:

```css
p { color: blue; }           /* Especificidad: 1 */
.texto { color: red; }       /* Especificidad: 10 */
#principal { color: green; } /* Especificidad: 100 */
```

Si tienes:
```html
<p id="principal" class="texto">Hola</p>
```

El color será **verde** porque el ID tiene mayor especificidad.

---

## Buenas Prácticas

1. **Usa CSS externo** siempre que sea posible
2. **Nombres descriptivos** para clases: `.boton-principal`, `.lista-productos`
3. **Evita IDs para estilos**, usa clases
4. **Organiza tu CSS** por secciones:
   ```css
   /* Reset */
   /* Tipografía */
   /* Layout */
   /* Componentes */
   /* Utilidades */
   ```
5. **Comenta tu código** para explicar decisiones complejas
6. **Mantén la especificidad baja** para facilitar el mantenimiento

---