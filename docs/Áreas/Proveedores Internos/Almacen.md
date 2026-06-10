## ¿Qué es?
El Almacén es el proveedor interno responsable de la custodia,
preparación y recepción de todos los [[Recurso]]s físicos de EBS.

## Responsabilidades
- Custodia de todos los recursos en el almacén
- Preparación de despachos según [[Despiece]] y [[ODS]]
- Ejecución de [[Salida de Almacen]] y [[Descarga en Almacen]]
- Ejecución de [[Entrada de Almacen]]
- Registro del estado de cada [[Recurso]] al entrar y salir
- Detección de daños y recursos fuera de servicio

## Capacidad limitada
El Almacén tiene:
- Espacio físico limitado (no puede almacenar recursos infinitos)
- Personal limitado (no puede despachar infinitos eventos simultáneos)
- Horario de operación (ventanas de carga/descarga)

## Relaciones
- Es el primer y último eslabón de cada [[Evento]]
- Coordina con [[Logistica de Carga]] para tiempos de vehículos
- Actualiza [[Inventario]] tras cada movimiento
- Reporta daños al [[Project Manager]] y [[Gerente Operaciones]]
