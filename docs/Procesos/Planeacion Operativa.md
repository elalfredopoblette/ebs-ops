## ¿Qué es?
La Planeación Operativa es el proceso mediante el cual el [[Project Manager]]
traduce el [[Brief]] en un plan ejecutable: qué personal, qué recursos,
qué logística, cuánto cuesta.

No es una entidad ni un documento — es una **fase del [[Evento]]**.
El Evento está "En planeación" mientras este proceso ocurre.

## Dos pasadas

### Pasada 1 — Preliminar (pre-contrato)
**Cuándo:** Apenas existe el [[Brief]], antes de que el [[Contrato]] se firme.

**Quién:** [[Project Manager]] o [[Gerente Operaciones]], con apoyo de
[[Jefe de Steel]] y [[Supervisor EPS]] según el tipo de evento.

**Qué hace el PM:**
- Lee el Brief y con base en su experiencia estima:
  - Cuántas personas por puesto se necesitan
  - Cuántos días por tipo ([[Tipo de Dia]]: Previo, Montaje, Show, Desmontaje)
  - Qué logística de personal requiere (vuelos, hospedaje, viáticos)
  - Qué equipos adicionales podrían necesitarse
- El sistema calcula la [[Procesos/Proyeccion|Proyección]] de costos usando el [[Tabulador]]

**Resultado:**
Proyección de costos operativos que Comercial usa como base real
para armar su cotización al cliente. Sin esta pasada, Comercial cotiza a ciegas.

### Pasada 2 — Definitiva (post-contrato)
**Cuándo:** El [[Contrato]] está firmado y el [[Despiece]] aprobado llega de [[Diseño]].

**Qué hace el PM:**
1. Recibe el [[Despiece]] aprobado
2. Ejecuta el [[Cross Check de Disponibilidad]] recurso por recurso
3. Confirma [[Asignacion]]es para inventario disponible
4. Inicia [[Renta]]s para lo que no hay en inventario
5. Resuelve [[Conflicto]]s detectados
6. Confirma o ajusta [[Turno]]s del personal
7. Coordina [[Logistica de Personal]]: [[Vuelos]], [[Hospedaje]], [[Viaticos]]
8. Coordina [[Logistica de Carga]]: rutas, [[Vehiculo]]s, horarios

**Resultado:**
[[Evento]] pasa a estado **Listo** → se genera la [[ODS]]

## Por qué dos pasadas importan
Hoy en EBS, Operaciones solo hace la pasada 2.
Comercial hace su propia estimación en paralelo (sin tabulador real)
y luego Operaciones la compara y solicita ajuste si no cuadra.

El sistema debe habilitar la pasada 1 para que Comercial deje de
estimar a ciegas y use los números reales de Operaciones desde el inicio.

## Entradas
| Pasada | Entradas |
|---|---|
| Preliminar | [[Brief]] + experiencia del PM + [[Tabulador]] |
| Definitiva | [[Despiece]] aprobado + [[Inventario]] + [[Asignacion]]es existentes |

## Salidas
| Pasada | Salidas |
|---|---|
| Preliminar | [[Procesos/Proyeccion\|Proyección]] de costos para Comercial |
| Definitiva | [[Asignacion]]es confirmadas, [[Turno]]s, [[Evento]] = Listo, [[ODS]] |

## Quién ejecuta
[[Project Manager]] como responsable principal.
[[Gerente Operaciones]] toma decisiones de [[Renta]] y resolución de [[Conflicto]]s.
[[Jefe de Steel]] y [[Supervisor EPS]] validan cantidades de personal y material.

## Relaciones
- Consume el [[Brief]] (pasada 1) y el [[Despiece]] (pasada 2)
- Genera la [[Procesos/Proyeccion|Proyección]] de costos
- Produce [[Asignacion]]es confirmadas
- Detecta [[Requerimiento]]s y [[Conflicto]]s
- Su completitud habilita la [[ODS]]
