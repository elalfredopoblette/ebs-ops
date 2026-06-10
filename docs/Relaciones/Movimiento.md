## ¿Qué es?
Registro histórico de un desplazamiento físico de un [[Recurso]]
entre dos ubicaciones en un momento determinado.

Es el log de trayectoria de cada recurso: de dónde salió, a dónde fue, cuándo y en qué estado.

## Por qué existe
Sin Movimientos no hay trazabilidad.
Si un recurso aparece como disponible pero no está en almacén, los Movimientos dicen dónde quedó.

## Tipos de Movimiento
| Tipo | Origen | Destino | Cuándo |
|---|---|---|---|
| Salida | Almacén | Venue | Antes del [[Load In]] |
| Entrada | Venue | Almacén | Después del [[Load Out]] |
| Traslado | Venue A | Venue B | Recurso pasa directo entre eventos (ver [[Gira]]) |
| Interno | Zona almacén A | Zona almacén B | Reorganización interna |

## Atributos
- recurso → [[Recurso]]
- tipo — Salida / Entrada / Traslado / Interno
- origen, destino — ubicación de inicio y fin
- fecha_salida, fecha_llegada
- estado_al_salir, estado_al_llegar — puede cambiar si hay daños en tránsito
- evento → [[Evento]] (si aplica)
- vehiculo → [[Vehiculo]] (si aplica)

## Ciclo de vida
Programado → En tránsito → Completado / Incidente (daño o faltante al llegar)

## Impacto en Inventario
Cada Movimiento completado actualiza el [[Inventario]]:
- Salida completada: recurso deja de estar en almacén
- Entrada completada: recurso regresa como Disponible (o En mantenimiento si llegó dañado)

## Reglas
- Un Movimiento de Salida sin Entrada correspondiente = recurso aún fuera de almacén
- No puede haber dos Movimientos activos del mismo recurso al mismo tiempo
- El estado del recurso al llegar puede diferir del estado al salir

## Relaciones
- Asociado a un [[Recurso]] (siempre)
- Asociado a un [[Evento]] (cuando sale o regresa de un evento)
- Generado por [[Salida de Almacen]] y [[Entrada de Almacen]]
- Alimenta el [[Inventario]] como read model
