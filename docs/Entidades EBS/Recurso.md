
## ¿Qué es?
Un recurso es cualquier elemento limitado que puede ser asignado a un 
evento durante un periodo determinado.
Los recursos tienen disponibilidad finita y pueden agotarse o 
comprometerse simultáneamente con otros proyectos.

## Características
- Tiene disponibilidad limitada.
- Tiene ubicación actual.
- Tiene estado en todo momento.
- Puede asignarse a un [[Evento]].
- Puede reservarse mediante una [[Reserva]].
- Puede liberarse al cerrar un [[Evento]].
- Puede generar [[Conflicto]] de disponibilidad.

## Tipos de Recurso
| Tipo        | Ejemplos                                                                                                          | ¿Es único?      |
| ----------- | ----------------------------------------------------------------------------------------------------------------- | --------------- |
| Steel       | Roof System, Delay Towers, Scaffold                                                                               | Por unidad      |
| EPS         | Arena Light Panel, LD Rolls, EPS Pro, GIGS Barricade, Cable Protectors                                            | Por m² o piezas |
| Vehículo    | Sprinter, camión                                                                                                  | Por unidad      |
| Persona     | Supervisor EPS, Auxiliar EPS, Armador Nomina, Armador Eventual, Jefe de Cuadrilla, Jefe de Steel, Project Manager | Por persona     |
| Herramienta | Taladros, Motores, Bombas de Agua, Computadoras, etc.                                                             | Por unidad      |
| Temporal    | Recurso proveniente de una [[Renta]] confirmada. Se trata como propio durante su vigencia. Ver [[Recurso Temporal]] | Por unidad o m² |

## Atributos comunes
- `id` — identificador único
- `nombre`
- `tipo` — de la tabla anterior
- `estado` — ver Estados posibles
- `ubicacion_actual` — almacén, venue, tránsito
- `proyecto_activo` → [[Proyecto]]
- `evento_activo` → [[Evento]]

## Atributos por tipo

### Estructura / Piso EPS
- `cantidad_total`
- `cantidad_disponible`
- `unidad` — piezas, m², kits

### Vehículo
- `placa`
- `capacidad_carga`
- `operador` → [[Entidades EBS/Persona]]

### Persona
- `rol` → [[Roles]]
- `disponibilidad_semanal`
- `contrato` — nómina  + destajo / externo / freelance

## Estados posibles
- **Disponible** — en almacén, sin compromiso
- **Reservado** — comprometido a futuro, aún no sale
- **Asignado** — confirmado en un [[Evento]]
- **En tránsito** — en movimiento hacia o desde venue
- **En operación** — activo en ShowDay
- **En mantenimiento** — no disponible temporalmente
- **Fuera de servicio** — no disponible indefinidamente

## Relaciones
- Un Recurso puede tener muchas [[Asignacion]]es (en distintos periodos)
- Un Recurso en dos Asignaciones simultáneas genera un [[Conflicto]]
- La disponibilidad de un Recurso es gestionada por [[Inventario]]
- Un Recurso puede ser cubierto por una [[Renta]] si no está disponible
- Los movimientos físicos de un Recurso generan un [[Movimiento]]

## Lo que NO es un Recurso
- [[Inventario]] — es el estado agregado de los recursos, no un recurso
- [[Producto]] — es la referencia comercial; el Recurso es la instancia física
- [[Servicio]] — no es asignable físicamente