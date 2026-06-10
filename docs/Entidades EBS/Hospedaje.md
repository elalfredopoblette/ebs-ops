## ¿Qué es?
Alojamiento contratado para el personal que trabaja en un [[Evento]]
fuera de su ciudad base.

Es un gasto logístico registrado por separado de [[Viaticos]] y [[Vuelos]].

## Cuándo aplica
Cuando una [[Persona]] tiene `ciudad_base` diferente a la ciudad del [[Venue]].
El [[Gerente Operaciones]] siempre programa llegada un día antes del primer
turno activo — el día **Previo** (ver [[Tipo de Dia]]) — para garantizar descanso.

## Atributos
- `persona` → [[Persona]]
- `evento` → [[Evento]]
- `hotel`, `ciudad`
- `fecha_check_in`, `fecha_check_out`
- `noches` — calculado desde fechas
- `costo_por_noche`
- `costo_total` — noches × costo_por_noche
- `estado` — Pendiente / Reservado / Confirmado / Cancelado

## Diferencia con Viáticos
| Hospedaje | Viáticos |
|---|---|
| Alojamiento (hotel) | Manutención diaria (comida, transporte local) |
| Pago único o por reserva | Pago por día activo |
| Coordinado por [[Logistica de Personal]] | Tarifa del [[Tabulador]] (`VIÁTICO_DÍA`) |

## Relaciones
- Coordinado por [[Logistica de Personal]]
- Su costo impacta la sección "Logística Personal" de la [[ODS]]
- Pagado por [[Administración]]
