# Ruta Libre — Carga Pesada MX (PWA)

Esta carpeta es una app web instalable (PWA): funciona offline y se puede
"Agregar a pantalla de inicio" en celular o instalar como app de escritorio.

Contiene:
- `index.html` — la app (autocontenida, no requiere build ni npm)
- `manifest.json` — nombre, ícono y colores para la instalación
- `sw.js` — service worker (cache offline)
- `icon-192.png`, `icon-512.png`, `icon-512-maskable.png` — íconos

## Por qué necesitas publicarla (un paso único)

Los navegadores solo ofrecen "Instalar app" cuando el sitio se sirve por
**HTTPS** desde un dominio real — no funciona abriendo el archivo
`index.html` directamente desde tu computadora. Elige una opción gratuita:

### Opción A — Netlify Drop (la más rápida, sin cuenta)
1. Entra a **https://app.netlify.com/drop**
2. Arrastra esta carpeta completa a la página.
3. Netlify te da una URL tipo `https://tu-app.netlify.app` en segundos — ya instalable.

### Opción B — Vercel o GitHub Pages
1. Sube esta carpeta a un repositorio de GitHub.
2. En GitHub Pages: Settings → Pages → selecciona la rama y carpeta raíz.
3. En Vercel: importa el repo desde vercel.com — detecta un sitio estático automáticamente.

### Opción C — Probarla localmente primero
```bash
cd ruta-libre
python3 -m http.server 8000
```
Abre `http://localhost:8000` en tu navegador. Verás la app funcionando,
pero el botón "Instalar" solo aparece cuando ya está en HTTPS (opción A o B).

## Cómo instalarla una vez publicada

- **Android (Chrome)**: abre la URL → menú (⋮) → "Instalar app" o "Agregar a pantalla de inicio".
- **iPhone (Safari)**: abre la URL → botón compartir (□↑) → "Agregar a pantalla de inicio".
- **Escritorio (Chrome/Edge)**: abre la URL → ícono de instalación (⊕) en la barra de direcciones.

Una vez instalada, abre como cualquier app, con ícono propio y sin barra del navegador.

## Actualizar el contenido

Los horarios y datos de restricción están en el bloque `CIUDADES`,
`CAMINOS_FEDERALES` y `TEMPORADAS` dentro de `index.html`. Edítalos ahí
y vuelve a publicar (arrastra de nuevo a Netlify, o haz `git push`).
