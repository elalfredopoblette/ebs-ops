## ¿Qué es?
Área de EBS que actúa como proveedor de servicios hacia los [[Evento]]s,
con su propia lógica, capacidad y costos.

## Proveedores Internos de EBS
| Área | Qué provee |
|---|---|
| [[Almacen]] | Custodia, despacho y recepción de [[Recurso]]s |
| [[Logistica de Carga]] | Transporte de material entre almacén y [[Venue]] |
| [[Logistica de Personal]] | Traslado, [[Vuelos]], [[Hospedaje]] y [[Viaticos]] del personal |
| [[Compras y Rentas]] | Gestión de [[Renta]]s y compras para cubrir faltantes |
| [[Pagos Por Evento (destajos)]] | Cálculo y pago al personal eventual |

## Por qué se modela como proveedor
Cada área tiene capacidad limitada, costo propio y proceso definido.
No pueden atender infinitos eventos simultáneos.

## Relaciones
- Se activan según la fase del [[Evento]]
- Sus costos contribuyen a los [[Costos]] del [[Evento]]
- Coordinados por el [[Project Manager]] y [[Gerente Operaciones]]
