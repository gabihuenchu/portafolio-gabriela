Portafolio · Gabriela Huenchullán

Sitio estático minimalista y responsive para presentar perfil profesional, proyectos y un formulario de contacto operativo.

Demo
- Producción: `https://portafolio-gabrielahuenchullan.netlify.app/`

Estructura del proyecto
- `index.html` — página principal
- `gamer-zone.html` — subpágina con galería del proyecto App Gamer Zone
- `assets/` — imágenes usadas en ambas páginas
  - `about01.jpg`, `logosumma.png`, `pikunkaru.png`, `treffen.png.jpg`, `tuscuentos.png`, `1.png`–`5.png`

Tecnologías
- HTML5 + CSS (inline)
- JavaScript nativo (inline)
- Hosting: Netlify
- Formulario: FormSubmit (AJAX y fallback por `action`)

Páginas
- `index.html`
  - Header fijo con navegación interna
  - Secciones: Hero, Sobre mí, Habilidades, Proyectos, Contacto, Footer
  - Estilos responsive con `@media` para 1024px y 640px
  - Metadatos SEO y Open Graph/Twitter
  - Formulario de contacto con envío real y pop‑up de éxito
- `gamer-zone.html`
  - Header sticky con enlace de retorno
  - Galería vertical con 5 imágenes (`assets/1.png`–`assets/5.png`)

Secciones principales (index.html)
- Header/Nav: navegación a `#home`, `#about`, `#projects`, `#contact`
- Hero: presentación y CTA “Ver trabajos”
- Sobre mí: descripción y bloque “Summa Estudio de Diseño”
- Habilidades: grid de 6 tarjetas (Diseño Web, Gráfico, UI/UX, Webflow, HTML/CSS, Identidad visual)
- Proyectos: 4 tarjetas con imagen, rol y enlace externo
- Contacto: formulario con Nombre, Email y Mensaje; información de contacto adicional
- Footer: copyright dinámico por año

Estilos y diseño
- Variables CSS (tema oscuro): `--bg`, `--surface`, `--text`, `--muted`, `--accent`, `--accent-2`, `--border`, `--maxw`, `--radius`
- Layouts: grids para hero, skills, projects y contact
- Estados hover y micro‑animación (transform y filter)

Accesibilidad
- Atributos ARIA de roles y labels (por ejemplo, `aria-label` en el formulario)
- `aria-live` para feedback del formulario
- Modal accesible: `role="dialog"`, `aria-modal`, `aria-labelledby`, `aria-describedby`

Formulario de contacto
- Ubicación: `index.html:237`
- Estructura: `form#contact-form` con campos `name`, `email`, `message` y `required`
- Envío real:
  - `action`: `https://formsubmit.co/73b9024b96f247cafba18692eef846bd`
  - AJAX: `fetch('https://formsubmit.co/ajax/73b9024b96f247cafba18692eef846bd', ...)`
  - Respuesta de éxito: resetea el formulario y abre el pop‑up
- Ocultos de configuración:
  - `_subject`: “Nuevo contacto desde el portafolio”
  - `_captcha`: `false`
  - `_template`: `table`
  - `_autoresponse`: “Gracias por tu mensaje. Te escribiré pronto.”
- Pop‑up de éxito:
  - Estilos: `.modal-overlay`, `.modal` dentro de `index.html:110`
  - Apertura: al completar envío AJAX con `success === 'true'`
  - Cierre: botón “Cerrar”, tecla Escape o clic fuera

Metadatos SEO
- `meta name="description"`: descripción del portafolio
- Open Graph: `og:type`, `og:site_name`, `og:title`, `og:description`, `og:url`, `og:image`
- Twitter: `twitter:card`, `twitter:title`, `twitter:description`, `twitter:image`
- `link rel="canonical"`: `https://portafolio-gabrielahuenchullan.netlify.app/`

Cómo ejecutar localmente
- Requisitos: Python 3 o cualquier servidor estático
- Ejecutar: `python -m http.server 8000`
- Abrir: `http://localhost:8000/`

Despliegue en Netlify
- Arrastrar la carpeta del proyecto en `https://app.netlify.com/drop`
- Asegurarse de que `index.html` esté en la raíz
- Opcional: configurar dominio personalizado y redirecciones

Activación de FormSubmit
- Paso único: hacer clic en “Activate Form” desde el correo de FormSubmit
- Token usado: `73b9024b96f247cafba18692eef846bd`
- Tras activar, los envíos funcionan tanto por `action` como por AJAX

Personalización sugerida
- Branding del modal (colores y logo)
- Página de “gracias” (`_next`) como alternativa al pop‑up
- Captcha/honeypot si aumenta el tráfico
- Ajuste de `canonical`/OG al dominio propio definitivo

- Diseño y desarrollo: Gabriela Huenchullán

