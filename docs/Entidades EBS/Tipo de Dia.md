## ¿Qué es?
Clasificación de cada día de trabajo en un [[Evento]] según el tipo
de actividad realizada. El tipo de día determina el valor en puntos
que se usa para calcular el pago en el [[Tabulador]].

## Tipos de día

| Tipo | Puntos | Cuándo aplica |
|---|---|---|
| Previo | 0.5 | Día de viaje/traslado antes del [[Load In]]. El personal llega, se hospeda y descansa. |
| Montaje | 1.5 | Días de trabajo intensivo de armado de estructura ([[Load In]]). |
| Show | 0.5 | Días de función con público ([[ShowDay]]). Personal en stand-by. |
| Guardia | 0.5 | Días de vigilancia de estructura entre fases. Trabajo menor, sin alcanzar nivel de Montaje. |
| Desmontaje | 1.5 | Días de trabajo intensivo de desarmado ([[Load Out]]). |

## El día Previo
El [[Gerente Operaciones]] siempre programa un día Previo antes del primer
día de Montaje. El personal viaja, llega a su [[Hospedaje]] y descansa
para rendir al máximo en su primer turno activo.

## El día Guardia y su posible conversión
Un día clasificado como Guardia (0.5 pts) puede convertirse en Montaje (1.5 pts)
si el [[Jefe de Steel]] o [[Supervisor EPS]] reporta que el trabajo realizado
justifica el cambio. La decisión final la toma el [[Gerente Operaciones]] personalmente.

Esta regla existe porque la diferencia de puntos impacta el pago de todos
los trabajadores de ese día y requiere validación de quien controla el presupuesto.

## Relación con el cálculo de pago
```
Pago por día = puntos_del_tipo × VALOR_X_PUNTO (del puesto en [[Tabulador]])

Ejemplo — Jefe de Steel en día de Montaje:
  1.5 pts × $800/pto = $1,200 ese día
  
Ejemplo — Jefe de Steel en día de Show:
  0.5 pts × $800/pto = $400 ese día
```

## Relaciones
- Define el valor de cada [[Turno]]
- Usado por [[Tabulador]] para calcular pago total
- Asignado durante la [[Procesos/Proyeccion|Proyección]] del evento
