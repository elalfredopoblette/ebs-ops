
## ¿Qué es?
Un Requerimiento es la expresión formal de una necesidad de [[Recurso]]
para un [[Evento]] en un [[Periodo]] determinado.

Es el punto donde una necesidad operativa deja de ser verbal o implícita
y se convierte en algo rastreable y resoluble.

## ¿Cuándo nace?
Idealmente: durante el [[Cross Check de Disponibilidad]], antes de 
confirmar el [[Evento]].

En la práctica actual de EBS: después de generar la [[ODS]], cuando 
alguien detecta que un recurso no está disponible o no existe en 
inventario propio.

> El sistema debería mover este momento hacia atrás en el flujo —
> del post-ODS al pre-ODS.

## Ejemplos
- Se necesitan 400 m² de LD Roll para Evento X · no hay suficiente
- Se requiere un Supervisor EPS para Festival Y · ya está asignado a Z
- Se necesita una Sprinter adicional · la flota está completa ese fin de semana

## Atributos
- `id`
- `recurso` → [[Recurso]]
- `evento` → [[Evento]]
- `cantidad`
- `fecha_inicio`
- `fecha_fin`
- `estado` — ver Estados
- `origen` — quién detectó la necesidad
- `prioridad` — alta / media / baja
- `notas`

## Estados posibles
- **Detectado** — se identificó la necesidad, sin acción aún
- **En evaluación** — se está revisando disponibilidad
- **Resuelto con propio** — hay inventario disponible → genera [[Asignacion]]
- **Resuelto con renta** — no hay propio → genera [[Renta]]
- **Sin resolver** — no hay solución identificada → escala a Operaciones
- **Cancelado** — el evento cambió o se canceló

## Ciclo de vida
Detectado → En evaluación → Resuelto con propio → [[Asignacion]]
                          → Resuelto con renta  → [[Renta]]
                          → Sin resolver        → escala

## Reglas críticas
- Un Requerimiento no resuelto bloquea la confirmación del [[Evento]]
- Puede existir sin una [[ODS]] generada — ese es el uso ideal
- Varios Requerimientos del mismo [[Recurso]] en fechas solapadas 
  generan un [[Conflicto]]

## Relaciones
- Nace del [[Cross Check de Disponibilidad]] o de la lectura de la [[ODS]]
- Se resuelve en una [[Asignacion]] o una [[Renta]]
- Si no se resuelve → [[Conflicto]]
- Está siempre ligado a un [[Evento]] y un [[Periodo]]