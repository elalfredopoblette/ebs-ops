## ¿Qué es?
Un Proveedor Externo es una empresa o persona que suministra [[Recurso]]s
o servicios a EBS cuando el inventario propio no es suficiente.

Es el actor que hace posible la [[Renta]].

## Tipos de Proveedor Externo
| Tipo | Qué provee | Ejemplos |
|---|---|---|
| Proveedor STEEL | Estructuras, piezas, Scaffold | Otras empresas de estructuras temporales |
| Proveedor EPS | LD Rolls, Arena Panels, Barricadas | Empresas de pisos y crowd control |
| Proveedor de Transporte | Vehículos, camiones | Agencias de renta de vehículos |
| Proveedor de Personal | Armadores, supervisores freelance | Agencias de personal técnico |
| Proveedor de Herramienta | Equipo técnico especializado | Rentas de maquinaria |

## Atributos
- `id`
- `nombre`
- `tipo` — de la tabla anterior
- `contacto_principal`
- `telefono`
- `email`
- `ciudad`
- `recursos_que_provee[]` — catálogo de lo que puede rentar
- `tiempo_respuesta_cotizacion` — referencia para planeación
- `calificacion` — histórico de cumplimiento (1–5)
- `activo` — boolean

## Relaciones
- Provee [[Recurso]]s a través de una [[Renta]]
- Su tiempo de respuesta impacta el estado del [[Requerimiento]]
- Su historial de cumplimiento informa decisiones de [[Gerente Operaciones]]

## Nota importante
El contrato formal y el pago al Proveedor Externo se gestionan en **Odoo**
a través de una ODC (Orden de Compra).
Este sistema solo registra qué proveedor cubre qué [[Renta]].
