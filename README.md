# Concigra — Landing page

Landing de **Concigra**, plataforma independiente para la conciliación de operaciones agrícolas.

> Una operación. Múltiples fuentes. Un registro conciliado.

## Qué es

Una página estática de un solo archivo (`index.html`, sin dependencias ni build) que funciona como **one-page application**: cada sección ocupa una pantalla y se navega con:

- las pestañas numeradas de arriba,
- los botones **Anterior / Siguiente** de la barra inferior,
- las flechas ← → del teclado,
- swipe horizontal en celular.

Cada sección tiene su propia URL (`#problema`, `#ejemplo`, `#contacto`, …), así que se puede compartir un link directo a cualquiera de ellas, y el botón "atrás" del navegador funciona.

### Secciones

| # | Sección | Función |
|---|---|---|
| 01 | Inicio | Llamar la atención |
| 02 | Problema | Generar identificación |
| 03 | Costo | Mostrar importancia |
| 04 | Solución | Explicar Concigra |
| 05 | Cómo funciona | Eliminar dudas |
| 06 | Ejemplo | Demostrar |
| 07 | Valor | Justificar |
| 08 | Integraciones | Diferenciar |
| 09 | Para quién | Calificar al prospecto |
| 10 | Resultado | Mostrar el estado final |
| 11 | Confianza | Reducir riesgo |
| 12 | Contacto | CTA + formulario + cierre |

## Verla en local

Abrí `index.html` en el navegador, o levantá un servidor:

```bash
npx serve .
# o
python3 -m http.server 8080
```

## Publicarla

**GitHub Pages:** en el repo, *Settings → Pages → Build and deployment → Deploy from a branch*, elegí `main` y la carpeta `/ (root)`. Queda en `https://<usuario>.github.io/concigra-landing/`.

**Netlify / Vercel:** importá el repo; no hace falta configurar comando de build ni carpeta de salida.

## Formulario de contacto

Por defecto el formulario **no envía datos**: solo muestra el mensaje de agradecimiento. Para recibir los leads, cargá un endpoint en la primera línea del `<script>` al final de `index.html`:

```js
var FORM_ENDPOINT = 'https://formspree.io/f/XXXXXXX';
```

Funciona con cualquier servicio que acepte un `POST` con `FormData` (Formspree, Getform, Basin) o con un backend propio. Campos que se envían: `nombre`, `empresa`, `cargo`, `email`, `telefono`, `actividad`, `operacion` (múltiple), `problema`, `mensaje`.

## Pendientes

- [ ] Link de LinkedIn en el cierre (hoy apunta a `#`).
- [ ] Email de contacto en el cierre (`[EMAIL DE CONTACTO]`).
- [ ] Endpoint del formulario (`FORM_ENDPOINT`).

## Stack

HTML + CSS + JavaScript sin frameworks. Tipografías: Archivo, IBM Plex Sans e IBM Plex Mono (Google Fonts).
