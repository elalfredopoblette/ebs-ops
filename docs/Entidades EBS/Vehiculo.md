## ¿Qué es?
Un Vehículo es un [[Recurso]] de transporte que EBS utiliza para mover
materiales y [[Entidades EBS/Persona]]l entre el almacén y los [[Venue]]s.

## Tipos
| Tipo | Uso principal |
|---|---|
| Sprinter | Traslado de personal, herramienta ligera |
| Camioneta | Material ligero |
| Camión 3.5 ton | Material mediano, piezas EPS |
| Camión 10 ton | Estructuras STEEL, carga pesada |
| Plataforma | Piezas largas, Roof System |

## Atributos
- `id`, `tipo`, `placa`, `capacidad_carga_kg`, `capacidad_personas`
- `operador` → [[Entidades EBS/Persona]]
- `estado` — Disponible / Asignado / En tránsito / En mantenimiento
- `propio` — boolean
- `proveedor` → [[Proveedor Externo]] (si es rentado)
- `ubicacion_actual`

## Relaciones
- Se asigna a [[Evento]]s mediante [[Asignacion]]
- Genera [[Movimiento]]s al trasladar material
- Gestionado por [[Logistica de Carga]]
- Sin disponibilidad propia → [[Renta]] de vehículo externo
