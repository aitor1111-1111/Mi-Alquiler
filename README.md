# Mi Alquiler

PWA local-first para gestionar inquilinos, rentas, facturas, liquidaciones y copias.

## Publicación
Sube el contenido de esta carpeta a un repositorio nuevo y activa GitHub Pages desde Settings > Pages > Deploy from a branch > main / root. Abre la URL por HTTPS en Chrome Android y usa «Añadir a pantalla de inicio».

## Datos y privacidad
Los datos se almacenan en IndexedDB del navegador. No existe sincronización entre dispositivos. Exporta regularmente una copia JSON y guárdala de forma segura. La copia incluye los documentos adjuntos codificados en base64.

## Limitaciones de esta primera versión
- La exportación es un archivo JSON único, no ZIP; permite conservar datos y adjuntos en un solo archivo.
- El PDF se genera mediante la función imprimir del navegador y permite Guardar como PDF.
- El cálculo de liquidación es una primera implementación que debe validarse con facturas reales anonimizadas antes de usarlo para cobrar.
- La liquidación calcula el reparto diario del importe de cada factura entre ocupantes del día. Internet se añade a 5 € por inquilino y mes prorrateado por días.
- Si hay solapamiento de salida y entrada en el mismo día, ambos se consideran ocupantes ese día, tal como se solicitó.
- No hay conexión bancaria, correo ni envío automático a WhatsApp.


## Revisión de avisos de Baser desde Outlook
La aplicación incorpora una sección para pegar el contenido del aviso recibido en Outlook. Extrae tipo de suministro, importe, fecha de emisión y periodo de consumo; detecta duplicados; permite pasar el aviso a la relación de facturas y adjuntar después el PDF original descargado manualmente desde Baser.

**Limitación importante:** esta PWA estática no accede directamente a Outlook ni inicia sesión en Baser. Para una conexión automática real con Outlook haría falta una integración OAuth y un servicio/backend seguro. No introduzcas contraseñas ni códigos en la aplicación.
