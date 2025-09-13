# 🚀 TecsyNet — Sitio corporativo (HTML + CSS puro)

**Technology Systems for Internet** — _“Making I.T. happens”_

- 🏗️ **Stack**: HTML + CSS (sin frameworks, sin build).
- 📅 **Fundación**: 2011
- 👥 **Co‑fundadores**: Ing. **Iván Valdivieso** (CEO) · Ing. **Adrián Correa** (CTO)
- 🧰 **Servicios**: Desarrollo Web · VoIP/Asterisk · IoT/Arduino

---

## ✨ Características
- ⚡ **Rápido y liviano** (cero dependencias).
- 📱 **Responsive** y limpio.
- 🔎 **SEO listo**: Open Graph/Twitter, `canonical`, JSON‑LD (Organization).
- ♿ **Accesible**: *skip link* y soporte a *reduced motion*.
- ✉️ **Formulario real** con **Formspree** + página `gracias.html`.
- 🗺️ `sitemap.xml` y `robots.txt` listos para GitHub Pages.

---

## 📂 Estructura
```
.
├─ index.html
├─ styles.css
├─ gracias.html
├─ robots.txt
├─ sitemap.xml
└─ assets/
   ├─ favicon.ico
   ├─ logo.png
   ├─ header1.png        (imagen principal del héroe)
   └─ cabezote.png       (fallback del héroe)
```

---

## 🚀 Publicación (GitHub Pages)
1. **Settings → Pages**.
2. **Build and deployment → Source**: `Deploy from a branch`.
3. **Branch**: `main` · **Folder**: `/(root)`.
4. URL de publicación: `https://<usuario>.github.io/<repo>/` → para este repo: `https://ivanosito.github.io/tecsynet/`

> Cada `git push` a `main` despliega automáticamente.

### 🌐 Dominio propio (opcional)
- Crea archivo **`CNAME`** en la raíz con tu dominio (p. ej. `tecsynet.com`).
- Configura los **DNS** según la guía de GitHub Pages (A/AAAA/CNAME).
- Activa **Enforce HTTPS** cuando esté disponible.

---

## 🧪 Pruebas del formulario (Formspree)
**Endpoint:** `https://formspree.io/f/xqadjgwo`

### ✅ Producción
Prueba desde **Pages**: `https://ivanosito.github.io/tecsynet/`

En `<head>` se recomienda mantener:
```html
<meta name="referrer" content="origin">
```
Así Formspree recibe `Origin/Referer` con tu dominio y evita falsos positivos de spam.

### 🧑‍💻 Local
No abras el HTML con doble clic (`file://`). Levanta un servidor:
```bash
python -m http.server 8000
# http://localhost:8000
```
Si tu plan de Formspree lo permite, agrega **localhost** o un túnel (ngrok) a dominios permitidos.

### 🔍 Verificación rápida
- DevTools → **Network** → request a `formspree.io` → Headers deben incluir:
  - `Origin: https://ivanosito.github.io`
  - `Referer: https://ivanosito.github.io/tecsynet/...`

---

## ✉️ Fragmento del formulario
```html
<form class="contact-form" action="https://formspree.io/f/xqadjgwo" method="POST">
  <input type="hidden" name="_subject" value="Nuevo contacto desde TecsyNet">
  <input type="hidden" name="_language" value="es">
  <input type="hidden" name="_redirect" value="gracias.html">
  <input type="text" name="_honey" style="display:none" tabindex="-1" autocomplete="off" aria-hidden="true">

  <div class="grid form-grid">
    <label><span>Nombre</span><input name="name" type="text" required placeholder="Tu nombre"></label>
    <label><span>Correo</span><input name="email" type="email" required placeholder="tu@empresa.com"></label>
    <label class="full"><span>Mensaje</span><textarea name="message" rows="5" required placeholder="Describe brevemente tu necesidad"></textarea></label>
  </div>
  <button class="btn" type="submit">Enviar</button>
</form>
```

---

## 🎨 Personalización rápida
- 🎯 **Colores**: ajusta variables en `:root` de `styles.css`.
- 🔤 **Tipografía**: cambia el `link` de Google Fonts en `<head>`.
- 🖼️ **Héroe**: sustituye `assets/header1.png` (hay *fallback* automático a `cabezote.png`).

### 📐 Tamaños recomendados
- **Hero / OG image**: `1200×630` px (ratio ~1.91:1).
- **Logo**: PNG/SVG con transparencia (`≥256×256`).
- **Favicon**: `.ico` multi‑tamaño (16/32/48 px).

---

## 🔎 SEO & Social
Incluido en `<head>`:
- `meta description`, Open Graph / Twitter Cards, `canonical`, `theme-color`.
- **JSON‑LD** `Organization` (nombre, fundación 2011, co‑fundadores).

Checklist extra:
- Títulos/descripciones únicos si creas subpáginas.
- `alt` descriptivos en imágenes.
- Comprimir imágenes (PNG‑8 / WebP).
- Analytics opcional (Plausible, Umami, Cloudflare).

---

## ♿ Accesibilidad
- 🔗 **Skip link**: “Saltar al contenido”.
- 🧘 *Reduced motion*: respeta `prefers-reduced-motion`.
- 📝 Formularios con `label` y `required`.

---

## ☎️ Botón de WhatsApp (opcional)
```html
<a class="btn" href="https://wa.me/57XXXXXXXXXX?text=Hola%20TecsyNet%2C%20quiero%20una%20cotizaci%C3%B3n"
   target="_blank" rel="noopener">Escríbenos por WhatsApp</a>
```
> Reemplaza `57XXXXXXXXXX` por tu número con código de país.

---

## 🧰 Troubleshooting
- 🧵 **Se ve “todo en fila”** → el CSS no cargó:
  - En `<head>` usa: `<link rel="stylesheet" href="./styles.css?v=3">`
  - Comprueba que el archivo se llame **exactamente** `styles.css` (sensible a mayúsculas/minúsculas).
  - Abre `https://<usuario>.github.io/<repo>/styles.css` y verifica que responde (no 404).
- 🖼️ **Hero roto** → revisa que exista `assets/header1.png` (o quedará el fallback `cabezote.png`).
- 🔏 **Formspree “Unauthorized domain: null”** → estabas en `file://` o sin `Referer`. Prueba desde Pages y deja `<meta name="referrer" content="origin">`.

---

## 🧭 Roadmap (ideas)
- 🌙 Modo oscuro (`prefers-color-scheme`).
- 🗂️ Página de proyectos detallados.
- 💬 Testimonios y logos de clientes.
- 📝 Blog/noticias simple (MD + generador estático si se desea).
- 🔒 Política de privacidad y términos.

---

## 🤝 Contribución
1. Crea una rama: `git checkout -b feature/nombre`  
2. Commit: `git commit -m "feat: descripción"`  
3. Push: `git push -u origin feature/nombre`  
4. Abre un Pull Request.

---

## © Licencia / Marca
Contenido y marca **TecsyNet**.  
© 2011–2025 TecsyNet. Todos los derechos reservados.
