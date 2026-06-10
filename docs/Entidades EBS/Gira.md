## ¿Qué es?
Una Gira es un [[Proyecto]] que consiste en múltiples [[Evento]]s
en diferentes ciudades o fechas, con los mismos recursos moviéndose
de venue en venue.

## Por qué es un caso especial
En una Gira, los [[Recurso]]s no regresan al almacén entre eventos:
van directo del [[Load Out]] de una ciudad al [[Load In]] de la siguiente.

Esto crea una cadena de dependencias de disponibilidad que el
[[Cross Check de Disponibilidad]] debe manejar de forma especial.

## Ejemplo real
EDC México gira latinoamericana:
- Evento 1: Ciudad de México, 15–17 mayo
- Evento 2: Bogotá, 22–24 mayo
- Evento 3: Santiago, 29–31 mayo

El Roof System sale de CDMX, va directo a Bogotá, luego a Santiago.
No toca el almacén de EBS en ningún tramo intermedio.

## Implicaciones en el modelo

### Disponibilidad
Un recurso en Gira está comprometido durante todo el bloque,
desde el primer Load In hasta el último Load Out.
No puede asignarse a otro evento en ningún punto intermedio.

### Movimientos
Los [[Movimiento]]s en Gira incluyen traslados internacionales:
tipo Traslado (Venue A → Venue B) sin pasar por almacén.

### Costos
Los [[Costos]] de logística internacional (flete, aduana, carnets ATA)
son costos de Gira, no de un evento individual.

## Atributos
- nombre, proyecto → [[Proyecto]]
- eventos → lista de [[Evento]]s en orden cronológico
- logistica_internacional — si hay traslados internacionales
- periodo_total — desde inicio del primer evento hasta fin del último

## Regla crítica
En una Gira, el [[Cross Check de Disponibilidad]] debe correr
para el periodo total de la Gira, no evento por evento.
Un recurso disponible para el Evento 1 pero no para el 3
invalida la Gira completa si es el único disponible.

## Relaciones
- Es un tipo de [[Proyecto]]
- Contiene múltiples [[Evento]]s con orden cronológico
- Sus recursos generan [[Movimiento]]s de tipo Traslado
- Afecta el [[Inventario]] durante todo el bloque de la gira
