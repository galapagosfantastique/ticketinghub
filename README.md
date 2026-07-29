# ticketinghub — assets de Galápagos Fantastique

Repositorio para **hospedar recursos estáticos** (CSS) del motor de reservas **TicketingHub** de Galápagos Fantastique, servidos vía **CDN jsDelivr**.

No contiene código de aplicación ni datos sensibles: solo archivos públicos que TicketingHub necesita cargar por URL.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `agencias.css` | Estilo de marca del **widget del portal de agencias/revendedores** (embed legacy `checkout.js`). Ajusta tipografías (Inter/Inconsolata), colores de marca (`#1D1D1B` negro, `#1470AF` azul) y bordes rectos. |

## Cómo se usa en TicketingHub

El widget del portal de reseller se estiliza con un **archivo CSS hospedado** (no admite pegar el código). Se enlaza así:

1. Dashboard → **Widgets → Channels → Web Integrations** (del widget del portal) → clic en el widget → **Settings**.
2. En **Custom CSS URL** pega la URL de jsDelivr:

   ```
   https://cdn.jsdelivr.net/gh/galapagosfantastique/ticketinghub@main/agencias.css
   ```

3. **Publish Changes → Confirm**.
4. Verifica el portal (`/agencias`) en una ventana de incógnito con **Ctrl+F5**.

> ⚠️ Usa la URL de **jsDelivr** (la sirve como `text/css`). **No** uses `raw.githubusercontent.com`: la entrega como `text/plain` y el navegador la rechaza como hoja de estilos.

## Cómo actualizar el estilo

1. Edita el `.css` y haz commit/push a `main`.
2. jsDelivr cachea `@main`; para forzar la última versión al instante, purga la caché:

   ```
   https://purge.jsdelivr.net/gh/galapagosfantastique/ticketinghub@main/agencias.css
   ```

   (o enlaza un commit/tag específico en lugar de `@main`).

## Contexto del proyecto

Parte de la automatización de reservas de Galápagos Fantastique (Squarespace + TicketingHub + pasarelas de pago). La documentación del proyecto vive fuera de este repo; aquí solo se alojan los assets que deben servirse por URL pública.
