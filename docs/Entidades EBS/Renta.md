## ¿Qué es?
Una Renta es la contratación temporal de un [[Recurso]] externo para cubrir
una necesidad que el inventario propio de EBS no puede satisfacer.

No es un fracaso operativo — es un mecanismo previsto en el flujo.
Cuando un [[Requerimiento]] no puede resolverse con inventario propio,
la Renta es la respuesta estándar.

## ¿Cuándo ocurre?
1. Se detecta un [[Requerimiento]] de un [[Recurso]]
2. El [[Inventario]] propio no tiene disponibilidad suficiente
3. No hay opción de reasignación desde otro [[Evento]]
4. Se autoriza contratar el recurso a un [[Proveedor Externo]]

## Ejemplos
- EBS no tiene suficientes m² de LD Roll para un festival → renta a proveedor X
- Todos los Sprinters están comprometidos ese fin de semana → renta camioneta externa
- Se necesita un Supervisor EPS adicional → subcontratación a freelance
- Faltan piezas de Scaffold → renta a otra empresa STEEL

## Atributos
- `id`
- `requerimiento` → [[Requerimiento]] (origen)
- `evento` → [[Evento]]
- `recurso_tipo` — descripción del recurso rentado
- `proveedor` → [[Proveedor Externo]]
- `cantidad`
- `unidad` — piezas, m², días, etc.
- `fecha_inicio`
- `fecha_fin`
- `costo_total`
- `estado` — ver Estados
- `aprobado_por` → [[Roles]]
- `odc_referencia` → ODC generada en Odoo
- `notas`

## Estados posibles
- **Solicitada** — se identificó la necesidad, buscando proveedor
- **Cotizada** — proveedor respondió con precio
- **Aprobada** — costo autorizado, esperando confirmación
- **Confirmada** — proveedor confirmó disponibilidad y fecha
- **Activa** — recurso rentado está en operación
- **Cerrada** — recurso devuelto, renta finalizada
- **Cancelada** — se anuló antes de activarse

## Ciclo de vida
Solicitada → Cotizada → Aprobada → Confirmada → Activa → Cerrada

## Impacto en costos
Una Renta genera costo variable en el [[Evento]].
La ODC correspondiente se genera en **Odoo** —
este sistema solo registra la referencia y el impacto operativo.

## Reglas críticas
- Una Renta no reemplaza al [[Recurso]] propio en el [[Inventario]]
- El recurso rentado NO se registra como inventario de EBS
- Si la Renta se cancela, el [[Requerimiento]] vuelve a Sin resolver
- Toda Renta aprobada requiere autorización de [[Gerente Operaciones]]
- El costo de Renta debe reflejarse en el presupuesto del [[Evento]] antes de aprobarse

## Relaciones
- Nace de un [[Requerimiento]] sin resolver con inventario propio
- Puede nacer de la resolución de un [[Conflicto]]
- Su proveedor es un [[Proveedor Externo]]
- Su costo impacta el [[Evento]] y genera una ODC en Odoo
- Al activarse, el recurso rentado se comporta operativamente como un [[Recurso]] asignado

## El recurso rentado en el sistema
Cuando la Renta pasa a estado **Confirmada**, el sistema crea un [[Recurso Temporal]]
vinculado a esta Renta. Se trata exactamente igual que un recurso propio:
aparece en el [[Despiece]], tiene [[Asignacion]], genera [[Movimiento]]s.

Al cerrar la Renta, el Recurso Temporal se desactiva y sale del [[Inventario]].
El proveedor cobra faltantes si algo no se devuelve en condiciones.
