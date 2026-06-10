## ¿Qué es?
La ODS (Orden de Servicio) es el documento formal que comunica las
decisiones operativas tomadas para un [[Evento]].

No es el centro del sistema — es una consecuencia.
Cuando todas las [[Asignacion]]es están confirmadas y los [[Requerimiento]]s
resueltos, la ODS se genera como resumen ejecutivo de lo que se va a operar.

## Principio fundamental
> La ODS documenta decisiones ya tomadas.
> No se toman decisiones al generar la ODS.
> Si hay algo sin resolver al momento de generarla, el problema no es la ODS —
> el problema es que el [[Evento]] no está listo.

## ¿Qué contiene?
- Datos del [[Evento]] y [[Proyecto]]
- [[Venue]] y fechas de cada fase (Load In, ShowDay, Load Out)
- [[Recurso]]s asignados con cantidades
- [[Persona]]l asignado con [[Roles]]
- [[Vehículo]]s asignados
- [[Renta]]s activas (recursos externos incluidos)
- Costos operativos totales
- Responsable ([[Project Manager]])

## ¿Quién la genera?
El [[Project Manager]], cuando el [[Evento]] alcanza el estado **Listo**.

## ¿Quién la usa?
- **Operaciones** — como guía de ejecución en campo
- **Almacén** — para preparar la [[Salida de Almacen]]
- **Logística de Carga** — para planificar viajes y cargas
- **Dirección** — como documento de aprobación final
- **Comercial** — para seguimiento con el [[Cliente]]

## Cuándo se genera
Solo cuando el [[Evento]] está en estado **Listo**:
- Todos los [[Requerimiento]]s resueltos
- Todas las [[Asignacion]]es confirmadas
- Ningún [[Conflicto]] en estado Detectado
- [[Despiece]] aprobado

## Relaciones
- Se genera a partir de un [[Evento]] en estado Listo
- Resume todas las [[Asignacion]]es activas del Evento
- Incluye todas las [[Renta]]s confirmadas
- Es la entrada para [[Salida de Almacen]] y [[Logistica de Carga]]
- En Odoo puede generar o actualizarse contra la factura del servicio

## Lo que NO es
- No es donde se deciden los recursos (eso es el [[Cross Check de Disponibilidad]])
- No es el presupuesto (eso es en Odoo / [[Presupuesto]])
- No es el [[Brief]] ni la [[Cotización]]
