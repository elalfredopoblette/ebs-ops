## ¿Qué es?
Un Venue es el lugar físico donde se ejecuta un [[Evento]].
No es solo una dirección — es un conjunto de restricciones y condiciones
que impactan directamente la planeación operativa.

## Ejemplos
- Foro Sol, CDMX
- Campo Marte, CDMX
- Estadio Akron, Guadalajara
- Palenque Feria de León
- Centro Banamex, CDMX
- Explanada externa (venue sin estructura fija)

## Por qué importa en el dominio
Dos Eventos idénticos en venues distintos pueden requerir recursos
completamente diferentes: distancias de carga, accesos, restricciones
de altura, disponibilidad de energía, clima.

El Venue es una restricción, no solo un dato de ubicación.

## Atributos
- `id`
- `nombre`
- `ciudad`
- `estado` / `país`
- `direccion`
- `tipo` — Foro cerrado / Explanada / Estadio / Recinto ferial / Otro
- `capacidad_aforo` — referencia general
- `tiene_energia_propia` — boolean (impacta logística de generadores)
- `acceso_vehicular` — restringido / libre / con permiso
- `altura_maxima_estructura` — metros (crítico para Roof Systems)
- `distancia_almacen_km` — distancia desde almacén EBS (impacta logística)
- `notas_operativas` — restricciones especiales, contactos, horarios de acceso

## Impacto operativo
| Restricción del Venue | Impacto en Recursos |
|---|---|
| Altura máxima limitada | Configura qué Roof System es viable |
| Sin acceso vehicular nocturno | Load In debe planificarse en horario específico |
| Lejos del almacén | Más vehículos o viajes, mayor costo de logística |
| Sin energía propia | Se requiere generador (Recurso adicional) |
| Clima exterior | Personal necesita equipo adicional |

## Relaciones
- Un Venue puede tener muchos [[Evento]]s (en distintos momentos)
- El Venue informa qué configuraciones son viables en el [[Despiece]]
- La distancia del Venue impacta [[Logistica de Carga]] y [[Viaticos]]
- Las restricciones del Venue pueden generar [[Requerimiento]]s adicionales
