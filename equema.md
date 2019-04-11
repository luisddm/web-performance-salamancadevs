Disclaimer: sencillo para unos, wow para otros
No hay blanco y negro, todo depende
Adaptarme al público la próxima vez

En el mundo real no es como en condiciones ideales
Problemas ancho de banda y moviles de mil tipos

Dos asuntos a tratar
- Ancho de banda, no todo el mundo tiene acceso a velocidades de gran ciudad
- Dispositivos, no todo el mundo tiene el ultimo iphone

Eliminar carga innecesaria para mejorar velocidad y reducir tamaño

Optimizar el first meaningful paint

NO BOOTSTRAP

# Minificar y comprimir
- Gulp, grunt, webpack
- UglifyJS o CDN

# Politicas de cacheado eficientes
- ETag header alto para imágenes, fuentes

# Código que no se usa
- Eliminar CSS de forma segura con tests

First meaningful paint??
First interactive
Consistently interactive

JS critical path?

Establecer presupuestos para JS, CSS e imágenes

La request más rápida es la que no se hace

# Inventario de assets
import-cost para VSCode
webpack bundle analyzer (npm run build --report
BundlePhobia)

# JS es lo más costoso!
- Descargar, parsear, compilar, ejecutar.
- Especialmente dañino en móviles de gama media-baja
- splitear por ruta o componente, imports dinámicos
- ejemplo, lodash: cargar solo funciones que usamos
- tree-shaking
- js moderno a los navegadores modernos

# Imagenes
- balance tamaño/calidad
- Usar WebP o JPG para fotos, PNG logos, SVG mejor
- ImageOptim, XNConvert, GIMP, imagemin (gulp), otras de npm (svgo, ...
- Nunca GIFs animados (enseñar twitter, emosido engañados) -> MPEG, WebM
  usar tag video con varios formatos si es posible
  ffmpeg -i animation.gif -b:v 0 -crf 40 -vf scale=600:-1 video.mp4
- Lazy loading con scroll u otras técnicas (ejemplo, slider)
- <img srcset>, <picture>, media queries
- eliminar metadata, guardar como progressive 

Usar https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/effectiveType para saber ancho banda

# prefetching-preloading-prebrowsing
- https://css-tricks.com/prefetching-preloading-prebrowsing/
- ejemplo, para fuentes desde google fonts -> preconnect
- <link rel="preload" as="font" href="webfont.woff2" type="font/woff2" crossorigin="anonymous">
- con preload, se cargan fuentes mientras otras cosas
- webpack 4.6 (prefetch, preload)
- selhostear fuentes
- svgs en lugar de fuentes de iconos

# evitar texto blanco mientras carga fuentes
- font-display: swap

marcar scripts no críticos con defer
evitar demasiados nodos en html
evitar redirecciones 

critical path CSS https://www.sitelocity.com/critical-path-css-generator

http2
https://developers.google.com/web/fundamentals/performance/prpl-pattern/

predecir navegación -> prefetch