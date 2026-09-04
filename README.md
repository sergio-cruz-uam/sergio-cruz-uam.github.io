# Web académica de Sergio Cruz Blázquez

La web está hecha únicamente con HTML y CSS. No hay que instalar programas ni ejecutar un proceso de construcción: los cambios publicados en la rama principal de GitHub se reflejan directamente en GitHub Pages.

Dirección pública: <https://sergio-cruz-uam.github.io/>

## Dónde se edita cada cosa

- `index.html`: portada, fotografía y datos de contacto.
- `docencia.html`: asignaturas y materiales descargables.
- `cv.html`: currículum académico.
- `styles.css`: aspecto visual y adaptación a móviles. Normalmente no hace falta tocarlo.
- `assets/apuntes`: archivos PDF, cuadernos y otros materiales docentes.
- `assets/img`: fotografía, iconos e imágenes.

Los tres archivos HTML contienen comentarios invisibles que empiezan por `GUÍA DE EDICIÓN`, `NUEVO MATERIAL`, `NUEVA ASIGNATURA` o `NUEVA PUBLICACIÓN`. Se pueden buscar con `Ctrl+F` para llegar directamente al lugar correcto.

## Añadir unos apuntes o un examen

1. Guarde el archivo en la carpeta de la asignatura dentro de `assets/apuntes`. Por ejemplo:

   `assets/apuntes/2025-2026/calculoI-mat/tema-4.pdf`

2. Abra `docencia.html` y busque el comentario `NUEVO MATERIAL` de esa asignatura.
3. Copie uno de los bloques comprendidos entre `<li>` y `</li>` y cambie solo el enlace, el título, la descripción y el tipo de archivo.

```html
<li>
  <a href="assets/apuntes/2025-2026/calculoI-mat/tema-4.pdf">
    <span><strong>Tema 4</strong><small>Notas de clase</small></span>
    <span class="file-type">PDF</span>
  </a>
</li>
```

El nombre escrito en `href` debe coincidir exactamente con el nombre y la ruta del archivo.

## Añadir una asignatura o un curso académico

Para añadir otra asignatura, copie un bloque completo desde `<article class="course-card">` hasta su `</article>` y cambie el código, el nombre, la titulación y los materiales.

Para abrir un nuevo curso académico, copie una sección completa desde `<section class="year-section" ...>` hasta su `</section>`. Después:

1. Cambie el identificador en `id`, por ejemplo a `curso-2026-2027`.
2. Cambie el `aria-labelledby` y el `id` del título para que ambos usen el mismo año.
3. Añada el nuevo curso al pequeño índice que aparece al principio de `docencia.html`.

## Añadir una entrada al CV

Abra `cv.html` y busque el comentario correspondiente a la sección.

- Puestos y formación usan bloques `<article class="timeline-item">`.
- Publicaciones usan un bloque `<li>` completo dentro de `publication-list`. La numeración se actualiza automáticamente.
- Docencia, proyectos, comunicaciones y cursos usan bloques `<li>` dentro de la lista de su sección.

Ejemplo de nuevo puesto:

```html
<article class="timeline-item">
  <p class="date">September 2026 – Present</p>
  <h3>Position · University</h3>
  <ul>
    <li>Department or project information.</li>
  </ul>
</article>
```

Ejemplo de nueva publicación:

```html
<li>
  <article class="publication">
    <p>Authors. <strong>Article title</strong>, <em>Journal</em>, volume, pages and year.</p>
    <a href="https://doi.org/DOI" target="_blank" rel="noopener noreferrer">doi:DOI</a>
  </article>
</li>
```

Las métricas bibliométricas son opcionales. Si se desean, copie también el bloque `<details class="metrics">` de otra publicación.

## Cambiar la portada

En `index.html`:

- El texto bajo la foto está dentro de `<span class="portrait-caption">`.
- El cargo está en el párrafo con `class="role"`.
- El correo, despacho, dirección institucional y perfiles están en `contact-list`.

Para sustituir la foto, reemplace `assets/img/sergio.jpg` por otra imagen con el mismo nombre. Si cambia el nombre del archivo, actualice también el atributo `src` de la imagen en `index.html`.

## Publicar los cambios

Con GitHub Desktop:

1. Revise que solo aparecen los archivos que quería modificar o añadir.
2. Escriba un resumen breve en el campo de descripción del cambio.
3. Pulse **Commit to main**.
4. Pulse **Push origin**.

Antes de publicar, conviene abrir `index.html`, `docencia.html` y `cv.html` en el navegador y comprobar los enlaces que se hayan añadido.
