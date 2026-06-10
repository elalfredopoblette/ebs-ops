## ¿Qué es?
Una Reserva es el bloqueo preventivo de un [[Recurso]] para un [[Evento]]
que aún no está confirmado pero tiene alta probabilidad de ocurrir.

Es una [[Asignacion]] en estado **Tentativa** —
no bloquea definitivamente el recurso, pero lo marca como comprometido
probable y genera una alerta si alguien intenta asignarlo a otro Evento
en el mismo [[Periodo]].

## ¿Cuándo se usa?
- El cliente dio luz verde verbal pero aún no firma contrato
- Se está en proceso de cotización y se quiere "apartar" el recurso
- Se anticipa demanda antes de recibir el [[Brief]] formal

## Diferencia clave con Asignación Confirmada
| | Reserva (Tentativa) | Asignación Confirmada |
|---|---|---|
| Bloquea el recurso | No (solo advierte) | Sí |
| Aparece en ODS | No | Sí |
| Genera Conflicto | Solo alerta | Bloquea |
| Requiere aprobación | No | Sí |

## Atributos
- Es una [[Asignacion]] con estado = Tentativa
- `fecha_expiracion` — hasta cuándo es válida la reserva
- `motivo` — por qué se reserva sin confirmar
- `probabilidad` — alta / media (criterio del PM)

## Ciclo de vida
Tentativa (Reserva) → Reservada → Confirmada (si el Evento se confirma)
                    → Cancelada (si el Evento no prospera)

## Reglas
- Una Reserva no impide crear otra Reserva del mismo recurso en el mismo periodo
  (puede haber dos eventos tentando el mismo recurso)
- Cuando una Reserva pasa a Confirmada, las otras Reservas del mismo
  recurso y periodo generan un [[Conflicto]] que debe resolverse
- Una Reserva sin confirmar después de su `fecha_expiracion` se cancela automáticamente

## Relaciones
- Es una [[Asignacion]] en estado específico
- Puede evolucionar a Asignación Confirmada
- Puede generar [[Conflicto]] cuando se confirma junto a otra del mismo recurso
