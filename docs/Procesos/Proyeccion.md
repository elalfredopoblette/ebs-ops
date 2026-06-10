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

## Estructura de la Proyección

La Proyección tiene 6 secciones que corresponden directamente a los
[[Proveedor Interno]]s y sus [[Subcuenta]]s:

### 1. Datos del Evento
EVENT_ID, artista, ciudad, [[Venue]], cliente, contacto.
Fechas: Llegada Staff, Load In, ShowDay, Salida Staff.
Catálogo de productos cotizados: STEEL (Roof, Scaffold, Torres) y EPS
con dimensiones, pesos y tipo de unidad de transporte requerida.

### 2. CREWLIST — PXE (Operaciones)
Una fila por [[Persona]] recurso. Columnas día a día con [[Tipo de Dia]].

**Para personal nómina:**
```
TOTAL_PXE = (TOTAL_PUNTOS × MULTIPLICADOR) + BASE_FIJA
```
- MULTIPLICADOR = VALOR_X_PUNTO del puesto en [[Tabulador]]
- BASE_FIJA = monto fijo por evento del [[Tabulador]]

**Para Armador Eventual:**
```
TOTAL_PXE = BASE_FIJA (tarifa flat negociada por evento)
MULTIPLICADOR = $0 — los eventuales NO cobran por puntos
```

**Columna DISPERSIÓN:** fecha individual en que cada persona recibe su pago.

Viáticos se calculan separado: `TOTAL_VIÁTICOS = VIÁTICO_DÍA × días_presentes`

### 3. Sprinters — Traslado de Personal (Logística Personal)
Cálculo de ruta punto a punto: km totales, rendimiento km/L, precio diesel,
casetas, mantenimiento (5%), imprevistos (5%).
Separado en: traslado carretera (origen→destino→origen) + movimientos locales.

### 4. Logística de Carga (Logística Transportes)
Por tipo de recurso (Roof, Scaffold, Torres, EPS, Extras):
- Tipo de unidad requerida (Drop Deck 53", Dry Van 40", Plataforma Trailer)
- Número de unidades
- Fechas Load In y Load Out
- **Estadías**: días que la unidad permanece en venue × costo diario de estadía
- Subtotales por categoría y total general

### 5. Renta Scaffold — Despiece (Compras)
Catálogo completo de piezas Layher con SKU, peso, cantidad requerida y
costo unitario del proveedor. Base para calcular la subrenta de scaffold.

### 6. Resumen — Proyección de Pagos
Consolida todo el presupuesto por [[Proveedor Interno]] y [[Subcuenta]]:

| Proveedor Interno | Subcuenta | Estructura de pago |
|---|---|---|
| Logística Transportes | Transportes de Carga | Anticipo 60% + Finiquito 40% con fechas |
| Operaciones | PXE | Pago único, semana del show |
| Logística Personal | Viáticos | Pago único anticipado |
| Logística Personal | Hospedaje | Pago único anticipado |
| Logística Personal | Traslado de Personal | Por tipo de traslado |
| Compras | Extras | Variable |

**TOTAL PROYECCIÓN** = suma de todas las subcuentas = costo operativo real antes del margen comercial.

Cada pago incluye `fecha_pago` y `semana_pago` (número de semana ISO)
para visualizar el flujo de caja del evento por semana.

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
