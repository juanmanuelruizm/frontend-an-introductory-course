# 🧱 Mi primer archivo en formato .html

Vamos a crear un archivo **HTML** para abrir desde nuestro navegador local.  
No esperes mucho de aquí, pues va a ser algo muy sencillo.

---

## 🗂️ Creación del archivo

Para empezar, necesitamos crear un archivo en formato `.html`.  
Esto es tan sencillo como ir a nuestro IDE y, dentro del directorio donde estemos trabajando, crear un nuevo archivo:

- Le damos un **nombre** (por ejemplo, `index`).
- Le asignamos el **formato** que buscamos: `.html`.


---

## 💻 Estructura básica de un documento HTML

Una vez tengamos el archivo creado, empezamos a escribir en él.  
El contenido será el siguiente:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Mi primera página HTML</title>
  </head>
  <body>
    <h1>Hola Mundo</h1>
    <h2>Mi primera página web</h2>
    <p>Este es un ejemplo sencillo de HTML.</p>
  </body>
</html>
```

## 🧩 Explicación de las partes

```markdown

- <!DOCTYPE html>: Indica al navegador que se trata de un documento HTML. 

- <html> ... </html>: Marca el inicio y el final del contenido HTML. 
- <head> ... </head>: Contiene información que no se muestra directamente en el navegador, como: El título de la pestaña (definido con <title>). Enlaces a hojas de estilo (.css) u otros metadatos. 
- <body> ... </body>: Contiene todo el contenido que sí se mostrará en la página, como: Títulos principales (<h1>), Subtítulos (<h2>), Párrafos (<p>).

```

Una vez tenemos esto, podemos abrir desde nuestro navegador local el archivo index.html y podremos ver el contenido de este.