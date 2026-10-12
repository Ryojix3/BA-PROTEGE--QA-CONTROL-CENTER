# BA Protege+ QA Control Center — Vercel Edition

Esta edición está preparada para desplegarse como sitio estático en Vercel. No requiere backend ni variables de entorno.

## Publicar en Vercel
1. Descomprime el ZIP.
2. Sube el contenido de esta carpeta a un repositorio GitHub.
3. En Vercel, selecciona **Add New → Project** y conecta ese repositorio.
4. Framework Preset: **Other**.
5. Build Command: dejar vacío.
6. Output Directory: `.` (raíz del proyecto).
7. Pulsa **Deploy**.

También puedes usar Vercel CLI desde esta carpeta: `npx vercel`.

## Uso
- Abre la aplicación desplegada.
- Ve a Dashboard y pulsa **Cargar casos iniciales**.
- Crea una ejecución, selecciona casos y guarda resultados.
- Registra bugs con Title, Description, Level - Area, Steps to reproduce, Current Behavior, Expected Behavior, Additional Notes, Attachments, Component, Affects Version, Fix Version, Platform y Reproduction Rate.
- En **Bugs**, usa **Exportar bugs JSON** para compartir tus defectos con otro tester y **Importar bugs** para agregar los que esa persona haya encontrado. La importación combina los registros, omite duplicados y renumera IDs si hay conflictos.
- Exporta reportes JSON o el catálogo CSV.

## Persistencia y limitaciones
Esta versión guarda todos los datos en `localStorage` del navegador. En el formulario de bugs, el campo Attachments registra los nombres de los archivos seleccionados, pero no sube ni almacena los archivos adjuntos. La importación/exportación de bugs comparte los datos del reporte, no los archivos binarios adjuntos. Es ideal para una demo o uso individual inicial, pero los datos no se comparten entre testers, dispositivos o navegadores y se pierden si se borra el almacenamiento del sitio. Exporta copias de seguridad periódicamente.

Para uso real de equipo, el siguiente paso recomendado es conectar Supabase (PostgreSQL + autenticación + almacenamiento de evidencias) o un backend persistente. No se ha desplegado por ti: este paquete está preparado para que lo publiques en tu cuenta de Vercel.
