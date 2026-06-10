## ¿Qué es?
El Cierre de Evento es el proceso formal mediante el cual el [[Project Manager]]
entrega el evento a [[Gerente Operaciones]] con toda la información de
ejecución real, costos y eficiencia.

No termina con el [[Load Out]] físico — termina cuando todos los proveedores
internos están pagados y cerrados, y el Gerente recibe el reporte de eficiencia.

## Por qué es necesario formalizarlo
Hoy no existe un checklist formal. El sistema debe estandarizarlo para:
- Garantizar que ningún pago quede pendiente
- Medir la eficiencia real vs proyectada
- Identificar aprendizajes para futuros eventos similares
- Liberar oficialmente los [[Recurso]]s del [[Evento]]

## Checklist de cierre (entregables del PM)

### 1. Cierre operativo
- [ ] [[Load Out]] completado y confirmado por Almacén
- [ ] [[Entrada de Almacen]] registrada con estado de cada recurso
- [ ] [[Recurso]]s dañados reportados e iniciado [[Mantenimiento de Recurso]]
- [ ] [[Recurso Temporal]]es devueltos al proveedor sin faltantes

### 2. Cierre de personal
- [ ] Todos los [[Turno]]s del evento marcados como Ejecutados o Cancelados
- [ ] Lista de asistencia final entregada por [[Jefe de Steel]] y [[Supervisor EPS]]
- [ ] Turnos de Guardia revisados — conversiones a Montaje autorizadas si aplica
- [ ] Aprobación de PM enviada a [[Pagos Por Evento (destajos)]]

### 3. Cierre de proveedores internos
- [ ] [[Logistica de Carga]] — viajes cerrados y pagados
- [ ] [[Logistica de Personal]] — vuelos, hospedaje y viáticos liquidados
- [ ] [[Compras y Rentas]] — rentas cerradas, ODC pagadas
- [ ] [[Pagos Por Evento (destajos)]] — destajos procesados y pagados

### 4. Reporte de eficiencia (entregable al Gerente de Operaciones)
El PM entrega a [[Gerente Operaciones]] un documento con:

**Budget vs Actual por rubro:**
| Rubro | Presupuestado | Real | Varianza | % Eficiencia |
|---|---|---|---|---|
| Logística Carga | | | | |
| PXE (Destajos) | | | | |
| Logística Personal | | | | |
| Extras / Rentas | | | | |
| **Total** | | | | |

**Day by Day:**
Reporte cronológico de lo que ocurrió cada día operativo:
- Avance de montaje
- Incidencias registradas
- Personal presente vs planeado
- Decisiones tomadas

**Eficiencia de recursos:**
- Recursos que llegaron dañados
- Recursos que no se usaron (sobra en Despiece)
- Recursos que faltaron (Rentas de emergencia)

**Eficiencia de tiempo:**
- Días planeados vs días reales por fase
- Retrasos y sus causas

## Quién aprueba el cierre
El [[Gerente Operaciones]] revisa los entregables y aprueba el cierre formal.
Solo entonces el [[Evento]] pasa a estado **Cerrado** en el sistema.

## Estado del Evento
```
Load Out completado → PM prepara entregables → Gerente aprueba → Evento: Cerrado
```
El Evento no debe cerrarse automáticamente al terminar el Load Out —
requiere aprobación explícita del Gerente con los entregables en mano.

## Relaciones
- Depende de que el [[Load Out]] esté completo
- Consume los [[Turno]]s ejecutados para el reporte de PXE
- Consume los [[Costos]] reales vs [[Presupuesto]] para la eficiencia
- Libera todas las [[Asignacion]]es del [[Evento]]
- Su aprobación actualiza el [[Inventario]] definitivamente
