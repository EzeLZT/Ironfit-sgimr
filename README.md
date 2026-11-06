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

## Declaración de Uso de Inteligencia Artificial

### Herramienta utilizada

- **ChatGPT (OpenAI)**: corrección ortográfica, revisión de estilo, sugerencias de formato y apoyo en la estructuración de textos técnicos.

### Uso crítico y correcciones humanas

La IA se utilizó como herramienta de apoyo para tareas mecánicas, manteniendo siempre el control intelectual del proyecto.

**Decisiones conceptuales propias (sin IA):**

- Elección del caso de estudio (IronFit) basada en conocimiento del rubro fitness.
- Identificación de los tres problemas críticos (morosos falsos, sobrecupo, errores de carga).
- Diseño del organigrama y ubicación del área de Sistemas al mismo nivel que Administración y Operaciones.
- Definición de las reglas de negocio del SGIMR (morosidad calculada desde `fecha_vencimiento`, lista de espera por cupo agotado).

**Correcciones humanas a sugerencias de la IA:**

- Diccionario de datos v1: la IA propuso incluir `estado_pago` como Boolean; tras la retroalimentación docente (Entrega 3) lo eliminé por redundante con `fecha_vencimiento` y pasé a calcularlo dinámicamente.
- Organigrama: la IA sugería colgar el área de Sistemas de Administración; la ubiqué al mismo nivel por su alcance transversal.
- Gantt: la IA no detectó que, siendo equipo unipersonal, no podía planificar tareas en paralelo; secuencié los módulos y extendí el plazo a 13 semanas con contingencia.
- BPMN: corregí a mano la conexión errónea "Confirmar reserva → Lista de espera" y agregué el subflujo de cupo liberado tras la observación docente de la Entrega 4.

**Responsabilidad intelectual:** todo el contenido conceptual, las decisiones de diseño y la coherencia entre las cuatro entregas son de mi autoría. Los errores de la IA fueron identificados y corregidos por mí durante las revisiones.
