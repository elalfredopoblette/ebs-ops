## ¿Qué es?
Empresa o persona que contrata los servicios de EBS para un [[Evento]].

> Vive en **Odoo** — este sistema lo referencia, no lo gestiona.

## Tipos frecuentes
| Tipo | Descripción |
|---|---|
| Promotora | Organiza giras y conciertos masivos |
| Productora | Eventos de entretenimiento y corporativos |
| Marca | Activaciones y eventos de marketing |
| Venue | El recinto contrata servicios para sus eventos |
| Gobierno | Festivales públicos, eventos institucionales |

## Atributos mínimos (referencia desde Odoo)
- `id_odoo`, `nombre`, `tipo`
- `contacto_principal` → [[Contacto]]
- `ciudad_frecuente`

## Relaciones
- Un Cliente puede tener muchos [[Proyecto]]s
- El [[Brief]] es el primer documento que vincula Cliente con Proyecto
- Pagos y facturas se gestionan en Odoo
