# Libertyfin — Sitio Web

## Estructura del proyecto

```
libertyfin/
├── index.html                          ← Página principal
├── css/
│   ├── main.css                        ← Estilos globales (navbar, footer, botones)
│   └── index.css                       ← Estilos exclusivos del inicio
├── js/
│   ├── shared.js                       ← Navbar, footer y WhatsApp (todas las páginas)
│   └── index.js                        ← Scripts exclusivos del inicio
├── pages/
│   ├── precios.html
│   ├── distribuidores.html
│   ├── punto-de-venta.html
│   ├── facturacion.html
│   ├── inventario.html
│   ├── clientes.html
│   ├── cotizaciones.html
│   ├── reportes.html
│   └── clientes-casos.html
└── img/                                ← TU CARPETA DE IMÁGENES
    ├── logo-libertyfin.png             ← Logo principal (navbar + footer)
    ├── Logo_-_img.png                  ← Logos de clientes
    ├── logo_transt_Mesa_de_trabajo_1__1_.png
    ├── LOGO-02.png
    └── LOGOS_check-03__1_.png
```

---

## ¿Cómo agregar tu logotipo?

### Especificaciones recomendadas

| Uso | Tamaño | Formato |
|-----|--------|---------|
| Navbar (barra superior) | 160 × 36 px | PNG con fondo transparente |
| Footer | 140 × 32 px | PNG con fondo transparente |
| Favicon | 32 × 32 px | ICO o PNG |

### Pasos

1. **Prepara tu logo** en PNG con fondo transparente (`.png`)
2. Nómbralo: `logo-libertyfin.png`
3. Colócalo en la carpeta `img/`
4. En `js/shared.js` busca la línea del navbar con el logo SVG y reemplázala:

**Antes (SVG genérico):**
```html
<div class="nav-logo-icon">
  <svg viewBox="0 0 28 28" ...>...</svg>
</div>
<span class="nav-logotype">Libertyfin<span>.</span></span>
```

**Después (con tu imagen):**
```html
<img src="../img/logo-libertyfin.png" alt="Libertyfin" class="nav-logo-img">
```

*(En `index.html` la ruta sería `img/logo-libertyfin.png` sin el `../`)*

### Ajuste de tamaño en CSS (`css/main.css`)

```css
/* Tamaño del logo en navbar */
.nav-logo-img {
  height: 36px;      /* Ajusta entre 28px y 44px */
  width: auto;
  max-width: 160px;
  object-fit: contain;
}

/* Tamaño del logo en footer */
.footer-logo-img {
  height: 32px;
  width: auto;
  max-width: 140px;
  object-fit: contain;
  filter: brightness(0) invert(1); /* Invierte a blanco para footer oscuro */
  opacity: 0.85;
}
```

---

## WhatsApp

En `js/shared.js` busca y cambia el número:
```js
window.open('https://wa.me/521XXXXXXXXXX?text=' + msg, '_blank');
```
Reemplaza `521XXXXXXXXXX` con tu número en formato internacional (ej: `5215512345678`).

---

## Publicar en GitHub Pages

1. Sube toda la carpeta a un repositorio público en GitHub
2. Ve a **Settings → Pages → Branch: main → / (root)**
3. Tu sitio estará en: `https://tu-usuario.github.io/libertyfin/`
