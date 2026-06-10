## Dos roles, una entidad

Una Persona en EBS tiene dos roles que conviven pero son distintos:

### Como Recurso (operativo)
La Persona es un [[Recurso]] de tipo humano — tiene disponibilidad limitada,
puede asignarse a [[Evento]]s y puede generar [[Conflicto]]s de disponibilidad.
Se gestiona igual que cualquier otro Recurso.

### Como Actor (usuario del sistema)
La Persona opera el sistema: crea [[Requerimiento]]s, aprueba [[Asignacion]]es,
resuelve [[Conflicto]]s, genera [[ODS]]. Tiene un [[Roles|Rol]] que define
qué puede hacer dentro del sistema.

> En DDD: estos son dos Bounded Contexts distintos.
> "Persona como Recurso" pertenece al contexto de Planeación Operativa.
> "Persona como Actor" pertenece al contexto de Identidad / Acceso.
> Comparten el mismo ser humano pero son representaciones diferentes.

## Tipos de Persona (como Recurso)
| Tipo                 | Contrato                    | Área        |
| -------------------- | --------------------------- | ----------- |
| Project Manager      | Nómina + destajo / Eventual | Operaciones |
| Supervisor EPS       | Nómina                      | Operaciones |
| Jefe de Steel        | Nómina                      | Operaciones |
| Armador Nómina       | Nómina                      | Operaciones |
| Armador Eventual     | Eventual (solo destajo)     | Operaciones |
| Jefe de Cuadrilla    | Nómina                      | Operaciones |
| Staff / Auxiliar     | Eventual (solo destajo)     | Operaciones |
| Operador de Vehículo | Nómina / Eventual           | Logística   |

## Atributos (como Recurso)
- `id`
- `nombre`
- `apellido`
- `rol` → [[Roles]]
- `tipo_contrato` — nómina / destajo / freelance / externo
- `puesto_tabulador` → [[Tabulador]] — define BASE_FIJA, VIÁTICO_DÍA y VALOR_X_PUNTO
- `disponibilidad_semanal` — días hábiles disponibles
- `estado` — Disponible / Asignado / En tránsito / En operación / No disponible
- `ciudad_base` — determina si requiere [[Vuelos]] o [[Hospedaje]]
- `activo` — boolean

## Atributos (como Actor del sistema)
- `usuario`
- `rol_sistema` → define permisos
- `area` → [[Áreas]]

## Crecimiento y cambio de puesto
El puesto en el [[Tabulador]] es casi siempre el mismo para una persona.
Sin embargo, existe movilidad interna: alguien que demostró habilidades
puede ascender de Supervisor EPS a Jefe de Steel, o de Jefe de Steel a PM.

Cuando una persona cambia de puesto:
- Su `puesto_tabulador` se actualiza
- Los eventos futuros usan el nuevo puesto
- Los eventos pasados mantienen el registro con el puesto que tenía entonces

## Relaciones (como Recurso)
- Se asigna a [[Evento]]s mediante [[Asignacion]]
- Sus horas en campo se organizan en [[Turno]]s
- Sus Turnos determinan [[Viaticos]] y [[Pagos Por Evento (destajos)]]
- Si viaja, genera necesidades de [[Vuelos]] y [[Hospedaje]]
- Puede generar [[Conflicto]] si está asignada a dos Eventos solapados

## Nota operativa
EBS trabaja con personal de nómina (fijo) y personal eventual (destajo).
Los eventuales no tienen disponibilidad garantizada — se confirman
evento por evento. Esto debe reflejarse en el modelo de disponibilidad.
