## ¿Qué es?
El Proyecto es la unidad de negocio que agrupa uno o más [[Evento]]s
bajo un mismo [[Cliente]], [[Contrato]] y contexto comercial.

## Proyecto vs Evento
Esta distinción es crítica en el modelo de dominio EBS:

| | Proyecto | Evento |
|---|---|---|
| ¿Qué es? | Unidad comercial y contractual | Unidad operativa de ejecución |
| ¿Quién lo maneja? | [[Gerente Comercial]] y [[Gerente Operaciones]] | [[Project Manager]] |
| ¿Cuántos puede haber? | Uno por contrato | Uno o más por proyecto |
| ¿Dónde vive parte de él? | En Odoo (cotización, contrato) | En este sistema (planeación, ejecución) |
| ¿Tiene recursos asignados? | No directamente | Sí, via [[Asignacion]] |

## Ejemplos
- Proyecto simple: un contrato = un evento = una fecha en una ciudad
- Proyecto multi-evento ([[Gira]]): un contrato = múltiples eventos en diferentes ciudades y fechas

## Atributos
- nombre, cliente → [[Cliente]]
- contrato → [[Contrato]] (referencia a Odoo)
- estado — Prospecto / Confirmado / En ejecución / Cerrado / Cancelado
- eventos → lista de [[Evento]]s
- tipo — Simple / Gira

## Estado
Prospecto → Confirmado → En ejecución → Cerrado / Cancelado

La transición Prospecto → Confirmado ocurre cuando el [[Contrato]] se firma.

## Relaciones
- Un Proyecto tiene uno o más [[Evento]]s
- Nace del [[Brief]] y la [[Cotización]] (ambos en Odoo)
- Se confirma con el [[Contrato]] (Odoo)
- Sus costos consolidados vienen de los [[Costos]] de cada [[Evento]]
