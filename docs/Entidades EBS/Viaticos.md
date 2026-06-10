## ¿Qué es?
Gastos de manutención que EBS cubre para personal asignado a un [[Evento]]
fuera de su ciudad base. Cubre alimentación y transporte local diario.

No incluye [[Hospedaje]] ni [[Vuelos]] — esos son registros separados.

## Cómo se calcula
La tarifa diaria está definida en el [[Tabulador]] como `VIÁTICO_DÍA` por puesto.

```
Viáticos por persona = días_presentes × VIÁTICO_DÍA (del puesto en Tabulador)

Ejemplo — Armador (VIÁTICO_DÍA = $500):
  15 días presentes × $500 = $7,500
```

Los días presentes incluyen todos los días desde llegada hasta salida,
incluido el día [[Tipo de Dia|Previo]] y los días de desmontaje.

## Atributos
- `persona` → [[Persona]]
- `evento` → [[Evento]]
- `dias_cubiertos` — desde llegada hasta salida
- `monto_diario` — tomado de [[Tabulador]] según puesto
- `total` — dias_cubiertos × monto_diario
- `estado` — Pendiente / Aprobado / Pagado
- `forma_pago` — Adelanto / Transferencia / Reembolso

## Anticipo vs liquidación
Por lo general se entrega un **anticipo** antes de que el personal viaje
y se **liquida** la diferencia después del evento según días reales.

## Relaciones
- Su tarifa viene del [[Tabulador]] (`VIÁTICO_DÍA` del puesto)
- Coordinado por [[Logistica de Personal]] y [[Administración]]
- Su costo impacta la sección "Logística Personal" de la [[ODS]]
- Número de días vinculado a los [[Turno]]s del personal
