## ¿Qué es?
El Despiece es el documento técnico que traduce un [[Plano]] en una lista
de [[Recurso]]s específicos, con cantidades y unidades, necesarios para
montar una configuración determinada en un [[Evento]].

Es el puente entre Diseño y Operaciones.
Sin Despiece, no pueden generarse [[Requerimiento]]s de recursos.

## Ejemplo
Plano: Roof System 12x8 con dos Delay Towers en Campo Marte
Despiece resultante:
- 48 piezas Beam 290
- 12 piezas Beam 100
- 8 Corner Block
- 24 Spigot
- 2 Delay Tower completas (kit)
- 16 Base Plate

## ¿Quién lo crea?
Área de **Diseño** — a partir del [[Brief]] y del [[Plano]] del venue.

## ¿Quién lo usa?
- **Operaciones** — para generar [[Requerimiento]]s y hacer el [[Cross Check de Disponibilidad]]
- **Almacén** — para preparar la [[Salida de Almacen]]
- **Project Manager** — para validar que lo que sale coincide con el Despiece

## Atributos
- `id`
- `evento` → [[Evento]]
- `proyecto` → [[Proyecto]]
- `plano` → [[Plano]]
- `version` — siempre hay una versión activa; los cambios generan nueva versión
- `creado_por` → Diseño
- `fecha_creacion`
- `estado` — Borrador / En revisión / Aprobado
- `items[]`:
  - `recurso_tipo`
  - `cantidad`
  - `unidad` — piezas, m², ml, kits
  - `categoria` — STEEL / EPS / Herramienta

## Flujo de uso
1. Diseño crea el Despiece a partir del [[Plano]]
2. Operaciones recibe el Despiece aprobado
3. Por cada ítem se genera un [[Requerimiento]]
4. Los Requerimientos van al [[Cross Check de Disponibilidad]]
5. Lo que hay en inventario → [[Asignacion]]
6. Lo que no hay → [[Renta]]

## Reglas críticas
- Un [[Evento]] no puede avanzar a planeación sin un Despiece aprobado
- Si el Despiece cambia, los [[Requerimiento]]s deben regenerarse
- El Despiece define "qué se necesita" — el [[Inventario]] define "qué hay"
- La diferencia entre ambos es el gap que dispara Rentas

## Relaciones
- Nace de un [[Plano]]
- Pertenece a un [[Evento]]
- Sus ítems generan [[Requerimiento]]s uno a uno
- Es la entrada del [[Cross Check de Disponibilidad]]
- Su ejecución física se valida en la [[Salida de Almacen]]

## Pregunta abierta
> ¿El Despiece vive en este sistema o en AutoCAD / herramienta de diseño externa?
> ¿Este sistema lo gestiona o solo lo consume?
