# Fotos a KMZ — notas para Claude

PWA: fotos con GPS EXIF → KMZ para Google Earth, todo en el navegador.
Repo `cvenegas-sernageomin/fotos-a-kmz` (rama `main`) → https://cvenegas-sernageomin.github.io/fotos-a-kmz/
Ficha en memoria: `proyecto-fotos-a-kmz-pwa`.

## Reglas
- Un solo `index.html` sin build + `sw.js` (`CACHE='fotos-a-kmz-vN'`, subirlo en cada cambio) + `vendor/jszip.min.js`.
- Orientación EXIF: usar `createImageBitmap(f,{imageOrientation:'from-image'})` y **no** rotar a mano (el navegador ya rota; rotar de nuevo duplica).
- Cada foto va embebida dos veces en el KMZ (miniatura + HD): decisión del usuario, no cambiarla.

## Verificar
El Browser pane no permite subir archivos a `<input type=file>`: inyectar `File` generados vía `javascript_tool`. Con la pestaña en segundo plano `setTimeout` se ralentiza mucho; no confundir con un cuelgue.
