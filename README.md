# Levantamiento en Sitio — SITI

Aplicación de una sola página (HTML/CSS/JS, sin dependencias ni instalación) para capturar
la información técnica necesaria en visitas de levantamiento y generar una cotización de:

- Nodos de red
- Enlaces de fibra
- CCTV (sistema nuevo y ampliación de equipo existente)
- PBX Issabel (instalación nueva y migración)
- Control de Asistencia
- Control de Acceso

## Uso

Abre `index.html` en cualquier navegador (Chrome, Safari, Edge). Funciona en computadora,
tablet o celular. No requiere servidor ni conexión a internet una vez cargada la página.

## Dónde se guardan los datos

- **Dentro de Claude.ai** (como artifact): los levantamientos se guardan compartidos, visibles
  para cualquier persona con acceso a ese artifact.
- **Fuera de Claude** (este repositorio, GitHub Pages, o empaquetada como app): los levantamientos
  se guardan únicamente en el navegador/dispositivo donde se capturaron (`localStorage`). Si
  necesitas que el equipo comparta la misma lista de levantamientos entre varios dispositivos,
  se requeriría conectar la app a una base de datos (por ejemplo Firebase o Supabase) — avísame
  si quieres que lo agreguemos más adelante.

## Publicar con GitHub Pages

1. Crea un repositorio en GitHub (puede ser público o privado).
2. Sube este archivo `index.html` (y este `README.md`) a la raíz del repositorio.
3. Ve a **Settings → Pages**, en "Build and deployment" selecciona **Deploy from a branch**,
   rama `main`, carpeta `/ (root)`, y guarda.
4. Después de uno o dos minutos, la app estará disponible en:
   `https://<tu-usuario>.github.io/<nombre-del-repositorio>/`

## Siguientes pasos (app para Android)

La forma más simple de tener un "ícono de app" en Android sin programar una app nativa es
convertir esta página en una PWA (Progressive Web App): agregando un `manifest.json` y un
service worker, Chrome en Android permite "Agregar a pantalla de inicio" y se abre a pantalla
completa como cualquier otra app. Si prefieres una app nativa real (Play Store), se puede
empaquetar este mismo HTML dentro de un WebView con Android Studio. Podemos hacer cualquiera
de las dos cuando quieras continuar.
