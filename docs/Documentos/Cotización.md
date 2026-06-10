## ¿Qué es?
La Cotización es la propuesta económica que EBS presenta al [[Cliente]]
para la prestación de servicios en un [[Proyecto]].

## Dónde vive
En **Odoo** — es un documento comercial, no operativo.

## Quién la crea
El área [[Comercial]] ([[Gerente Comercial]] o [[Asistente Comercial]]).

## De dónde salen sus números
Idealmente, la Cotización se basa en la [[Procesos/Proyeccion|Proyección]]
de costos operativos generada por [[Operaciones]] a partir del [[Brief]].

Operaciones calcula el costo real usando el [[Tabulador]].
Comercial agrega su margen y condiciones comerciales → precio al cliente.

> Hoy en EBS esto no siempre ocurre así: Comercial a veces estima por su cuenta
> y luego Operaciones compara. El sistema debe cerrar ese gap.

## Qué contiene
- Servicios ofrecidos (STEEL, EPS, combinación)
- Precio por servicio
- Condiciones de pago
- Vigencia de la propuesta
- Exclusiones y notas

## Ciclo
```
Brief → Proyección de Ops → Cotización en Odoo → Cliente aprueba → Contrato
```

## Relaciones
- Basada en el [[Brief]] y la [[Procesos/Proyeccion|Proyección]] operativa
- Su aprobación por el cliente genera el [[Contrato]]
- El [[Contrato]] firmado activa la [[Planeacion Operativa]] definitiva
