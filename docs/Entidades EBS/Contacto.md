## ¿Qué es?
Persona física dentro del [[Cliente]] con quien EBS se comunica
directamente para un [[Proyecto]] o [[Evento]].

> Vive en **Odoo** — este sistema lo referencia para saber a quién llamar en campo.

## Tipos
| Tipo | Relación con EBS |
|---|---|
| Contacto Comercial | Negocia contratos. Habla con Gerente Comercial EBS |
| Contacto de Producción | Coordina operaciones en venue. Habla con PM EBS |
| Contacto Técnico | Define specs. Habla con Jefe de Steel / Supervisor EPS |

## Atributos
- `id`, `cliente` → [[Cliente]], `nombre`, `rol`
- `telefono`, `email`, `notas`

## Relaciones
- Pertenece a un [[Cliente]]
- El PM lo usa como referencia de contacto durante la ejecución
