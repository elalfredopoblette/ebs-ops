## ¿Qué es?
Proceso mediante el cual los [[Recurso]]s salen físicamente del almacén
hacia el [[Venue]] para el [[Load In]] de un [[Evento]].

## Cuándo ocurre
Antes del primer día de [[Load In]].
El PM define la fecha y hora de salida según el calendario del [[Evento]].

## Entradas requeridas
- [[ODS]] generada y firmada
- [[Despiece]] del Evento (lista exacta de qué sale)
- [[Asignacion]]es confirmadas para los recursos a despachar
- Vehículos disponibles ([[Logistica de Carga]])

## Proceso
1. [[Almacen]] recibe la [[ODS]] o instrucción de despacho
2. Personal de almacén prepara y verifica el material contra [[Despiece]]
3. Se registra la salida: qué sale, cuánto, en qué estado
4. El material se carga a los [[Vehículo]]s
5. Los [[Recurso]]s cambian de estado: Disponible → **En tránsito**
6. Se genera documento de [[Movimiento]] de salida

## Regla crítica
No puede salir ningún recurso que no tenga [[Asignacion]] Confirmada.
Si hay faltantes al verificar → se genera [[Requerimiento]] urgente.

## Relaciones
- Depende del [[Despiece]] y las [[Asignacion]]es
- Genera [[Movimiento]]s de salida
- Actualiza estados en [[Inventario]]
- Habilita el [[Load In]]
