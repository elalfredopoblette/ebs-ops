## ¿Qué es?
Acuerdo formal entre EBS y el [[Cliente]] que define alcance, condiciones
y precio de los servicios para un [[Proyecto]].

> Vive en **Odoo** y en Administración.
> Este sistema lo referencia como señal de que el [[Proyecto]] está confirmado.

## Por qué importa operativamente
Un Contrato firmado habilita iniciar la [[Planeacion Operativa]].
Sin contrato, el [[Evento]] no puede pasar de Prospecto a Confirmado.

## Estados relevantes
| Estado | Significado operativo |
|---|---|
| En negociación | [[Evento]] en estado Prospecto |
| Firmado | [[Evento]] puede confirmarse |
| Modificado | Puede requerir re-planeación del [[Evento]] |
| Cancelado | Libera todas las [[Asignacion]]es del [[Evento]] |

## Relaciones
- Pertenece a un [[Proyecto]]
- Su firma activa el estado Confirmado del [[Evento]]
- Su cancelación libera todas las [[Asignacion]]es
