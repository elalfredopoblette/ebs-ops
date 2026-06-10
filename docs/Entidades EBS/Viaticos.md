## ¿Qué es?
Gastos de manutención que EBS cubre para personal asignado a un [[Evento]]
fuera de su ciudad base. Incluye alimentación y transporte local.
No incluye [[Hospedaje]] ni [[Vuelos]] — esos van separados.

## Atributos
- `id`, `evento` → [[Evento]], `persona` → [[Entidades EBS/Persona]]
- `dias_cubiertos` — basado en [[Turno]]s activos
- `monto_diario` — tarifa fija
- `total` — dias × monto_diario
- `estado` — Pendiente / Aprobado / Pagado
- `forma_pago` — Adelanto / Transferencia / Reembolso

## Cómo se calcula
1 [[Turno]] activo fuera de ciudad base = 1 día de viáticos.

## Relaciones
- Deriva de [[Turno]]s del personal en el [[Evento]]
- Coordinado por [[Logistica de Personal]] y [[Administración]]
