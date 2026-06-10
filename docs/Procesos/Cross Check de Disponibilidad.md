## ¿Qué es?
El Cross Check de Disponibilidad es el proceso central de planeación
donde se verifica si los [[Recurso]]s requeridos para un [[Evento]] están
disponibles en las fechas necesarias.

Es el momento donde el dominio toma decisiones:
¿con propio o con [[Renta]]?

## Cuándo ocurre
Después de recibir el [[Despiece]] aprobado y antes de confirmar las
[[Asignacion]]es. Idealmente, antes de generar la [[ODS]].

> El problema actual de EBS es que este proceso ocurre **después** de
> la ODS — cuando el recurso ya fue prometido al cliente.
> El sistema debe moverlo **antes**.

## Entradas
- [[Despiece]] aprobado (lista de recursos requeridos)
- [[Inventario]] actual de cada recurso
- [[Periodo]]s del Evento (Load In, ShowDay, Load Out)
- [[Asignacion]]es activas en ese mismo periodo (otros Eventos)

## Proceso paso a paso
1. Por cada ítem del [[Despiece]], se crea un [[Requerimiento]]
2. Se consulta el [[Inventario]] del recurso en ese [[Periodo]]
3. **Si hay disponibilidad** → se crea [[Asignacion]] en estado Tentativa
4. **Si no hay disponibilidad** → el Requerimiento queda Sin resolver
5. Se busca alternativa: otro recurso del mismo tipo, reasignación o [[Renta]]
6. Si se resuelve con Renta → se inicia proceso de cotización con [[Proveedor Externo]]
7. Todos los [[Conflicto]]s detectados se exponen y se resuelven
8. Cuando todos los Requerimientos están resueltos → Asignaciones pasan a Confirmadas
9. El [[Evento]] avanza a estado **Listo**

## Salidas
- Todas las [[Asignacion]]es en estado Confirmado
- Todos los [[Requerimiento]]s resueltos
- [[Conflicto]]s cerrados
- [[Renta]]s iniciadas para lo que no había propio
- [[Evento]] listo para generar [[ODS]]

## Quién lo ejecuta
[[Project Manager]] con apoyo de [[Gerente Operaciones]] para decisiones
de Renta y resolución de Conflictos.

## Regla crítica
Ninguna [[ODS]] debe generarse si el Cross Check no está completo.
Un Evento con Requerimientos sin resolver no está listo.

## Relaciones
- Consume el [[Despiece]] como entrada
- Consulta el [[Inventario]]
- Genera o confirma [[Asignacion]]es
- Detecta [[Conflicto]]s
- Inicia [[Renta]]s
- Su completitud habilita la generación de [[ODS]]
