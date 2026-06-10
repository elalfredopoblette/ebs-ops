## ¿Qué es?
Un Turno es la asignación de un bloque horario específico a una [[Persona]]
dentro de una fase de un [[Evento]] (Load In, ShowDay o Load Out).

Mientras la [[Asignacion]] dice "esta persona va a este Evento",
el Turno dice "esta persona trabaja de 06:00 a 18:00 el día X".

## Por qué existe
Un [[Evento]] puede durar varios días. No toda la [[Persona]]l trabaja
las mismas horas ni los mismos días. El Turno permite:
- Distribuir la carga de trabajo
- Calcular viáticos por días trabajados
- Identificar quién está disponible en cada momento
- Cumplir con regulaciones laborales

## Ejemplos
- Armador A: Load In día 1 turno 06:00–18:00, Load In día 2 turno 06:00–14:00
- Supervisor EPS: ShowDay turno completo 08:00–00:00
- Jefe de Steel: Load In días 1–3 turno 07:00–19:00, libre ShowDay, Load Out día 1

## Atributos
- `id`
- `persona` → [[Entidades EBS/Persona]]
- `evento` → [[Evento]]
- `fase` — Load In / ShowDay / Load Out
- `fecha`
- `hora_inicio`
- `hora_fin`
- `horas_totales` — calculado
- `tipo_pago` — nómina / destajo / freelance
- `monto_destajo` — si aplica
- `notas`

## Relaciones
- Pertenece a una [[Asignacion]] de [[Entidades EBS/Persona]]
- Define los días que se calculan [[Viaticos]]
- Es la base para [[Pagos Por Evento (destajos)]]
- Informa a [[Logistica de Personal]] cuándo necesita traslados

## Pregunta abierta
> ¿Los Turnos los define el PM antes del evento o se registran en campo?
> ¿Hay aprobación de Turnos o son solo informativos?
