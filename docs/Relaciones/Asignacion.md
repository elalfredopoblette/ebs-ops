
## ¿Qué es?
Una Asignación es el vínculo formal entre un [[Recurso]] y un [[Evento]] 
durante un [[Periodo]] determinado.
Representa una reserva de capacidad operativa: el recurso queda 
comprometido y no puede usarse en otro evento que se solape en el tiempo.

## Ejemplos
- Supervisor EPS → EDC México · 12–15 marzo
- Jefe de Steel → Intermoda · 8–10 abril
- Sprinter 2 → Festival X · 20–22 mayo
- 300 m² de LD Roll → Evento Y · 1–3 junio

## Atributos
- `id`
- `recurso` → [[Recurso]]
- `evento` → [[Evento]]
- `proyecto` → [[Proyecto]] (heredado del Evento)
- `fecha_inicio`
- `fecha_fin`
- `cantidad` — relevante para recursos de inventario (m², piezas)
- `estado` — ver Estados posibles
- `origen` — propio / renta / subcontrato
- `creado_por` → [[Roles]]
- `notas`

## Estados posibles
- **Tentativa** — exploratoria, sin confirmar disponibilidad
- **Reservada** — disponibilidad verificada, recurso bloqueado
- **Confirmada** — aprobada operativamente, aparece en [[ODS]]
- **Liberada** — el evento terminó, recurso vuelve a estar disponible
- **Cancelada** — se anuló antes de ejecutarse

## Reglas críticas
- No pueden existir dos Asignaciones **Confirmadas** del mismo 
  [[Recurso]] en periodos que se solapan → genera [[Conflicto]]
- Una Asignación **Tentativa** no bloquea al recurso, pero advierte 
  riesgo de conflicto
- Al pasar a **Liberada**, el [[Inventario]] del recurso se actualiza
- Si el recurso no está disponible, la Asignación no puede confirmarse 
  → se evalúa [[Renta]]

## Ciclo de vida
Tentativa → Reservada → Confirmada → Liberada
                                    ↘ Cancelada

## Relaciones
- Nace de un [[Requerimiento]]
- Puede generar un [[Conflicto]] si hay solapamiento
- Confirmada → aparece en [[ODS]]
- Liberada → actualiza [[Inventario]]
- Si no resolvible → deriva en [[Renta]]
- Su ventana de tiempo es un [[Periodo]]