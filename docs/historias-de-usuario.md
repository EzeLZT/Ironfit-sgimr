# Historias de Usuario – Backlog inicial SGIMR

Formato formal: "Como [usuario], quiero [funcionalidad], para [beneficio]".
Estas tres HU se trackean en el tablero GitHub Projects del repositorio.

## HU-01 – Reserva con cupos visibles
Como socio, quiero reservar clases grupales desde el portal web viendo los cupos
disponibles en tiempo real, para no ir al gimnasio y encontrarme con la clase llena.

Criterios de aceptación:
- La grilla muestra cupos restantes por clase y horario.
- Con cupo en 0, la reserva pasa a lista de espera automáticamente.
- El sistema bloquea la reserva si la membresía está vencida.

## HU-02 – Morosidad calculada, no cargada
Como administrador, quiero que el estado de pago se calcule comparando la fecha de
vencimiento con la fecha actual, para eliminar los "morosos falsos" generados por
cargas manuales erróneas.

Criterios de aceptación:
- No existe campo de estado guardado: se deriva de `fecha_vencimiento`.
- El reporte de morosidad lista solo socios con fecha vencida y sin pago registrado.

## HU-03 – Asistencia sin doble carga
Como entrenador, quiero marcar asistencia desde una tablet al finalizar la clase,
para que los reportes de asistencia y retención se actualicen sin recarga manual.

Criterios de aceptación:
- La asistencia se registra sobre la reserva existente (campo `asistio`).
- Un socio con 14 días sin asistencia dispara alerta de retención.

## Estados en tablero
- HU-01: Listo (documentada y modelada en BPMN).
- HU-02: En Progreso (diccionario de datos v2 ajustado).
- HU-03: Por Hacer (pendiente de módulo de asistencia).
