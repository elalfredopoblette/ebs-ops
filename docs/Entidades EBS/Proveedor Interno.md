## ¿Qué es?
Área interna de EBS que recibe requerimientos a través de la [[ODS]] y ejecuta
su parte del presupuesto del [[Evento]]. Cada proveedor interno gestiona su propio
ciclo: recibe la ODS → genera [[SDC]] a externos → recibe cotización → genera [[ODC]]
a Tesorería → Tesorería ejecuta el pago.

> No confundir con [[Proveedor Externo]] — los proveedores internos son
> departamentos de EBS, no empresas terceras.

## Los 4 Proveedores Internos

| Proveedor Interno | Subcuentas | Qué gestiona |
|---|---|---|
| **Logística Transportes** | Transportes de Carga | Renta de camiones (Drop Deck, Dry Van, Plataformas). EBS no tiene unidades propias — todo se renta. Cobra estadías por días en venue. |
| **Operaciones** | PXE | Pago a cada [[Persona]] recurso (destajos). El [[Gerente Operaciones]] pasa esta solicitud directo a Tesorería. |
| **Logística Personal** | Viáticos, Hospedaje, Traslado de Personal | Traslados (Sprinter, avión, autobús), [[Hospedaje]] y [[Viaticos]] del crew. También gestiona gastos de las Sprinters. |
| **Compras** | Extras | Subrenta de Scaffold, motores, pipas de agua, bidones, personal eventual externo (stagehands, armadores), y otros. |

## Subcuentas

Cada línea de pago se identifica con la estructura:
```
CENTRO_DE_COSTO → PROVEEDOR_INTERNO → SUBCUENTA → ÁREA/SERVICIO → DETALLE
```
Ver [[Subcuenta]] para el detalle de cada una.

## Estructura de pago por proveedor

| Proveedor Interno | Estructura |
|---|---|
| Logística Transportes | Anticipo 60% antes del evento + Finiquito 40% post |
| Operaciones (PXE) | Pago único, semana del show |
| Logística Personal | Pagos anticipados (semana previa al evento) |
| Compras | Variable según acuerdo |

## Ciclo de compra (Proveedores Internos distintos de Operaciones)
```
ODS → Área interna identifica necesidad
    → SDC al Proveedor Externo
      → Cotización recibida
        → ODC generada en Odoo → Tesorería
          → Tesorería ejecuta pago
```

## Excepción: Operaciones
El [[Gerente Operaciones]] pasa la solicitud de PXE directo a Tesorería.
No genera SDC ni ODC — el cálculo viene de los [[Turno]]s aprobados.

## Relaciones
- Reciben instrucciones vía [[ODS]] con presupuesto por sección
- Sus costos son calculados en la [[Procesos/Proyeccion|Proyección]] antes del evento
- Cada costo tiene una [[Subcuenta]] para clasificación contable
- Sus pagos a externos generan [[ODC]] en Odoo
