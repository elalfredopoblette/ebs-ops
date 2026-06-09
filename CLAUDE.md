# EBS OPS — Sistema Operativo EBS Group

## Objetivo del Proyecto

Plataforma operativa para EBS Group, empresa especializada en montaje de estructuras temporales para eventos y espectáculos.

**Esta plataforma NO reemplaza Odoo.** Odoo sigue siendo el sistema de CRM, cotizaciones, compras, facturación y contabilidad.

Esta plataforma es el sistema operativo de la **ejecución de proyectos**.

---

## Fase Actual: Modelado de Dominio

**NO estamos desarrollando software todavía.**

Estamos modelando el negocio. La prioridad es descubrir:
- Entidades
- Procesos
- Relaciones
- Reglas de negocio
- Flujos operativos

Antes de diseñar bases de datos, APIs o interfaces.

---

## Obsidian como Fuente de Verdad

La documentación vive en:
```
C:\Users\Administrador\Desktop\obsidian\OPERACIONES\EBS OPS\
```

Estructura del vault:
```
EBS OPS/
├── Entidades EBS/      # 18 entidades modeladas
├── Documentos/         # ODS, Brief, Cotización, Despiece, etc.
├── Procesos/           # Load In, Load Out, Reserva, ShowDay, etc.
├── Roles/              # PM, Supervisor EPS, Jefe Steel, etc.
├── Áreas/              # Operaciones, Comercial, Almacén, etc.
├── Relaciones/         # Asignación, Conflicto, Movimiento, Requerimiento
└── Categoria de Servicios/  # STEEL, EPS
```

---

## Hallazgos Clave del Dominio

### Hipótesis Principal
La operación gira alrededor de:
```
Demanda de Recursos → Disponibilidad → Asignación → Ejecución → Liberación
```

### Recurso
Cualquier elemento **limitado** que puede ser asignado a un proyecto durante un periodo determinado.
- Roof Systems, Delay Towers, LD Rolls, Arena Panels
- Barricadas, Sprinters, Personal
- Todos tienen: Disponibilidad, Estado, Ubicación

### Inventario
**NO es un recurso.** Representa la disponibilidad y estado de recursos.

### ODS
**NO es el centro del sistema.** Es un documento que comunica decisiones previamente tomadas.

---

## Stack Tecnológico Objetivo

| Capa | Tecnología |
|------|-----------|
| Backend | Python + FastAPI |
| Base de Datos | PostgreSQL |
| ORM | SQLAlchemy |
| Frontend | Por definir |
| Auth | Por definir |
| Infra | Por definir |

---

## Instrucciones para Claude

### Al analizar una nota de Obsidian:
1. Detecta entidades faltantes
2. Detecta conceptos duplicados o mal clasificados
3. Sugiere relaciones no documentadas
4. Identifica impacto en el modelo de dominio
5. Propón refinamientos DDD (Bounded Contexts, Aggregates, Value Objects)

### Restricciones estrictas:
- **NO** generar pantallas hasta que el modelo de dominio sea estable
- **NO** generar tablas de BD hasta que las entidades estén claramente definidas
- **NO** generar código CRUD por defecto
- **SIEMPRE** cuestionar clasificaciones y relaciones
- **NUNCA** asumir que el modelo está terminado

### Enfoque DDD:
- Priorizar modelado sobre programación
- Identificar Bounded Contexts
- Distinguir Entities vs Value Objects vs Aggregates
- Mapear Domain Events
- Descubrir el Ubiquitous Language de EBS

---

## Comandos Útiles

```bash
# Ver notas de Obsidian desde el proyecto
ls "C:\Users\Administrador\Desktop\obsidian\OPERACIONES\EBS OPS\"

# Leer una entidad específica
cat "C:\Users\Administrador\Desktop\obsidian\OPERACIONES\EBS OPS\Entidades EBS\Recurso.md"
```

---

## Estado del Modelo

| Categoría | Notas | Estado |
|-----------|-------|--------|
| Entidades | 18 | En progreso |
| Documentos | 8 | En progreso |
| Procesos | 11 | En progreso |
| Roles | 6 | En progreso |
| Áreas | 8 | En progreso |
| Relaciones | 4 | En progreso |
| Categorías de Servicio | 6 | En progreso |
