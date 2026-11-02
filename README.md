# SGIMR – Sistema de Gestión Integral de Membresías y Reservas

Proyecto integrador de la asignatura **Organización Empresarial** (TUP – UTN, TUPAD).
Caso de estudio: **IronFit**, gimnasio de barrio.

## Descripción del sistema

El SGIMR es un sistema web que digitaliza la gestión que hoy IronFit hace en papel y
WhatsApp: altas y renovaciones de membresías, cobro automático de cuotas, reserva de
clases grupales con control de cupos y reportes de asistencia y morosidad. Nace de los
problemas detectados en la Entrega 1 del TPI: errores de carga, socios que figuran como
morosos sin serlo y clases sobreocupadas.

Alcance incluido: membresías, cobros, reservas con cupos, asistencia y reportes.
Alcance excluido (a propósito, por viabilidad): app móvil y notificaciones push.

## Integrante

- Juan Esequiel Lisarriturri – Tecnicatura Universitaria en Programación (UTN).
- Desarrollo unipersonal. Docente titular: Gabriela Martínez. Docente tutor: Andrea Ramos.

## Documentación técnica del proyecto

- `docs/historias-de-usuario.md` – Backlog inicial en formato formal.
- `docs/diccionario-de-datos.md` – Entidades SOCIO, MEMBRESÍA y RESERVA (v2).
- `docs/proceso-bpmn.md` – Proceso de reserva de clases modelado en BPMN.
- `docs/indicadores-control.md` – Indicadores de control y estándares de desempeño.
- Tablero de gestión: https://github.com/<<TU-USUARIO>>/ironfit-sgimr/projects/1

## Dinámica de versionado

- Rama principal: `main` (solo recibe cambios vía Pull Request).
- Ramas secundarias: `docs/*` para cada bloque de documentación.
- Commits descriptivos con prefijo `docs:`.
- PR n.º 1 con revisión previa al merge.

## Declaración de Uso de IA

Se utilizaron asistentes de IA (ChatGPT) con fines acotados y verificables:
revisión de estilo y ortografía, sugerencias de estructura documental y apoyo procedural
para Git/GitHub y BPMN. Control crítico humano aplicado sobre los resultados:

- El asistente propuso mantener el campo `estado_pago` en la entidad MEMBRESÍA; se lo
  eliminó tras detectar redundancia con `fecha_vencimiento` (observación docente
  incorporada): el estado se calcula, no se almacena.
- El asistente sugirió un Gantt con tareas en paralelo; se lo corrigió a secuencia
  estricta porque el equipo es unipersonal, y se sumó una semana de contingencia.
- El asistente propuso oportunidades y amenazas del FODA referidas al gimnasio; se las
  reencuadró al proyecto de software, que es lo que pide la consigna.
- Todos los diagramas (organigrama, bloques TGS, BPMN) fueron dibujados a mano por el
  autor; la IA solo aportó la especificación textual previa.
- Cada salida del modelo fue contrastada contra la consigna y la rúbrica antes de
  aceptarse. Las decisiones de alcance (qué entidades y módulos quedan afuera) son
  exclusivamente del autor.

La responsabilidad intelectual por errores u omisiones es íntegramente del estudiante.
