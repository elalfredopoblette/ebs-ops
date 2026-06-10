## ¿Qué es?
Alojamiento contratado para el [[Entidades EBS/Persona]]l que trabaja en un
[[Evento]] fuera de su ciudad base. Es un gasto logístico, no un [[Recurso]].

## Atributos
- `id`, `evento` → [[Evento]], `persona` → [[Entidades EBS/Persona]]
- `hotel`, `ciudad`, `fecha_check_in`, `fecha_check_out`, `noches`
- `costo_por_noche`, `costo_total` — calculado
- `estado` — Pendiente / Reservado / Confirmado / Cancelado

## Relaciones
- Deriva de [[Asignacion]] de personal foráneo
- Coordinado por [[Logistica de Personal]]
- Costo incluido en [[Viaticos]] del [[Evento]]
