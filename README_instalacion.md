# Reservas Museo Scasso — instalación

Esta carpeta contiene:

- `index.html`: página pública para GitHub Pages.
- `assets/`: imágenes y logo usados por el HTML.
- `apps_script_backend.gs`: código que debe pegarse en Google Apps Script.

## Estado de esta versión

La URL de Apps Script ya fue incorporada en el HTML:

`https://script.google.com/macros/s/AKfycbympMMx8jODBiYDSo7bdlI-4b3ZRJhbMhiFPaM8_MlFgGNelHcr39lWbTPvXYeSarQ0mA/exec`

## Paso pendiente importante

Como se actualizó el backend para que funcione con el calendario visual del HTML, hay que reemplazar el código actual de Apps Script por el contenido del archivo:

`apps_script_backend.gs`

Luego:

1. Guardar.
2. Ir a **Implementar → Administrar implementaciones**.
3. Editar la implementación existente.
4. Elegir **Nueva versión**.
5. Mantener:
   - Ejecutar como: `museoscasso.videos@gmail.com`
   - Usuarios con acceso: `Cualquier persona`
6. Implementar.

## Calendarios usados

Calendario público — solo muestra bloqueos:

`132c920445f800e510cd7d9b9b7cd4119d5663eb56d7f88d0c4752dfc57c486f@group.calendar.google.com`

Calendario privado institucional — guarda datos resumidos:

`b8ba3b85avon1iir2f8ifeum5g@group.calendar.google.com`

La cuenta `museoscasso.videos@gmail.com` debe tener permiso **Hacer cambios en eventos** sobre ambos calendarios.

## Flujo esperado

1. El visitante elige propuesta, fecha y horario.
2. La página consulta Apps Script.
3. Apps Script consulta el calendario público y la planilla.
4. Si hay cupo, permite seleccionar.
5. Al enviar, Apps Script:
   - guarda la reserva en Google Sheets;
   - crea `NO DISPONIBLE` en el calendario público cuando corresponde;
   - crea un evento detallado en el calendario privado;
   - envía correo al solicitante y a `damianvoglino@yahoo.com.ar`.

## Nota sobre cupos

- Visitas escolares: se bloquea el turno completo al primer pedido.
- Talleres y eventos con cupo: se descuentan cupos y se bloquea cuando se completa la capacidad.
