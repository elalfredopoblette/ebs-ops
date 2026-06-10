## ¿Qué es?
El Load Out es la fase de desmontaje de un [[Evento]].
Comienza al terminar el último [[ShowDay]] y termina cuando todos los
[[Recurso]]s están de regreso en el almacén o en su siguiente destino.

Es el último [[Periodo]] del Evento y el momento donde los recursos
se liberan y el [[Inventario]] se actualiza.

## Qué ocurre en el Load Out
1. **Desmontaje** — equipo desmonta en orden inverso al [[Load In]]
2. **Verificación** — se compara contra [[Despiece]] para detectar faltantes o daños
3. **Carga** — material se embala y sube a [[Vehículo]]s
4. **Transporte** — traslado de regreso al almacén
5. **Entrada al Almacén** — recepción, conteo y registro del estado de cada recurso
6. **Cierre del Evento** — el [[Evento]] pasa a estado Cerrado

## Por qué es crítico
Si el Load Out no se registra correctamente:
- Recursos aparecen comprometidos cuando ya están libres
- El [[Inventario]] está desactualizado
- El próximo [[Cross Check de Disponibilidad]] puede bloquear recursos disponibles

## Quién participa
| Rol | Responsabilidad |
|---|---|
| [[Project Manager]] | Cierre con cliente, firma de conformidad |
| [[Jefe de Steel]] | Supervisión desmontaje STEEL |
| [[Supervisor EPS]] | Supervisión desmontaje EPS |
| Almacén | Recepción y registro en destino |
| [[Logistica de Carga]] | Transporte de regreso |

## Relaciones
- Es el último [[Periodo]] del [[Evento]]
- Al terminar, todas las [[Asignacion]]es pasan a estado Liberadas
- Genera [[Movimiento]]s de entrada al almacén
- Actualiza el [[Inventario]] con disponibilidad y estado real
- Puede reportar daños que cambian el estado del [[Recurso]]
