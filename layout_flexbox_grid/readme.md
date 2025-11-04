# Layout: Flexbox y Grid

Los sistemas de layout en CSS permiten organizar y posicionar elementos en una página web de manera eficiente. Flexbox y Grid son las dos herramientas modernas más poderosas para crear layouts.

---

## ¿Qué es un Layout?

El **layout** (disposición) se refiere a cómo se organizan y distribuyen los elementos en una página web. Antes de Flexbox y Grid, se usaban técnicas menos eficientes como floats y positioning.

### Evolución de los layouts en CSS:
1. **Tables** (años 90) - No semántico, difícil de mantener
2. **Floats** (años 2000) - Diseñado para texto, usado incorrectamente para layouts
3. **Positioning** - Bueno para casos específicos, no para layouts generales
4. **Flexbox** (2012) - Diseñado para layouts unidimensionales
5. **Grid** (2017) - Diseñado para layouts bidimensionales

---

## Flexbox vs Grid: ¿Cuándo usar cada uno?

### Flexbox (Flexible Box Layout)
**Uso:** Layouts **unidimensionales** (una fila o una columna)

**Ideal para:**
- Barras de navegación
- Centrar elementos
- Distribuir espacio entre elementos
- Alinear items en una dirección
- Componentes pequeños

### Grid (CSS Grid Layout)
**Uso:** Layouts **bidimensionales** (filas y columnas simultáneas)

**Ideal para:**
- Layouts de página completa
- Galerías de imágenes
- Dashboards
- Layouts complejos con filas y columnas
- Estructuras de página

**No son excluyentes:** Puedes usar Grid para el layout general y Flexbox para componentes internos.

---

## Flexbox (Flexible Box Layout)

Flexbox organiza elementos en una dimensión: horizontal (fila) o vertical (columna).

### Conceptos básicos

```
┌─────────────────────────────────────┐
│  Flex Container                     │
│  ┌──────┐ ┌──────┐ ┌──────┐        │
│  │Item 1│ │Item 2│ │Item 3│        │
│  └──────┘ └──────┘ └──────┘        │
└─────────────────────────────────────┘
     ↑                  ↑
Main Axis          Cross Axis
(horizontal)       (vertical)
```

### Activar Flexbox

```css
.contenedor {
    display: flex;  /* Activa Flexbox */
}
```

Con esto, todos los hijos directos se convierten en **flex items**.

---

## Propiedades del Flex Container

Estas propiedades se aplican al contenedor padre:

### 1. `flex-direction`
Define la dirección del eje principal:

```css
.contenedor {
    display: flex;
    flex-direction: row;  /* Por defecto: horizontal, izquierda a derecha */
}
```

**Valores:**
- `row`: Horizontal, izquierda a derecha (default)
- `row-reverse`: Horizontal, derecha a izquierda
- `column`: Vertical, arriba a abajo
- `column-reverse`: Vertical, abajo a arriba

### 2. `justify-content`
Alinea items en el **eje principal** (horizontal si es row):

```css
.contenedor {
    display: flex;
    justify-content: center;  /* Centra horizontalmente */
}
```

**Valores:**
- `flex-start`: Al inicio (default)
- `flex-end`: Al final
- `center`: Centrado
- `space-between`: Espacio entre items (extremos pegados)
- `space-around`: Espacio alrededor de items
- `space-evenly`: Espacio igual entre y alrededor de items

### 3. `align-items`
Alinea items en el **eje transversal** (vertical si es row):

```css
.contenedor {
    display: flex;
    align-items: center;  /* Centra verticalmente */
}
```

**Valores:**
- `stretch`: Estira para llenar el contenedor (default)
- `flex-start`: Al inicio
- `flex-end`: Al final
- `center`: Centrado
- `baseline`: Alinea según la línea base del texto

### 4. `flex-wrap`
Controla si los items se envuelven en múltiples líneas:

```css
.contenedor {
    display: flex;
    flex-wrap: wrap;  /* Permite múltiples líneas */
}
```

