## ¿Qué es?
Categoría contable dentro de cada [[Proveedor Interno]] que agrupa
los costos de un [[Evento]] para efectos de clasificación y seguimiento
de presupuesto.

Cada línea de pago se identifica con la jerarquía:
```
CENTRO_DE_COSTO → PROVEEDOR_INTERNO → SUBCUENTA → ÁREA/SERVICIO → DETALLE
```

## Subcuentas por Proveedor Interno

| Proveedor Interno | Subcuenta | Qué agrupa |
|---|---|---|
| Logística Transportes | Transportes de Carga | Renta de unidades (Drop Deck, Dry Van, Plataforma) + estadías |
| Operaciones | PXE | Pago destajo a cada [[Persona]] recurso por [[Turno]]s ejecutados |
| Logística Personal | Viáticos | Viático diario por persona |
| Logística Personal | Hospedaje | Costo de hotel por persona por noche |
| Logística Personal | Traslado de Personal | Sprinter, avión, autobús, plataformas, renta auto PM |
| Compras | Extras | Subrenta Scaffold, motores, pipas, personal eventual externo, otros |

## Por qué importa
- Permite comparar presupuesto vs real **por subcuenta** en el [[Cierre de Evento]]
- Define qué área de EBS es responsable de gestionar ese gasto
- Tesorería usa la subcuenta para registrar el egreso en contabilidad
- El [[Presupuesto]] de la [[ODS]] se aprueba por sección de Proveedor Interno

## Relaciones
- Pertenece a un [[Proveedor Interno]]
- Agrupa [[Pago]]s dentro de un [[Evento]]
- Se origina en la [[Procesos/Proyeccion|Proyección]] operativa
- Su comparativo real vs proyectado forma parte del [[Cierre de Evento]]
