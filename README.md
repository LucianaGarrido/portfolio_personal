# Portfolio — Luciana Garrido

Sitio personal de **Luciana Garrido**, diseñadora gráfica & UX/UI (Mendoza, Argentina).
Una sola página, HTML/CSS/JS puro, sin frameworks ni dependencias externas.

🔗 **Demo:** _(pegá acá la URL cuando lo publiques)_

---

## Estructura

```
portfolio-luciana-garrido/
├── index.html                  ← toda la página (estructura, estilos y scripts)
├── netlify.toml                ← config de deploy para Netlify
├── .gitignore
├── .nojekyll                   ← necesario para GitHub Pages
└── assets/
    ├── patron-stickers.svg     ← trama de fondo (ilustraciones originales)
    ├── fonts/
    │   ├── bagel.woff2         ← Bagel Fat One (títulos)
    │   ├── familjen.woff2      ← Familjen Grotesk (subtítulos)
    │   └── karla.woff2         ← Karla (textos)
    └── img/
        ├── luciana-hero.webp
        ├── luciana-sobre.webp
        ├── club-01…17.webp
        ├── vicencio-01…11.webp
        ├── ades-01…30.webp
        ├── menduco-01…14.webp
        ├── dogue-01.webp
        └── blueberry-01.webp
```

---

## Publicar

### Opción A — Netlify (recomendada)

1. Subí esta carpeta a un repositorio de GitHub.
2. Entrá a [app.netlify.com](https://app.netlify.com) → **Add new site** → **Import an existing project**.
3. Elegí el repositorio. Dejá el build command vacío y el publish directory en `.` (ya está definido en `netlify.toml`).
4. **Deploy**. Cada push a `main` republica el sitio solo.

También podés arrastrar la carpeta entera a [app.netlify.com/drop](https://app.netlify.com/drop) sin usar Git.

### Opción B — GitHub Pages

1. Subí la carpeta al repositorio.
2. **Settings** → **Pages** → Source: `Deploy from a branch` → Branch: `main` / carpeta `/ (root)`.
3. Guardá. En un par de minutos queda en `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`.

---

## Cómo editar

Todo se cambia dentro de `index.html`, que está dividido en bloques comentados.

**Colores** — bloque `TOKENS`, arriba de todo:

```css
--red:#E03C2D;   --orange:#F26522;  --coral:#F4815C;
--pink:#F58BC0;  --pink-lt:#FBD3E4; --cream:#FBEEE2;  --ink:#2A0E0A;
```

**Tipografías** — variables `--display`, `--sub` y `--body`. Para cambiarlas hay que
reemplazar el `.woff2` correspondiente en `assets/fonts/` y ajustar el `@font-face`.

**Proyectos** — array `GALLERIES` al inicio del `<script>`. Cada proyecto tiene:

| campo | qué hace |
|---|---|
| `title` | nombre del proyecto |
| `meta` | cátedra o cliente + año |
| `desc` | descripción corta |
| `tags` | etiquetas del pie |
| `free` | `true` = badge rosa "Freelance"; `false` = "Académico" |
| `images` | rutas de las páginas, en orden |
| `ratio` | ancho ÷ alto de la pieza (**importante**: define el ancho de la tarjeta) |

Para sumar un proyecto: guardá las imágenes en `assets/img/`, agregá el objeto al array
y calculá el `ratio` dividiendo el ancho por el alto de la primera página.

**Textos y experiencia** — están escritos directo en el HTML, en las secciones
`#sobre`, `#skills` y `#trayectoria`.

**Contacto** — sección `#contacto`: mail, WhatsApp (`wa.me`), LinkedIn y Behance.

---

## Notas técnicas

- Las tipografías están subseteadas a latín + latín extendido y embebidas en el repo:
  no hay llamadas a Google Fonts, así que el sitio funciona sin conexión y no filtra
  datos de visitantes a terceros.
- Las imágenes están en WebP, redimensionadas a tamaño de pantalla. Las páginas de los
  manuales y las miniaturas del visor usan `loading="lazy"`.
- Las ilustraciones de animalitos son SVG originales, definidas como `<symbol>` al
  principio del `<body>`.
- El scroll horizontal de proyectos usa `position: sticky` + `transform`, sin librerías.
- **Accesibilidad:** el sitio no respeta `prefers-reduced-motion` (decisión de diseño).
  Si en algún momento querés activarlo, envolvé las animaciones en
  `@media (prefers-reduced-motion: no-preference)`.

---

© 2026 Luciana Garrido. El código es libre de reutilizar; las piezas de diseño y las
fotografías no.
