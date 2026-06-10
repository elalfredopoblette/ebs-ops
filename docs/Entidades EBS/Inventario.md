
## ¿Qué es?
El Inventario es el estado actual de disponibilidad de los [[Recurso]]s
de EBS en un momento determinado.

No es una lista estática — es una fotografía dinámica que cambia
cada vez que un [[Recurso]] se asigna, se mueve, se libera o entra
a mantenimiento.

> El Inventario no es el Recurso.
> El Recurso existe. El Inventario dice cuánto hay disponible
> y dónde está.

## Problema actual
EBS mantiene conteos en Excel y en Odoo de forma paralela.
Ninguno está conectado con las [[Asignacion]]es activas ni con
los [[Evento]]s en curso.
Esto genera el riesgo principal: comprometer recursos que ya
están comprometidos.

## Unidades por categoría

### STEEL — por pieza individual
Los recursos de Steel se cuentan por pieza porque los despieces
cambian por proyecto. Las mismas piezas pueden armar configuraciones
distintas según el [[Plano]] y el [[Despiece]].

| Recurso | Unidad |
|---|---|
| Roof System | pieza |
| Delay Tower | pieza |
| Scaffold | pieza |

> El [[Despiece]] define cuántas piezas de cada tipo requiere
> una configuración específica. El Inventario dice si esas
> piezas están disponibles.

### EPS — por unidad o m²
| Recurso | Unidad |
|---|---|
| LD Rolls | m² |
| Arena Light Panel | m² / pieza |
| EPS Pro | m² |
| GIGS Barricada | ml / pieza |

## Atributos por recurso
- `recurso` → [[Recurso]]
- `cantidad_total` — stock total que posee EBS
- `cantidad_asignada` — comprometida en [[Asignacion]]es activas
- `cantidad_en_mantenimiento` — no disponible temporalmente
- `cantidad_disponible` — calculada: total − asignada − mantenimiento
- `ubicacion` — almacén / venue / tránsito
- `ultima_actualizacion` — datetime

## Cómo se actualiza
| Evento | Efecto en Inventario |
|---|---|
| [[Asignacion]] confirmada | ↓ cantidad_disponible |
| [[Asignacion]] liberada | ↑ cantidad_disponible |
| [[Movimiento]] de salida | ubicacion → tránsito / venue |
| [[Movimiento]] de entrada | ubicacion → almacén |
| Recurso en mantenimiento | ↓ cantidad_disponible, ↑ en_mantenimiento |
| Recurso dado de alta | ↑ cantidad_total |
| Recurso dado de baja | ↓ cantidad_total |

## Reglas críticas
- `cantidad_disponible` nunca puede ser negativa
- Si una [[Asignacion]] requiere más cantidad de la disponible
  → se genera un [[Requerimiento]] sin resolver
- El Inventario debe consultarse antes de confirmar cualquier
  [[Asignacion]] — ese es el [[Cross Check de Disponibilidad]]
- Un recurso En tránsito no cuenta como disponible aunque
  físicamente exista

## Relaciones
- Refleja el estado de todos los [[Recurso]]s de EBS
- Se actualiza con cada [[Asignacion]] y cada [[Movimiento]]
- Es la fuente de verdad para el [[Cross Check de Disponibilidad]]
- Cuando no alcanza → dispara un [[Requerimiento]]
- Cuando el [[Requerimiento]] no se resuelve con propio → [[Renta]]