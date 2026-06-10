## ¿Qué es?
La Orden de Servicio (ODS) es el documento que comunica a los proveedores
internos de EBS las decisiones operativas ya tomadas para un [[Evento]].

Tiene dos funciones simultáneas:
1. **Comunicar** — qué servicios se ejecutan, con qué recursos, en qué fechas
2. **Controlar** — cuánto hay asignado por rubro de costo y cuándo se paga

## Quién la genera
El [[Project Manager]] de Operaciones. Es un documento 100% de [[Operaciones]].

## Cuándo se genera
Solo cuando el [[Evento]] está en estado **Listo** — es decir, cuando:
- El [[Cross Check de Disponibilidad]] está completo
- Todas las [[Asignacion]]es están confirmadas
- La [[Procesos/Proyeccion|Proyección]] de costos está aprobada

No se genera antes. Una ODS con recursos sin confirmar es un documento incorrecto.

## Estructura de la ODS

### Encabezado
- ID del evento, artista/evento, ciudad, venue, cliente, contacto
- Fechas: llegada, Load In, ShowDay, Load Out, salida
- Días de operación total

### Servicios contratados
Lista de servicios STEEL y EPS comprometidos con el cliente.

### Secciones de presupuesto por rubro
Cada sección tiene: lista de ítems, monto asignado, fecha de pago.

| Sección | Qué cubre |
|---|---|
| Logística de Carga | Camiones, unidades, rutas, estadías |
| PXE (Destajos) | Personal operativo por puesto, calculado con [[Tabulador]] |
| Viáticos | Días × monto/día por puesto |
| Hospedaje | Habitaciones × noches × monto/noche |
| Sprinter / Traslados | Transporte de personal |
| Extras | [[Renta]]s externas, maquinaria, personal especializado |

### Resumen de presupuesto
Total por sección y total general del evento.

### Nota al pie
"El total de los montos es sin IVA. Esta ODS puede cambiar según
actualizaciones internas o de cliente. En caso de superar el monto
asignado por rubro, validar con Operaciones."

## Quién la recibe
Los [[Proveedor Interno]]s relevantes: [[Almacen]], [[Logistica de Carga]],
[[Logistica de Personal]], [[Compras y Rentas]], [[Pagos Por Evento (destajos)]].

## Diferencia con la Cotización
| ODS | Cotización |
|---|---|
| Documento interno de Operaciones | Documento comercial para el cliente |
| Muestra costo operativo real | Muestra precio de venta con margen |
| Generada por el PM | Generada por Comercial en Odoo |
| Fuente: [[Tabulador]] real | Fuente: ODS + margen comercial |

## Relaciones
- Solo se genera cuando el [[Evento]] está en estado Listo
- Sus presupuestos derivan de la [[Procesos/Proyeccion|Proyección]]
- Distribuida a todos los [[Proveedor Interno]]s del evento
- Sus montos son los topes de gasto por rubro — excederlos requiere aprobación de [[Gerente Operaciones]]
