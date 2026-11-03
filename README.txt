BA PROTEGE+ — CENTRO DE CONTROL QA

Contenido:
- index.html: aplicación web del Centro de control QA.
- cases.json: catálogo inicial de 32 escenarios del modo Responsable en español.
- responsible-mode-test-cases.json / .csv: archivos para importar los 32 escenarios.
- suite-membership.csv: asignación de casos a las suites, con encabezados y contenido en español.
- qa_responsible_mode_additive_migration.sql: migración aditiva para description, is_active y comment.

Antes de desplegar:
1. Ejecutar qa_responsible_mode_additive_migration.sql en Supabase SQL Editor.
2. Reemplazar el index.html del repositorio por este index.html.
3. Importar responsible-mode-test-cases.csv o .json desde Casos de prueba.
4. En Casos de prueba, usar «Importar pertenencia a suites» y seleccionar suite-membership.csv.
5. Publicar los cambios en el repositorio para que Vercel despliegue la nueva versión.

Notas importantes:
- La migración solo modifica tablas QA existentes; no modifica tablas ajenas.
- El borrado del catálogo es lógico (is_active=false): conserva resultados e historial.
- La edición actualiza el caso del catálogo; las ejecuciones ya creadas conservan case_snapshot.
- El modo Protegido no está finalizado; los casos PIN/QR validan únicamente las pantallas disponibles del Responsable.
- Los permisos indicados son opcionales y no deben bloquear la configuración.
- El mismo dispositivo debe esperar 24 horas para volver a vincularse después de desvincularse.
- El archivo suite-membership.csv crea las relaciones en qa_test_suite_cases; no es una migración SQL.