**Valores:**
- `nowrap`: Una sola línea (default)
- `wrap`: Múltiples líneas si es necesario
- `wrap-reverse`: Múltiples líneas en orden inverso

### 5. `gap`
Espacio entre items (moderno, muy útil):

```css
.contenedor {
    display: flex;
    gap: 20px;  /* 20px de espacio entre items */
}
```

También puedes especificar gap vertical y horizontal:
```css
.contenedor {
    display: flex;
    gap: 20px 10px;  /* 20px vertical, 10px horizontal */
}
```

---

## Propiedades de los Flex Items

Estas propiedades se aplican a los hijos (items):

### 1. `flex-grow`
Define cuánto puede crecer un item:

```css
.item {
    flex-grow: 1;  /* Puede crecer para llenar espacio */
}
```

- `0`: No crece (default)
- `1+`: Proporción de crecimiento relativo

### 2. `flex-shrink`
Define cuánto puede reducirse un item:

```css
.item {
    flex-shrink: 1;  /* Puede reducirse si es necesario */
}
```

- `1`: Puede reducirse (default)
- `0`: No se reduce

### 3. `flex-basis`
Tamaño base del item antes de distribuir espacio:

```css
.item {
    flex-basis: 200px;  /* Tamaño base de 200px */
}
```

### 4. `flex` (shorthand)
Combina grow, shrink y basis:

```css
.item {
    flex: 1;  /* Equivale a: flex-grow: 1; flex-shrink: 1; flex-basis: 0; */
}

.item {
    flex: 0 0 200px;  /* No crece, no se reduce, base 200px */
}
```

### 5. `align-self`
Sobrescribe `align-items` para un item específico:

```css
.item-especial {
    align-self: flex-end;  /* Este item va al final verticalmente */
}
```

---

## Ejemplos Prácticos de Flexbox

### Centrar un elemento (horizontal y verticalmente)

```css
.contenedor {
    display: flex;
    justify-content: center;  /* Centrado horizontal */
    align-items: center;      /* Centrado vertical */
    height: 100vh;            /* Altura completa de la ventana */
}
```

```html
<div class="contenedor">
    <div class="caja">Estoy centrado</div>
</div>
```

### Barra de navegación

```css
.nav {
    display: flex;
    justify-content: space-between;  /* Logo a la izquierda, menú a la derecha */
    align-items: center;             /* Centrado vertical */
    padding: 20px;
}

.nav-menu {
    display: flex;
    gap: 20px;  /* Espacio entre links */
}
```

```html
<nav class="nav">
    <div class="logo">Mi Sitio</div>
    <ul class="nav-menu">
        <li><a href="#">Inicio</a></li>
        <li><a href="#">Sobre mí</a></li>
        <li><a href="#">Contacto</a></li>
    </ul>
</nav>
```

### Distribución equitativa de espacio

```css
.contenedor {
    display: flex;
    gap: 10px;
}

.item {
    flex: 1;  /* Todos los items ocupan el mismo espacio */
}
```

```html
<div class="contenedor">
    <div class="item">Columna 1</div>
    <div class="item">Columna 2</div>
    <div class="item">Columna 3</div>
</div>
```

### Cards responsivas

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    flex: 1 1 300px;  /* Crece, se reduce, base 300px */
}
```

---

## CSS Grid Layout

Grid permite crear layouts bidimensionales complejos con filas y columnas.

### Conceptos básicos

```
Grid Container
┌─────────────────────────────────┐
│ ┌───────┐ ┌───────┐ ┌───────┐ │
│ │Item 1 │ │Item 2 │ │Item 3 │ │  ← Fila 1
│ └───────┘ └───────┘ └───────┘ │
│ ┌───────┐ ┌───────┐ ┌───────┐ │
│ │Item 4 │ │Item 5 │ │Item 6 │ │  ← Fila 2
│ └───────┘ └───────┘ └───────┘ │
└─────────────────────────────────┘
    ↑         ↑         ↑
  Col 1     Col 2     Col 3
