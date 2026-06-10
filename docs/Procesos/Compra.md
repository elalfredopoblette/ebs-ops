## ¿Qué es?
Proceso de adquisición de un bien o material que pasa a ser propiedad de EBS.

> A diferencia de una [[Renta]], la Compra agrega un nuevo [[Recurso]] al inventario permanente.

## Cuándo ocurre
- Inventario de un recurso es insuficiente y la demanda futura justifica compra
- Material consumible se agota
- Un recurso se da de baja y necesita reemplazo

## Proceso
1. [[Project Manager]] o [[Gerente Operaciones]] detecta la necesidad
2. Se levanta solicitud de compra al área de [[Compras y Rentas]]
3. [[Compras y Rentas]] cotiza con proveedores
4. [[Gerente Operaciones]] aprueba la compra
5. Odoo genera la Orden de Compra (OC)
6. Material llega al almacén → [[Entrada de Almacen]] especial para nuevos recursos
7. Nuevo [[Recurso]] se registra en el sistema con estado Disponible

## Diferencia con Renta
| Compra | Renta |
|---|---|
| El recurso queda en EBS | El recurso se devuelve |
| Gasto de capital | Gasto operativo |
| Decisión estratégica | Decisión táctica |
| Proceso más largo | Proceso más rápido |

## Relaciones
- Gestionada por [[Compras y Rentas]]
- Registrada en Odoo como OC
- Agrega [[Recurso]] permanente al [[Inventario]]
