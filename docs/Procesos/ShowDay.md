## ¿Qué es?
El ShowDay es la fase de operación activa de un [[Evento]].
Es el día (o días) en que el espectáculo se realiza con público presente.

Los [[Recurso]]s están plenamente comprometidos.
Los errores tienen consecuencias inmediatas y visibles.

## Duración
Un ShowDay puede ser uno o varios días consecutivos.
EDC México tiene 3 ShowDays — el Evento no se interrumpe entre ellos
y los recursos no se liberan entre días.

## Qué ocurre en el ShowDay
1. Verificación de estructura antes de apertura al público
2. Personal en stand-by durante la función
3. Atención de incidencias en tiempo real
4. Coordinación con producción del cliente
5. Cierre de operaciones al terminar el último día

## Quién participa
| Rol | Responsabilidad |
|---|---|
| [[Project Manager]] | Punto de contacto con cliente, decisiones |
| [[Supervisor EPS]] | Stand-by EPS, atención de incidencias |
| [[Jefe de Steel]] | Stand-by STEEL, supervisión estructural |
| Personal de soporte | Presencia durante función según contrato |

## Atributos del periodo
- `fecha_inicio` — apertura del primer ShowDay
- `fecha_fin` — cierre del último ShowDay
- `num_showdays` — número de días de función
- `evento` → [[Evento]]

## Regla operativa importante
Los recursos NO se liberan entre ShowDays consecutivos aunque no estén
siendo usados activamente. El compromiso es por todo el bloque hasta
el fin del [[Load Out]].

## Relaciones
- Es el [[Periodo]] central del [[Evento]] (entre [[Load In]] y [[Load Out]])
- Sus [[Turno]]s suelen ser los más intensivos
- Los [[Viaticos]] acumulan por cada día de ShowDay
- Al terminar el último ShowDay inicia el [[Load Out]]
