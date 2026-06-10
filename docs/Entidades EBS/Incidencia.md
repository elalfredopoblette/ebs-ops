## ¿Qué es?
Una Incidencia es cualquier evento no planeado que ocurre durante
la ejecución de un [[Evento]] y que requiere decisión o seguimiento.

Hoy en EBS se reportan por WhatsApp o en el grupo de Teams del proyecto
(nombrado con el EVENT ID). El sistema debe darles un lugar formal.

## Tipos de incidencia

| Tipo | Descripción | ¿Puede escalar? |
|---|---|---|
| Retraso de Personal | Personal no llega a tiempo a su turno | Sí → afecta [[Turno]]s |
| Faltante de Material | Un recurso del [[Despiece]] no está en campo | Sí → activa [[Requerimiento]] urgente |
| Daño a Recurso | Un [[Recurso]] se daña durante la operación | Sí → activa [[Mantenimiento de Recurso]] |
| Modificación en Sitio | El cliente solicita cambio de alcance en campo | Sí → puede requerir nueva versión de [[ODS]] |
| Cambio de Turno | Un día de Guardia amerita ser Montaje | Sí → decisión del [[Gerente Operaciones]] |
| Acceso restringido | El [[Venue]] limita el acceso en momento crítico | Depende |
| Otro | Cualquier evento no categorizado | Depende |

## Modificación en Sitio — caso especial
Es el tipo más delicado porque toca presupuesto y relación con cliente.

| Magnitud | Impacto | Acción |
|---|---|---|
| Menor | Sin cambio de costo ni días | Se absorbe, sin actualizar documentos |
| Mayor | Agrega días de montaje o material | Requiere nueva versión de [[ODS]], posible cargo extra al cliente |

> Existe una tensión operativa: algunos días que podrían upgradearse a Montaje
> se mantienen en Guardia para eficientar costos. El "deber ser" es cobrar
> al cliente el trabajo real y registrarlo correctamente.

## Atributos
- `tipo` — de la tabla anterior
- `evento` → [[Evento]]
- `fase` — [[Load In]] / [[ShowDay]] / [[Load Out]]
- `fecha_hora` — cuándo ocurrió
- `reportado_por` → [[Persona]]
- `descripcion` — qué pasó
- `impacto` — Menor / Mayor
- `estado` — Reportada / En atención / Resuelta / Escalada
- `resolucion` — qué se decidió
- `genera_documento` — si requiere actualizar [[ODS]], [[Despiece]] u otro

## Flujo general
```
Incidencia ocurre en campo
      ↓
Jefe de Steel / Supervisor EPS la reporta (Teams/sistema)
      ↓
PM evalúa impacto
      ↓
Menor → resuelto en campo, registrado
Mayor → PM escala a Gerente Operaciones
      ↓
Si hay cambio de costo → nueva versión de ODS + coordinación con Comercial
```

## Relaciones
- Siempre asociada a un [[Evento]] y una fase
- Reportada por [[Jefe de Steel]] o [[Supervisor EPS]]
- Gestionada por el [[Project Manager]]
- Puede generar: [[Requerimiento]] urgente, [[Mantenimiento de Recurso]], cambio de [[Turno]], nueva versión de [[ODS]]