```

### Activar Grid

```css
.contenedor {
    display: grid;  /* Activa Grid */
}
```

---

## Propiedades del Grid Container

### 1. `grid-template-columns`
Define el número y tamaño de las columnas:

```css
.contenedor {
    display: grid;
    grid-template-columns: 200px 200px 200px;  /* 3 columnas de 200px */
}
```

**Usando fracciones (fr):**
```css
.contenedor {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;  /* 3 columnas iguales */
}

.contenedor {
    display: grid;
    grid-template-columns: 2fr 1fr;  /* 2 columnas: primera el doble de la segunda */
}
```

**Función `repeat()`:**
```css
.contenedor {
    display: grid;
    grid-template-columns: repeat(3, 1fr);  /* 3 columnas iguales */
}

.contenedor {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    /* Columnas automáticas, mínimo 200px, máximo 1fr */
}
```

### 2. `grid-template-rows`
Define el número y tamaño de las filas:

```css
.contenedor {
    display: grid;
    grid-template-rows: 100px 200px;  /* 2 filas: 100px y 200px */
}
```

### 3. `gap` (antes `grid-gap`)
Espacio entre filas y columnas:

```css
.contenedor {
    display: grid;
    gap: 20px;  /* 20px entre filas y columnas */
}

.contenedor {
    display: grid;
    gap: 20px 10px;  /* 20px entre filas, 10px entre columnas */
}
```

También puedes usar:
```css
.contenedor {
    row-gap: 20px;     /* Solo entre filas */
    column-gap: 10px;  /* Solo entre columnas */
}
```

### 4. `grid-template-areas`
Define áreas nombradas del grid:

```css
.contenedor {
    display: grid;
    grid-template-columns: 1fr 3fr 1fr;
    grid-template-rows: auto 1fr auto;
    grid-template-areas:
        "header header header"
        "sidebar main aside"
        "footer footer footer";
}

.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main    { grid-area: main; }
.aside   { grid-area: aside; }
.footer  { grid-area: footer; }
```

---

## Propiedades de los Grid Items

### 1. `grid-column`
Define qué columnas ocupa un item:

```css
.item {
    grid-column: 1 / 3;  /* Desde línea 1 hasta línea 3 (ocupa 2 columnas) */
}

.item {
    grid-column: span 2;  /* Ocupa 2 columnas */
}
```

### 2. `grid-row`
Define qué filas ocupa un item:

```css
.item {
    grid-row: 1 / 4;  /* Desde línea 1 hasta línea 4 (ocupa 3 filas) */
}

.item {
    grid-row: span 2;  /* Ocupa 2 filas */
}
```

### 3. Alineación individual

```css
.item {
    justify-self: center;  /* Alineación horizontal del item */
    align-self: center;    /* Alineación vertical del item */
}
```

**Valores:** `start`, `end`, `center`, `stretch`

---

## Ejemplos Prácticos de Grid

### Layout básico de página

```css
.layout {
    display: grid;
    grid-template-columns: 200px 1fr;  /* Sidebar 200px, contenido flexible */
    grid-template-rows: 80px 1fr 60px;  /* Header 80px, main flexible, footer 60px */
    gap: 10px;
    min-height: 100vh;
}

.header  { grid-column: 1 / 3; }  /* Header ocupa ambas columnas */
.sidebar { }                      /* Sidebar en su columna */
.main    { }                      /* Main en su columna */
.footer  { grid-column: 1 / 3; }  /* Footer ocupa ambas columnas */
```

```html
<div class="layout">
    <header class="header">Header</header>
    <aside class="sidebar">Sidebar</aside>
    <main class="main">Contenido principal</main>
    <footer class="footer">Footer</footer>
</div>
```

### Galería de imágenes

```css
.galeria {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
}

.galeria img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

```html
<div class="galeria">
    <img src="foto1.jpg" alt="Foto 1">
    <img src="foto2.jpg" alt="Foto 2">
    <img src="foto3.jpg" alt="Foto 3">
    <!-- Más imágenes... -->
</div>
```

### Dashboard con áreas nombradas

```css
.dashboard {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: auto 300px 300px;
    gap: 20px;
    grid-template-areas:
        "header header header header"
        "sidebar main main stats"
        "sidebar footer footer stats";
}

.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main    { grid-area: main; }
.stats   { grid-area: stats; }
.footer  { grid-area: footer; }
```

