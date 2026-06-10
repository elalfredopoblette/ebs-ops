
## ¿Qué es?
Un Periodo es una ventana de tiempo con fecha de inicio y fecha de fin.
Es la unidad de tiempo que define cuándo un [[Recurso]] está comprometido
y cuándo está disponible.

Sin un Periodo, una [[Asignacion]] no existe.
Sin un Periodo, un [[Conflicto]] no puede detectarse.

## Ejemplos
- Load In: 12 marzo 08:00 → 14 marzo 18:00
- ShowDay: 15 marzo 10:00 → 15 marzo 23:59
- Load Out: 16 marzo 06:00 → 16 marzo 14:00

## Atributos
- `fecha_inicio` — datetime
- `fecha_fin` — datetime
- `tipo` — ver Tipos
- `evento` → [[Evento]]

## Tipos
| Tipo | Descripción |
|---|---|
| Load In | Montaje previo al evento |
| ShowDay | Día(s) de operación |
| Load Out | Desmontaje post evento |
| Reserva | Bloqueo preventivo sin evento confirmado |
| Mantenimiento | Recurso fuera de servicio temporalmente |

## Regla crítica
Dos [[Asignacion]]es del mismo [[Recurso]] generan un [[Conflicto]] si sus Periodos se solapan, así sea parcialmente.

## Solapamiento
Dos periodos se solapan cuando:
- A.fecha_inicio < B.fecha_fin
- Y A.fecha_fin > B.fecha_inicio

Cualquier otra combinación = sin conflicto.

## Relaciones
- Todo [[Evento]] tiene uno o más Periodos
- Toda [[Asignacion]] vive dentro de un Periodo
- Todo [[Conflicto]] existe porque dos Periodos se solapan
- Todo [[Movimiento]] ocurre dentro de un Periodo