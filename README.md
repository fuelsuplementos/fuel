# FUEL⚡ — Tienda online

Tienda de suplementos deportivos y healthy snacks. Sitio estático sin build, vanilla HTML + CSS + JS.

Marcas: ENA Sport, Star Nutrition, Granger Foods, Integra, Muecas, Gentech, Crudda y frutos secos.

## Estructura

```
.
├── index.html      # Página única
├── img/            # 44 imágenes de productos (WebP)
└── README.md
```

Todo el CSS y JS está embebido en `index.html` para mantener el deploy simple.

## Probarlo localmente

Abrí `index.html` en el navegador (doble clic). No hace falta servidor.

Si querés un servidor local (recomendado para que el lazy-loading y los caches funcionen igual que en producción):

```bash
# Python 3
python -m http.server 8000

# Node
npx serve .
```

Después abrís `http://localhost:8000`.

## Deploy en GitHub Pages

1. Subir el repo a GitHub.
2. En el repo: **Settings → Pages**.
3. **Source**: "Deploy from a branch", **Branch**: `main`, **Folder**: `/ (root)`.
4. Guardar. En 1-2 minutos queda en `https://<usuario>.github.io/<repo>/`.

## Funcionalidades

- **Catálogo** con 44 productos filtrables por categoría y marca (sidebar drawer).
- **Carrito** con cantidades, código de descuento (`LOSMORUGBY` = -5%) y recargo automático del 5% por tarjeta.
- **Checkout** que arma el pedido y lo envía por WhatsApp al `+54 11 6520-1776`.
- Vista del grid configurable (1 / 2 / 3 columnas).
- Modal de pedido individual también disponible (botón "Encargar →" en cada card).
- Responsive con breakpoints en 1024px / 768px / 480px.

## Cambiar el número de WhatsApp

Está como constante `WA_NUMBER` cerca del inicio del `<script>` en `index.html`, y como atributo `href="https://wa.me/541165201776"` en 3 lugares (nav-hero "Escribinos", footer y FAB flotante).

## Cambiar el código de descuento

En `index.html` buscar:

```js
const DISCOUNT_CODE = 'LOSMORUGBY';
const DISCOUNT_PCT = 5;
```

## Stack

- HTML + CSS + JS vanilla (sin frameworks).
- Google Fonts: Bebas Neue (titulares), DM Sans (texto), Inter (números/precios con `tabular-nums`).
- Imágenes WebP (calidad 85, ~1 MB total).