---

## Combinando Flexbox y Grid

Es común usar ambos en el mismo proyecto:

```css
/* Grid para el layout general */
.page-layout {
    display: grid;
    grid-template-columns: 250px 1fr;
    gap: 20px;
}

/* Flexbox para la navegación */
.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* Flexbox para cards dentro del grid */
.card {
    display: flex;
    flex-direction: column;
    gap: 10px;
}
```

---

## Comparación Rápida

| Característica | Flexbox | Grid |
|----------------|---------|------|
| **Dimensiones** | Unidimensional | Bidimensional |
| **Uso principal** | Componentes, navegación | Layouts de página |
| **Control** | Basado en contenido | Basado en contenedor |
| **Alineación** | Más simple | Más control |
| **Responsive** | Wrap natural | Más explícito |
| **Soporte navegadores** | Excelente | Excelente (IE11 parcial) |

---

## Unidades de medida útiles

### Para Flexbox y Grid

- **`px`**: Píxeles fijos
- **`%`**: Porcentaje del contenedor padre
- **`fr`**: Fracción del espacio disponible (solo Grid)
- **`auto`**: Tamaño automático basado en contenido
- **`vh/vw`**: Porcentaje del viewport (100vh = altura completa de la ventana)
- **`min-content`**: Tamaño mínimo del contenido
- **`max-content`**: Tamaño máximo del contenido

### Funciones útiles

- **`minmax(min, max)`**: Define un rango de tamaño
  ```css
  grid-template-columns: repeat(3, minmax(200px, 1fr));
  ```

- **`repeat()`**: Repite un patrón
  ```css
  grid-template-columns: repeat(4, 1fr);
  ```

- **`auto-fill`**: Crea tantas columnas como quepan
  ```css
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  ```

- **`auto-fit`**: Similar a auto-fill pero colapsa tracks vacíos
  ```css
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  ```

---

## Buenas Prácticas

### Flexbox

1. **Usa `gap`** en lugar de márgenes para espaciado entre items
2. **Evita alturas fijas** en flex containers, deja que el contenido defina la altura
3. **Usa shorthand `flex`** en lugar de propiedades individuales
4. **Mobile-first**: Empieza con `flex-direction: column` y cambia a `row` en pantallas grandes

### Grid

1. **Usa `fr`** en lugar de porcentajes para distribución flexible
2. **Nombra áreas** para layouts complejos (más legible)
3. **`auto-fill` para responsive** automático sin media queries
4. **Define grid en el contenedor**, no en los items (cuando sea posible)
5. **Usa `gap`** para espaciado consistente

### General

1. **Grid para layouts**, Flexbox para componentes
2. **No uses floats** para layouts (son obsoletos)
3. **Evita positioning absoluto** para layouts principales
4. **Piensa mobile-first**: diseña para móvil primero, luego expande
5. **Usa DevTools**: Chrome/Firefox tienen excelentes inspectores de Grid y Flexbox

---

## Herramientas de Desarrollo

### Chrome/Firefox DevTools

- **Flexbox overlay**: Muestra ejes, dirección y espaciado
- **Grid overlay**: Muestra líneas, áreas y tracks
- **Inspeccionar propiedades**: Ver valores calculados en tiempo real

### Recursos Interactivos

- [Flexbox Froggy](https://flexboxfroggy.com/) - Juego para aprender Flexbox
- [Grid Garden](https://cssgridgarden.com/) - Juego para aprender Grid
- [CSS Tricks - Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS Tricks - Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)

---

## Soporte de Navegadores

### Flexbox
- Chrome 29+
- Firefox 28+
- Safari 9+
- Edge 12+
- IE 11 (con prefijos)

### Grid
- Chrome 57+
- Firefox 52+
- Safari 10.1+
- Edge 16+
- IE 11 (versión antigua con prefijos, limitada)

**Nota:** Ambas tecnologías tienen soporte prácticamente universal en navegadores modernos.

---