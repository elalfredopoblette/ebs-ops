## ¿Qué es?
Proceso mediante el cual los [[Recurso]]s regresan físicamente al almacén
después del [[Load Out]] de un [[Evento]].

## Cuándo ocurre
Al terminar el [[Load Out]], cuando los vehículos llegan al almacén.

## Proceso
1. Vehículos llegan al almacén con material del [[Evento]]
2. Personal de almacén descarga y verifica contra [[Despiece]] original
3. Se registra cada recurso: qué llegó, en qué estado
4. **Si hay daños** → recurso pasa a estado En mantenimiento o Fuera de servicio
5. **Si hay faltantes** → se registra como incidencia y se escala al PM
6. Los [[Recurso]]s en buen estado pasan a estado: En tránsito → **Disponible**
7. Se generan [[Movimiento]]s de entrada
8. Se cierra el ciclo del [[Evento]] en [[Inventario]]

## Por qué es crítico
La Entrada de Almacén correcta garantiza que:
- Los [[Recurso]]s aparezcan disponibles para futuros [[Evento]]s
- El [[Inventario]] refleje el estado real
- Los daños se detecten y gestionen antes del próximo despacho

## Relaciones
- Cierra el [[Load Out]]
- Genera [[Movimiento]]s de entrada
- Actualiza [[Inventario]] y estados de [[Recurso]]s
- Libera definitivamente las [[Asignacion]]es del [[Evento]]
