# Verovio Viewer (Cliente puro)

Visualizador de partituras MEI / MusicXML (y MXL) **100% en el navegador** usando Verovio (WASM).

## Rápido: publicar en GitHub Pages

1. Crea un repositorio nuevo en GitHub (público), por ejemplo: `verovio-viewer`.
2. Sube estos archivos al repositorio (tal cual):  
   - `index.html`  
   - `.github/workflows/pages.yml`  
3. Haz commit a la rama `main`.
4. En **Settings → Pages**, en **Build and deployment**, deja **Source: GitHub Actions** (por defecto).
5. Ve a **Actions** y espera que el workflow **Deploy static site to Pages** termine en ✅.
6. Tu sitio quedará publicado en una URL como:  
   `https://<tu-usuario>.github.io/verovio-viewer/`

> La primera publicación puede tardar 1–2 minutos.

## Uso jh

- Abre la URL publicada.  
- Carga un archivo **.mei**, **.xml/.musicxml** o **.mxl** (MusicXML comprimido) con el botón **Cargar archivo**.  
- O pega el contenido MEI/MusicXML en **Pegar texto** y pulsa **Renderizar texto**.  
- Usa **Prev/Next** para navegar páginas y **Zoom – / +** para ajustar escala.

## ¿Por qué GitHub Pages?

Abrir `index.html` como `file://` hace que algunos navegadores bloqueen la descarga del archivo `.wasm` de Verovio (política CORS).  
Publicar bajo `https://` (GitHub Pages/Netlify/Vercel) evita ese bloqueo.

## Si sigues viendo un aviso de inicialización

En casos raros, si el host del toolkit remoto cambiara sus cabeceras CORS, puedes **auto‑hospedar** el toolkit en tu repo:

1. Descarga `verovio-toolkit-wasm.js` y su `.wasm` correspondiente desde el sitio oficial de Verovio.  
2. Guárdalos en una carpeta local, por ejemplo `vendor/verovio/`.  
3. Cambia en `index.html` la línea del `<script>` por la ruta local:
   ```html
   <script src="vendor/verovio/verovio-toolkit-wasm.js" defer></script>
   ```

Así eliminas cualquier dependencia de CORS externo.

## Licencia

Este repositorio es solo un ejemplo de integración. Verovio es un proyecto independiente con su propia licencia.
