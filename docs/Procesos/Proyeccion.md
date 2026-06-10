## ¿Qué es?
La Proyección es el proceso mediante el cual el área de Operaciones
calcula el costo operativo real de ejecutar un [[Evento]].

Es 100% responsabilidad de Operaciones. Comercial no la genera — la recibe
y ajusta su cotización con base en ella.

## Quién la hace
El [[Gerente Operaciones]] o el [[Project Manager]] asignado, con apoyo del
[[Jefe de Steel]] y [[Supervisor EPS]] según el tipo de evento.

## Entradas
- [[Brief]] del evento (servicios requeridos, fechas, venue)
- [[Tabulador]] de puestos vigente
- [[Tipo de Dia]]s del evento (Previo, Montaje, Show, Guardia, Desmontaje)
- Histórico de eventos similares (referencia)

## Lo que calcula la Proyección

### 1. PXE (Destajos)
Por cada puesto requerido:
```
Pago operativo = BASE_FIJA + Σ (días × puntos(tipo_dia) × VALOR_X_PUNTO)
Viáticos       = días_presentes × VIÁTICO_DÍA
Total puesto   = (pago_op + viáticos) × cantidad_personas
```
Genera los [[Turno]]s planeados para cada [[Persona]] en el evento.

### 2. Logística de Carga
Número de camiones, tipo de unidad, rutas, estadías.
Presupuesto por servicio (STEEL, EPS, etc.).

### 3. Logística de Personal
[[Vuelos]], [[Hospedaje]], [[Viaticos]], traslados locales.
Por puesto, cantidad de personas, días.

### 4. Extras / Rentas
[[Renta]]s de equipo que no está en inventario propio.
Maquinaria, andamio, personal especializado externo.

## Relación con la Cotización de Comercial
Actualmente el flujo es:
```
Comercial hace su proyección (estimada)  ←→  Operaciones hace Proyección real
         ↓                                           ↓
Comparte presupuesto con Ops ──→ Ops compara y solicita ajuste si no cuadra
```

El sistema debe evolucionar a:
```
Brief entra → Operaciones genera Proyección con tabulador real
                      ↓
          Proyección es la fuente de verdad
                      ↓
   Comercial usa esos datos para armar su cotización al cliente
```

## Salidas
- Presupuesto operativo por rubro (PXE, Logística Carga, Logística Personal, Extras)
- [[Turno]]s planeados por persona
- Insumo para sección de presupuesto de la [[ODS]]
- Dato base para la Cotización de Comercial

## Regla de excepción — internacional
Para personal enviado fuera de México, el pago no usa el [[Tabulador]]:
es un monto cerrado acordado directamente con cada persona.
Se registra como monto_fijo en la Proyección.

## Relaciones
- Consume el [[Brief]] como entrada principal
- Usa el [[Tabulador]] y [[Tipo de Dia]] para calcular PXE
- Genera [[Turno]]s planeados
- Sus totales alimentan el [[Presupuesto]] del evento y la [[ODS]]
