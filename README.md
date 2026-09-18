# 🎬 My Profile Cine & TV

Landing page centralizada tipo *Linktree* para concentrar mis perfiles de contenido audiovisual: **Letterboxd** (películas) y **Serializd** (series), con un cielo estrellado animado de fondo (deriva, parallax, titileo y estrellas fugaces).

## 🧪 Stack

* **Astro 7** — arquitectura de componentes, 0 JS por defecto en cliente salvo lo necesario.
* **Tailwind CSS v4** — tokens en `@theme` (paleta nocturna, glows y fuentes).
* **Canvas 2D** — cielo estrellado dinámico sin dependencias (60fps, `prefers-reduced-motion` respetado).
* **astro-icon + lucide** — iconos SVG inlined en build.
* **@fontsource-variable** — Inter y Outfit auto-alojadas (sin render-blocking).

## 📁 Estructura

```text
my-profile-cine/
├── src/
│   ├── layouts/BaseLayout.astro     # <head>, SEO/OG, fuentes, estilos
│   ├── components/
│   │   ├── Starfield.astro          # cielo estrellado (canvas + parallax)
│   │   ├── ProfileHeader.astro      # avatar, bio, compartir perfil + toast
│   │   ├── PlatformCard.astro       # tarjeta reutilizable (props + acento)
│   │   └── SeriesGrid.astro         # mis 4 series favoritas (data-driven)
│   ├── pages/index.astro            # composición de la landing
│   └── styles/global.css            # tokens Tailwind v4 + keyframes
├── public/favicon.svg
├── astro.config.mjs
├── vercel.json
└── package.json
```

## ⚙️ Comandos

```bash
pnpm install       # instalar dependencias
pnpm dev           # desarrollo local (http://localhost:4321)
pnpm build         # build estático en dist/
pnpm preview       # previsualizar el build
pnpm check         # type-check con @astrojs/check (astro check)
```

## 🔗 Personalización

* **Usuarios:** en `src/pages/index.astro` están `letterboxd.com/Hater_movies/` y `serializd.com/user/Hater_shows/profile`.
* **Avatar:** `AVATAR` en `src/components/ProfileHeader.astro`.
* **Series:** array `series` en `src/components/SeriesGrid.astro` (título, seed de imagen y rating).
* **URL del sitio:** `site` en `astro.config.mjs` (≈ URL final de Vercel).

## 🚀 Deploy (Vercel)

1. Empuja este repo a GitHub y conéctalo en [vercel.com](https://vercel.com).
2. Vercel detecta Astro automáticamente (`pnpm build`, output `dist/`, static).
3. Actualiza `site` en `astro.config.mjs` con tu dominio final.

La receta original está en `instruction/project_documentation.md`.