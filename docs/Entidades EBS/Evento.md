# Evento

## ¿Qué es?
Un Evento es una instancia continua de operación dentro de un [[Proyecto]].
Abarca desde el inicio del Load In hasta el fin del Load Out.
Durante ese periodo, los [[Recurso]]s asignados permanecen comprometidos
y no se liberan entre fases.

## Ejemplos
- EDC México 2026 — Load In 12 marzo → Load Out 16 marzo (3 ShowDays)
- Campo Marte Fase 1 — Load In 8 abril → Load Out 10 abril
- Campo Marte Fase 2 — Load In 28 abril → Load Out 30 abril
- Festival X — Load In viernes → Load Out lunes (1 ShowDay)

>Campo Marte Fase 1  y Campo Marte Fase 2 son dos Eventos del mismo Proyecto.
> EDC con 3 ShowDays es un solo Evento — el recurso no se libera entre días.

## Atributos
- `id`
- `nombre`
- `proyecto` → [[Proyecto]]
- `venue` → [[Venue]]
- `cliente` → [[Cliente]]
- `estado` — ver Estados
- `fecha_load_in` — datetime
- `fecha_load_out` — datetime
- `showdays` — número de días de operación
- `presupuesto_operativo` → [[Presupuesto]]
- `tiene_proyeccion_preliminar` — bool: indica si existe una Proyección de costos pre-contrato
- `responsable` → [[Roles]]
- `notas`

## Fases internas
Todo Evento se compone de Periodos en este orden:

| Fase | Descripción |
|---|---|
| Load In | Montaje. Recursos entran al venue |
| ShowDay | Operación. Puede repetirse N días |
| Load Out | Desmontaje. Recursos salen del venue |

Estas fases son [[Periodo]] — no son Eventos distintos.

## Estados posibles
- **Prospecto** — en evaluación comercial, sin confirmar. Puede tener [[Procesos/Proyeccion|Proyección]] preliminar si el [[Brief]] ya fue recibido.
- **Confirmado** — vendido, en planeación operativa
- **En planeación** — [[Cross Check de Disponibilidad]] en curso
- **Listo** — recursos asignados, [[ODS]] generada
- **En operación** — Load In iniciado
- **Cerrado** — Load Out completado, recursos liberados
- **Cancelado** — se anuló antes de ejecutarse

## Reglas críticas
- Un Evento no puede pasar a **Listo** si tiene [[Requerimiento]]s
  sin resolver
- Un Evento no puede pasar a **Listo** si tiene [[Conflicto]]
  en estado Detectado
- Al pasar a **Cerrado**, todos sus [[Recurso]]s se liberan
  y el [[Inventario]] se actualiza
- Dos Eventos del mismo [[Proyecto]] con fechas solapadas
  son válidos solo si usan recursos distintos

## Relaciones
- Pertenece a un [[Proyecto]]
- Ocurre en un [[Venue]]
- Tiene uno o más [[Periodo]]s internos
- Genera [[Requerimiento]]s de recursos
- Sus Requerimientos se resuelven en [[Asignacion]]es
- Sus Asignaciones pueden generar [[Conflicto]]s
- Cuando está Listo produce una [[ODS]]
- Al cerrarse libera [[Recurso]]s y actualiza [[Inventario]]