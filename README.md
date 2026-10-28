# Landing · Programa de pilotos de agentes de IA

Sitio estático (HTML, CSS y JS sin dependencias) en español, inglés y portugués, con modo claro y oscuro, lista de espera y política de privacidad.

## Estructura

```
index.html            Landing completa (textos, estilos y lógica)
404.html              Página de error
vercel.json           Cabeceras de seguridad, caché y redirecciones (/privacidad)
robots.txt
assets/img/           Fotos, pósters de video e imagen para redes (og.jpg)
assets/video/         Videos del hero y de la banda (720p, sin audio)
assets/fonts/         Tipografías alojadas en el propio sitio (sin Google Fonts)
```

## Antes de publicar: edita el bloque `CONFIG` en `index.html`

Busca `CONFIGURACIÓN: edita solo este bloque` dentro de `index.html`:

| Campo | Qué poner |
|---|---|
| `brand` | `yupana`, `veta`, `ceque` o `cauce` |
| `theme` | `petroleo`, `faena` u `oxido` |
| `mode` | `auto` (según el dispositivo), `light` o `dark` |
| `formEndpoint` | URL del formulario (por ejemplo `https://formspree.io/f/xxxx`). Si queda vacío, se abre el correo del visitante. |
| `contactEmail` | Correo que recibe la lista de espera si no hay endpoint |
| `showDock` | `false` para ocultar el botón “Estilo y marca” cuando ya elegiste |
| `legal.*` | Razón social, RUC, domicilio, correo de privacidad, código del banco de datos y proveedor del formulario. Lo que esté entre `[corchetes]` aparece resaltado en la página hasta que lo completes. |

### Si usas un proveedor de formulario distinto a Formspree

`vercel.json` limita a qué dominios puede enviar datos la página. Cambia `https://formspree.io` en la línea `connect-src` por el dominio de tu proveedor (por ejemplo `https://api.tally.so`). Si no lo cambias, el navegador bloqueará el envío.

## Publicar

1. Crea un repositorio en GitHub y sube el contenido de esta carpeta (que `index.html` quede en la raíz).
2. En Vercel: **Add New → Project → Import** el repositorio.
3. Framework Preset: **Other**. Sin Build Command. Output Directory: la raíz (vacío o `.`).
4. **Deploy**. Cada `git push` a `main` vuelve a publicar.
5. Opcional: en **Settings → Domains** conecta tu dominio.

## Probar en tu computadora

Puedes hacer doble clic en `index.html` siempre que la carpeta `assets/` esté al lado. Todas las rutas son relativas, así que también funciona en GitHub Pages y en Vercel.

## Comprobar que subiste todo bien

En GitHub, la raíz del repositorio debe verse así (no dentro de otra carpeta):

```
assets/
404.html
README.md
index.html
robots.txt
vercel.json
```

Y `assets/` debe tener tres carpetas: `fonts`, `img` y `video`. Si al abrir `https://TU-SITIO/assets/img/mineria.jpg` ves la foto, los recursos están publicados.

## Enlaces útiles

- Política de privacidad: `/privacidad` (también `/privacy` y `/privacidade`)
- Forzar idioma, estilo o modo: `/?lang=en&theme=oxido&mode=dark&brand=veta`
