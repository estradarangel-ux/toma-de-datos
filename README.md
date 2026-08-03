# Levantamiento en Sitio — SITI

Aplicación de una sola página (HTML/CSS/JS, sin dependencias ni instalación) para capturar
la información técnica necesaria en visitas de levantamiento y generar una cotización de:

- Nodos de red
- Enlaces de fibra
- CCTV (sistema nuevo y ampliación de equipo existente)
- PBX Issabel (instalación nueva y migración)
- Control de Asistencia
- Control de Acceso

Disponible en: **https://levantamiento.siticomunicaciones.com**

## Archivos de este repositorio

```
index.html                  ← la app (súbelo a la raíz del repositorio)
manifest.json                ← hace que se pueda "instalar" como app
sw.js                        ← permite que abra aunque no haya señal en el sitio
icons/
  icon-192.png
  icon-512.png
  icon-maskable-512.png
  apple-touch-icon.png
  favicon-32.png
```

Sube **todos** estos archivos (incluyendo la carpeta `icons/` completa, con los mismos
nombres) a la raíz del repositorio — no solo el `index.html`. Si solo subes el HTML, la
app seguirá funcionando en el navegador, pero no se podrá "instalar" como ícono en el
celular/tablet ni funcionará sin conexión.

## Instalarla como app en el celular/tablet

**Android (Chrome):**
1. Abre `https://levantamiento.siticomunicaciones.com` en Chrome.
2. Toca el menú (⋮, arriba a la derecha).
3. Toca **"Instalar app"** (o "Agregar a pantalla de inicio").
4. Aparecerá el ícono de SITI en el cajón de apps, y se abre a pantalla completa como
   cualquier otra app — sin pasar por Play Store.

**iPad / iPhone (Safari):**
1. Abre la misma dirección en **Safari** (tiene que ser Safari, no Chrome — en iOS solo
   Safari puede instalar así).
2. Toca el botón de **Compartir** (el cuadro con la flecha hacia arriba).
3. Baja y toca **"Agregar a pantalla de inicio"**.
4. Confirma el nombre y toca **"Agregar"**. Aparece el ícono en la pantalla de inicio y
   abre a pantalla completa, sin la barra de Safari.

Esto es una PWA (Progressive Web App): no pasa por App Store ni Play Store, no requiere
cuenta de desarrollador, y funciona igual en ambas plataformas con el mismo código.

## Dónde se guardan los datos

Cada dispositivo guarda su propia lista de levantamientos en el navegador (`localStorage`).
No es compartida automáticamente entre distintos celulares/tablets del equipo. Para
compartir la misma lista entre varios dispositivos se necesitaría conectar la app a una
base de datos real (por ejemplo Firebase o Supabase) — es una ampliación posible más
adelante si el equipo la necesita.

Para respaldar o pasar la información a tu cotizador: desde el resumen de cada
levantamiento puedes **Imprimir / Guardar como PDF**, **Copiar resumen** (texto), o
**Descargar CSV** (para Excel/Sheets).

## Publicar cambios futuros

Cada vez que se actualice `index.html` (o cualquier otro archivo), solo hay que volver a
subirlo al repositorio de GitHub — GitHub Pages lo publica automáticamente en un par de
minutos. Los celulares/tablets que ya la tengan "instalada" recibirán la versión nueva la
próxima vez que la abran con conexión a internet (el service worker se encarga de
actualizarla en segundo plano).

## Si más adelante quieren una app "de verdad" en Play Store / App Store

Lo de arriba (PWA) cubre el 90% del caso de uso sin costo ni trámites. Si en algún
momento se quiere que aparezca en las tiendas oficiales, existen dos caminos, ambos
requieren herramientas fuera de este chat:
- **Android**: empaquetar este mismo sitio con [Bubblewrap](https://github.com/GoogleChromeLabs/bubblewrap)
  o Android Studio (WebView), y publicarlo en Play Store (cuenta de desarrollador: pago
  único de $25 USD).
- **iOS/iPadOS**: empaquetarlo con Xcode y publicarlo en App Store (cuenta de desarrollador
  Apple: $99 USD/año).
