## ¿Qué es?
La Orden de Compra (ODC) es el documento formal que autoriza a un
[[Proveedor Externo]] a entregar bienes o servicios a EBS a cambio de pago.

> La ODC se genera en **Odoo**. Este sistema la referencia como confirmación
> de que una [[Renta]] o [[Compra]] fue autorizada formalmente.

## Cuándo se genera
- Cuando una [[Renta]] pasa a estado **Aprobada** → se genera ODC de renta
- Cuando una [[Compra]] es aprobada por [[Gerente Operaciones]] → se genera ODC de compra

## Qué contiene
- Número de ODC (referencia de Odoo)
- Proveedor → [[Proveedor Externo]]
- Descripción del bien o servicio
- Cantidad, precio unitario, total
- Fechas de entrega o vigencia
- Condiciones de pago
- Firma de autorización

## Diferencia con la ODS
| ODC | ODS |
|---|---|
| Para proveedores **externos** | Para proveedores **internos** |
| Compra o renta de recursos | Ejecución de servicios EBS |
| Generada en Odoo | Generada por el PM en este sistema |
| Vinculada a un [[Proveedor Externo]] | Vinculada a un [[Evento]] |

## Relaciones
- Nace de una [[Renta]] aprobada o una [[Compra]] aprobada
- Referenciada en este sistema como `odc_referencia` en la [[Renta]]
- Procesada y pagada por [[Administración]] via Odoo
