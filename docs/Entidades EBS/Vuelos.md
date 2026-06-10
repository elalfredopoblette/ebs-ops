## ¿Qué es?
Traslado aéreo para [[Entidades EBS/Persona]]l que debe llegar a un [[Venue]]
en otra ciudad. Es un gasto logístico, no un [[Recurso]].

## Atributos
- `id`, `evento` → [[Evento]], `persona` → [[Entidades EBS/Persona]]
- `origen`, `destino`, `fecha_salida`, `fecha_regreso`
- `aerolinea`, `numero_vuelo`, `costo`
- `estado` — Pendiente / Cotizado / Comprado / Cancelado

## Relaciones
- Deriva de [[Asignacion]] de personal foráneo
- Coordinado por [[Logistica de Personal]]
- El horario impacta los [[Turno]]s (define cuándo llega el personal)
