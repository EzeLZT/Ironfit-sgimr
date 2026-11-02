# Diccionario de Datos del SGIMR (v2)

Versión corregida respecto de la Entrega 3: se elimina `estado_pago` (redundante con
`fecha_vencimiento`: el estado se calcula comparando con la fecha actual, lo que evita
inconsistencias y "morosos falsos") y se renombra `precio_mensual` a `importe_cuota`
porque hay planes no mensuales (ej. Trimestral).

## Entidad: SOCIO
| Campo | Tipo | Descripción funcional |
|---|---|---|
| id_socio | Integer | Identificador único de cada socio (clave primaria). |
| nombre_apellido | String | Nombre completo; se usa en alta, credencial digital y reportes. |
| dni | String | Documento de identidad; validación ante homónimos. |
| fecha_alta | Date | Fecha de inscripción; permite medir antigüedad y abandonos. |
| activo | Boolean | Socio vigente (true) o inactivo (false); filtra reportes sin borrar historial. |

## Entidad: MEMBRESÍA
| Campo | Tipo | Descripción funcional |
|---|---|---|
| id_membresia | Integer | Identificador único del contrato (clave primaria). |
| id_socio | Integer | Clave foránea hacia SOCIO. |
| plan | String | Plan contratado ("Mensual", "Trimestral", "Full horario pico"). |
| importe_cuota | Decimal | Importe de la cuota del plan; cobro automático y reportes de ingresos. |
| fecha_vencimiento | Date | Fecha hasta la cual la membresía está paga. De aquí se deriva el estado de pago por comparación con la fecha actual. |

## Entidad: RESERVA
| Campo | Tipo | Descripción funcional |
|---|---|---|
| id_reserva | Integer | Identificador único de la reserva (clave primaria). |
| id_socio | Integer | Clave foránea: qué socio reservó. |
| nombre_clase | String | Clase grupal reservada (spinning, HIIT, yoga). |
| fecha_hora | DateTime | Día y horario de la clase; control de superposiciones. |
| estado_reserva | String | "Confirmada", "En espera" o "Cancelada". |
| asistio | Boolean | Si el socio concurrió; alimenta reportes y alertas de retención. |

Nota de alcance: el cupo por clase vivirá en la entidad CLASE en la próxima etapa de
modelado. Sin esa entidad el control de cupos no es implementable; queda registrado
como deuda de diseño consciente y no como omisión.

## Relaciones
SOCIO 1:N MEMBRESÍA y SOCIO 1:N RESERVA, vía `id_socio`. Regla de negocio: si al
reservar la `fecha_vencimiento` de la membresía activa es anterior a hoy, el SGIMR
bloquea la reserva hasta regularizar la cuota.
