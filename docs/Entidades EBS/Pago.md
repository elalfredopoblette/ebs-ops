## ¿Qué es?
Transferencia de dinero que EBS realiza a proveedores o personal eventual
en relación con un [[Evento]].

> Pagos formales (facturas, transferencias) viven en **Odoo**.
> Este sistema registra pagos operativos que requieren seguimiento en campo.

## Tipos
| Tipo | Destinatario | Cuándo |
|---|---|---|
| Destajo | Personal eventual | Al terminar el evento o por día |
| Anticipo de viáticos | Personal foráneo | Antes del [[Load In]] |
| Pago a proveedor de renta | [[Proveedor Externo]] | Según acuerdo |
| Reembolso | Personal | Post-evento |

## Atributos
- `id`, `evento` → [[Evento]], `destinatario`, `tipo`
- `monto`, `fecha`, `estado` — Pendiente / Aprobado / Pagado
- `aprobado_por` → [[Roles]]
- `referencia_odoo`

## Relaciones
- Pagos a personal de destajo derivan de [[Turno]]s registrados
- Pagos a proveedores derivan de [[Renta]]s confirmadas
- Coordinado por [[Administración]] y [[Pagos Por Evento (destajos)]]
