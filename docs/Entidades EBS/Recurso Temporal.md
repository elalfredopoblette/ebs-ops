## ¿Qué es?
Un Recurso Temporal es un [[Recurso]] que EBS incorpora a su operación
mediante una [[Renta]], durante el periodo de vigencia de esa renta.

Se trata exactamente igual que un recurso propio dentro del evento:
aparece en el [[Despiece]], tiene [[Asignacion]], genera [[Movimiento]]s
y el proveedor cobra los faltantes al cierre.

> "Se vuelve nuestro hasta que se regresa."

## Por qué existe como entidad separada
Un recurso rentado NO entra al inventario permanente de EBS.
Pero SÍ necesita seguimiento operativo completo durante su uso.
Al cerrar la [[Renta]], el Recurso Temporal se desactiva y sale del [[Inventario]].

## Ciclo de vida
```
Renta Confirmada
      ↓
Recurso Temporal creado → estado: Disponible (en bodega del proveedor)
      ↓
Movimiento de entrega (proveedor → venue o almacén EBS)
      ↓
Asignado al Evento
      ↓
En operación
      ↓
Movimiento de devolución (venue → proveedor)
      ↓
Renta Cerrada → Recurso Temporal desactivado
```

## Atributos
- `recurso_base` — descripción del tipo de recurso rentado
- `renta` → [[Renta]] (origen)
- `evento` → [[Evento]]
- `cantidad`
- `unidad`
- `proveedor` → [[Proveedor Externo]]
- `fecha_inicio`, `fecha_fin` — igual que la Renta
- `estado` — Disponible / En tránsito / Asignado / En operación / Devuelto
- `estado_al_devolver` — completo / con faltantes / dañado

## Responsabilidad sobre faltantes
Si al devolver hay piezas faltantes o dañadas, el proveedor cobra el diferencial.
Por eso el [[Almacen]] debe hacer inventario detallado antes de la devolución.
El [[Jefe de Steel]] o [[Supervisor EPS]] son responsables del cuidado en campo.

## Diferencia con Recurso propio
| Recurso propio | Recurso Temporal |
|---|---|
| Inventario permanente | Inventario temporal |
| No genera costo al usarse | Su uso tiene costo de renta |
| Al dañarse: mantenimiento interno/externo | Al dañarse: cargo por el proveedor |
| Permanece en EBS al terminar | Se devuelve al proveedor |

## Relaciones
- Nace de una [[Renta]] Confirmada
- Se comporta como [[Recurso]] durante su vigencia
- Sus [[Movimiento]]s incluyen entrega y devolución al [[Proveedor Externo]]
- Al cerrarse la [[Renta]], sale del [[Inventario]]
