## ¿Qué es?
El Load In es la fase de montaje de un [[Evento]].
Comienza cuando los primeros [[Recurso]]s salen del almacén hacia el [[Venue]]
y termina cuando la estructura está montada y lista para operación.

Es el primer [[Periodo]] activo del Evento.
Durante el Load In, los recursos están comprometidos y no disponibles para otros Eventos.

## Qué ocurre en el Load In
1. **Salida de Almacén** — los recursos salen según el [[Despiece]]
2. **Transporte** — [[Vehículo]]s trasladan material al Venue
3. **Llegada al Venue** — descarga y verificación contra [[Despiece]]
4. **Montaje** — el equipo de [[Entidades EBS/Persona]]l arma la estructura
5. **Supervisión** — [[Jefe de Steel]] o [[Supervisor EPS]] valida avance
6. **Inspección final** — estructura lista para ShowDay

## Quién participa
| Rol | Responsabilidad |
|---|---|
| [[Project Manager]] | Coordinación general, comunicación con cliente |
| [[Jefe de Steel]] | Dirección del montaje STEEL |
| [[Supervisor EPS]] | Dirección del montaje EPS |
| Armadores | Ejecución del montaje |
| [[Logistica de Carga]] | Transporte de material |

## Atributos del periodo
- `fecha_inicio` — primera salida de almacén o primer camión al Venue
- `fecha_fin` — estructura montada y aprobada
- `venue` → [[Venue]]
- `evento` → [[Evento]]

## Riesgos operativos
- Recurso faltante detectado en campo → activa [[Requerimiento]] urgente
- Acceso restringido al Venue → retrasa inicio, ajusta [[Turno]]s
- Material dañado en tránsito → puede requerir [[Renta]] de emergencia

## Relaciones
- Es el primer [[Periodo]] del [[Evento]]
- Depende de que la [[Salida de Almacen]] esté completa
- Sus [[Turno]]s definen las horas de cada [[Entidades EBS/Persona]]
- Al terminar, el Evento pasa de "En planeación" a "En operación"
