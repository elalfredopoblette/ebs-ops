## ¿Qué es?
Una Gira es un [[Proyecto]] de tipo `Gira` — múltiples [[Evento]]s
en diferentes ciudades o fechas, con los mismos recursos moviéndose
de venue en venue sin regresar al almacén entre paradas.

> **Nota de modelo:** Gira no es un Aggregate separado. Es el comportamiento
> especial que tiene un Proyecto cuando `tipo = Gira`. Esta nota documenta
> ese comportamiento diferencial.

## Qué lo hace diferente a un Proyecto simple

| | Proyecto Simple | Proyecto tipo Gira |
|---|---|---|
| Eventos | 1 | 2 o más en secuencia |
| Recursos entre eventos | Regresan al almacén | Van directo al siguiente venue |
| Cross Check | Por evento | Por bloque completo de la Gira |
| Movimientos | Salida / Entrada | Salida / Traslado / Traslado / Entrada |
| Costos de logística | Local | Incluye flete internacional, aduana, carnets ATA |
| Pago al personal | Tabulador estándar | Personal enviado a LATAM: monto cerrado individual |

## Ejemplo real
EDC México gira latinoamericana:
- Evento 1: Ciudad de México, 15–17 mayo
- Evento 2: Bogotá, 22–24 mayo
- Evento 3: Santiago, 29–31 mayo

El Roof System sale de CDMX, va directo a Bogotá, luego a Santiago.
No toca el almacén de EBS en ningún tramo intermedio.

## Regla crítica de disponibilidad
El [[Cross Check de Disponibilidad]] debe correr sobre el **periodo total
de la Gira** (desde el primer Load In hasta el último Load Out).

Un recurso disponible para el Evento 1 pero comprometido durante el Evento 3
invalida su uso en toda la Gira — no se puede liberar entre paradas.

## Atributos adicionales del Proyecto tipo Gira
- `eventos` — lista ordenada cronológicamente
- `periodo_total` — desde inicio Evento 1 hasta fin último Evento
- `logistica_internacional` — bool
- `pago_personal_latam` — monto cerrado por persona (no aplica tabulador)

## Movimientos en Gira
Los [[Movimiento]]s incluyen tipo **Traslado** (Venue A → Venue B)
que no pasa por almacén EBS. El [[Almacen]] solo ve la Salida inicial
y la Entrada final al terminar toda la Gira.

## Relaciones
- Es un [[Proyecto]] con `tipo = Gira`
- Sus recursos generan [[Movimiento]]s de tipo Traslado
- El [[Inventario]] los bloquea durante todo el bloque de la Gira
