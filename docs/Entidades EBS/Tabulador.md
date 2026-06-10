## ¿Qué es?
Tabla de tarifas oficiales que define cuánto cobra cada puesto operativo
en EBS Group por su participación en un [[Evento]].

Es la fuente de verdad para calcular el costo de PXE (destajos) y viáticos
en la [[Procesos/Proyeccion|Proyección]] de cualquier evento.

## Estructura del Tabulador

| Puesto | VIÁTICO_DÍA | BASE_FIJA | VALOR_X_PUNTO |
|---|---|---|---|
| Dirección | $1,200 | $0 | $0 |
| Gerencia | $900 | $0 | $0 |
| Show Coordinator | $700 | $0 | $0 |
| Project Manager Senior | $600 | $2,400 | $800 |
| Project Manager Jr | $600 | $2,400 | $800 |
| Project Manager Inhouse | $0 | $1,500 | $200 |
| Jefe de Steel | $600 | $2,400 | $800 |
| Supervisor EPS | $500 | $1,800 | $600 |
| Auxiliar EPS | $500 | $1,800 | $600 |
| Ayudante | $500 | $1,500 | $500 |
| Armador | $500 | $2,040 | $600 |
| Jefe de Cuadrilla | $500 | $5,000 | $700 |
| Armador Eventual | $500 | $8,000 | $0 |
| Chofer Armador | $500 | $4,040 | $600 |

> El Armador Eventual tiene VALOR_X_PUNTO = 0 — su pago es la BASE_FIJA sin importar cuántos días o qué tipo de días trabaje.

## Fórmula de pago por persona
```
Pago operativo = BASE_FIJA
               + Σ (días_trabajados[tipo] × puntos[tipo] × VALOR_X_PUNTO)

Viáticos       = Σ (días_presentes × VIÁTICO_DÍA)

Pago total     = Pago operativo + Viáticos
```

## Tipos de día y sus puntos
Ver [[Tipo de Dia]].

## Alcance del Tabulador

### México
Un solo tabulador aplica a todos los eventos en territorio nacional.
Lo controla y actualiza el [[Gerente Operaciones]].

### Sucursales internacionales
Cada sucursal opera con su propio tabulador en su moneda local.
Mismo principio, tarifas distintas.

### Personal enviado a Sudamérica
Cuando EBS manda armadores a giras internacionales, el pago
es un **monto cerrado negociado individualmente** con cada persona.
No se aplica el tabulador estándar — es un acuerdo directo.
Se registra en la [[Procesos/Proyeccion|Proyección]] como monto fijo por persona.

## Quién lo puede modificar
Solo el [[Gerente Operaciones]]. Es una configuración del sistema.

## Relaciones
- Usado por [[Procesos/Proyeccion|Proyección]] para calcular costos de PXE
- Referenciado en [[Turno]] para calcular el pago por día trabajado
- Sus totales alimentan la sección PXE de la [[ODS]]
