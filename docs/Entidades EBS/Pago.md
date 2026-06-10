## ¿Qué es?
Transferencia de dinero que EBS realiza a [[Proveedor Interno]]s, [[Proveedor Externo]]s
o personal en relación con un [[Evento]].

> Pagos formales (facturas, transferencias) viven en **Odoo**.
> Este sistema registra la estructura, montos y fechas planificadas de pago.

## Estructura de pago por tipo

### Transportes de Carga (Logística Transportes)
Dos desembolsos por contrato de unidad:
- **Anticipo** — 60% del total, ~2 semanas antes del Load In
- **Finiquito** — 40% restante, post Load Out

### PXE — Operaciones
Pago único a cada [[Persona]] recurso al cerrar el evento.
- Monto: calculado de los [[Turno]]s aprobados por [[Gerente Operaciones]]
- Fecha: semana del show o siguiente
- **DISPERSIÓN**: fecha individual por persona en que recibe su pago

### Logística Personal
Tres subcuentas con fechas independientes:
- **Viáticos** — pago único antes del evento (crew debe tener efectivo antes de salir)
- **Hospedaje** — pago único ~2 semanas antes (hotel necesita liquidación anticipada)
- **Traslado de Personal** — pago por tipo (Sprinter, avión, autobús, plataformas)

### Compras / Extras
Variable según acuerdo con cada proveedor externo.

## Concepto SEMANA
Todos los pagos en la [[Procesos/Proyeccion|Proyección]] se planifican con número
de semana ISO (ej. Semana 23, 25, 27). Permite visualizar el flujo de caja
del evento por semana, no solo por fecha.

## Atributos
- `id`
- `evento` → [[Evento]]
- `proveedor_interno` → [[Proveedor Interno]]
- `subcuenta` → [[Subcuenta]]
- `destinatario` — persona o empresa
- `tipo` — Anticipo / Finiquito / Único / Dispersión
- `monto`
- `fecha_pago`
- `semana_pago` — número de semana ISO
- `estado` — Pendiente / Aprobado / Pagado
- `referencia_odoo`

## Relaciones
- Pagos PXE derivan de [[Turno]]s aprobados por [[Gerente Operaciones]]
- Pagos a transportistas derivan del cálculo de [[Logistica Transportes]] en la [[Procesos/Proyeccion|Proyección]]
- Pagos de hospedaje/traslados los gestiona [[Logistica Personal]]
- Toda ODC de pago a externo se genera en Odoo
