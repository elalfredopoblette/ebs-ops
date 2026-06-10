## ¿Qué es?
Proceso mediante el cual un [[Recurso]] dañado o fuera de condiciones
es evaluado, reparado y regresado a estado Disponible —
o dado de baja definitivamente.

## Cuándo se activa
- [[Recurso]] llega dañado en la [[Entrada de Almacen]] post [[Load Out]]
- [[Incidencia]] de tipo "Daño a Recurso" durante la operación
- Revisión periódica en almacén detecta deterioro

## Cadena de autorización

```
Jefe de Steel (o Supervisor EPS) reporta el daño en campo
      ↓
Project Manager notifica a Almacén formalmente
      ↓
Almacén evalúa el daño y estima costo de reparación
      ↓
Gerente Operaciones autoriza la acción (mantenimiento o baja)
      ↓
Si el monto es alto → escala a Dirección de Operaciones para confirmación final
```

## Tipos de reparación

| Tipo | Cuándo | Quién |
|---|---|---|
| Interno | El personal de EBS tiene herramientas y conocimiento | Personal de Almacén / Steel |
| Externo | Requiere herramientas especializadas o conocimiento específico | [[Proveedor Externo]] de mantenimiento |

## Estados del Recurso durante el proceso
```
Disponible → [daño detectado] → En mantenimiento → Disponible (reparado)
                                                  → Fuera de servicio (irreparable)
```

Un [[Recurso]] "En mantenimiento" NO cuenta como disponible en el [[Inventario]]
y no puede ser asignado a ningún [[Evento]] mientras dura el proceso.

## Decisión: reparar vs dar de baja
| Criterio | Reparar | Dar de baja |
|---|---|---|
| Costo de reparación | < valor de reposición | ≥ valor de reposición |
| Disponibilidad de repuestos | Hay repuestos | No hay repuestos |
| Tiempo de reparación | Razonable vs demanda futura | Demasiado largo |
| Condición estructural | Compromiso menor | Compromiso estructural grave |

La decisión final siempre es del [[Gerente Operaciones]] (o [[Dirección]] si el monto es alto).

## Impacto en inventario
- Durante mantenimiento: `cantidad_en_mantenimiento` ↑, `cantidad_disponible` ↓
- Al regresar a Disponible: se revierte
- Al darse de baja: `cantidad_total` ↓ permanentemente

## Si el daño ocurrió en un Recurso Temporal (rentado)
El [[Proveedor Externo]] cobrará el daño o faltante.
No aplica proceso de mantenimiento interno — se coordina devolución
y se registra el cargo en los [[Costos]] del [[Evento]].

## Relaciones
- Activado por [[Incidencia]] de daño o por [[Entrada de Almacen]] con anomalía
- Gestionado por [[Almacen]] con autorización de [[Gerente Operaciones]]
- Actualiza el [[Inventario]] y el estado del [[Recurso]]
- Si el recurso es dado de baja permanente → puede disparar una [[Compra]] de reposición
