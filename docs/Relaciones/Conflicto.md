
## ¿Qué es?
Un Conflicto es la condición que ocurre cuando un [[Recurso]] tiene
dos o más [[Asignacion]]es cuyo [[Periodo]] se solapa.

El Conflicto no es un error del sistema — es una realidad operativa
que el sistema debe detectar, exponer y forzar a resolver.

## Ejemplos
- Supervisor EPS asignado a 260606_FANFEST_GDL
 y a 260606_YURIDIA_ZACATEPEC el mismo fin de semana
- Sprinter 2 requerida en Guadalajara y en CDMX simultáneamente
- 300 m² de LD Roll comprometidos en dos eventos con fechas solapadas
- Jefe de Steel en Load Out de Evento X y Load In de Evento Y el mismo día

## ¿Cuándo ocurre?
Cuando:
1. Existe una [[Asignacion]] A confirmada para un [[Recurso]] en un [[Periodo]]
2. Se intenta crear una [[Asignacion]] B para el mismo [[Recurso]]
3. El Periodo de B se solapa con el Periodo de A

## Atributos
- `id`
- `recurso` → [[Recurso]]
- `asignacion_a` → [[Asignacion]]
- `asignacion_b` → [[Asignacion]]
- `periodo_conflicto` → [[Periodo]]
- `estado` — ver Estados
- `detectado_en` — datetime
- `resuelto_en` — datetime
- `resuelto_por` → [[Roles]]
- `resolucion` — descripción de cómo se cerró
- `notas`

## Estados posibles
- **Detectado** — el sistema lo identificó, nadie lo ha atendido
- **En revisión** — Operaciones está evaluando opciones
- **Resuelto** — se tomó una decisión y se ejecutó
- **Ignorado** — se decidió aceptar el riesgo conscientemente

## Formas de resolución
| Resolución | Descripción |
|---|---|
| Reasignación | Se mueve uno de los eventos a otro recurso disponible |
| Renta | Se cubre la necesidad con recurso externo → [[Renta]] |
| Reprogramación | Se ajustan fechas del [[Periodo]] en uno de los eventos |
| Cancelación | Se cancela una de las [[Asignacion]]es |
| Aceptado con riesgo | Operaciones decide continuar sabiendo el conflicto |

## Reglas críticas
- El sistema debe detectar Conflictos automáticamente al crear
  o modificar una [[Asignacion]]
- Un Conflicto **Detectado** debe bloquear o advertir — nunca
  silenciarse solo
- El estado **Ignorado** requiere autorización explícita de
  [[Gerente Operaciones]]
- Todo Conflicto resuelto debe documentar cómo se resolvió

## Relaciones
- Existe porque dos [[Asignacion]]es comparten [[Recurso]] y [[Periodo]]
- Puede nacer de un [[Requerimiento]] no resuelto
- Su resolución genera una [[Renta]], una reasignación, o una cancelación
- Debe ser visible en el [[Inventario]] del recurso afectado