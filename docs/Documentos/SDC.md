## ¿Qué es?
La Solicitud de Cotización (SDC) es el documento con el que EBS pide
a un [[Proveedor Externo]] que indique su precio y disponibilidad
para un bien o servicio específico.

Es el primer paso del proceso de [[Renta]] o [[Compra]] cuando se necesita
un recurso externo.

## Cuándo se genera
Cuando el [[Cross Check de Disponibilidad]] detecta un [[Requerimiento]]
que no puede resolverse con inventario propio y se decide cotizar con proveedores externos.

El área de [[Compras y Rentas]] genera la SDC y la envía a uno o más
[[Proveedor Externo]]s para obtener opciones.

## Qué contiene
- Descripción del recurso o servicio requerido
- Cantidad y especificaciones técnicas
- Fechas de uso (inicio y fin)
- Venue o ciudad de entrega
- Plazo para responder
- Condiciones especiales

## Flujo
```
Requerimiento sin resolver
        ↓
SDC enviada a Proveedor(es) Externo(s)
        ↓
Proveedor responde con precio y disponibilidad
        ↓
[[Renta]] pasa a estado Cotizada
        ↓
Gerente Operaciones aprueba → ODC
```

## Relaciones
- Generada por [[Compras y Rentas]]
- Enviada a [[Proveedor Externo]]
- Su respuesta lleva la [[Renta]] de Solicitada → Cotizada
- Cuando se aprueba, origina una [[ODC]]
