## ¿Qué es?
Un Turno es el registro de la participación de una [[Persona]] en un día
específico de un [[Evento]], con su [[Tipo de Dia]] correspondiente.

Es la unidad mínima del cálculo de PXE (destajos).

## Atributos
- `persona` → [[Persona]] (quien trabaja)
- `evento` → [[Evento]]
- `fecha` — fecha del día
- `tipo_dia` → [[Tipo de Dia]] — Previo / Montaje / Show / Guardia / Desmontaje
- `puntos` — derivado del tipo_dia
- `pago_dia` — calculado: puntos × VALOR_X_PUNTO del puesto en [[Tabulador]]
- `estado` — Planeado / Ejecutado / Cancelado / Convertido (Guardia→Montaje)

## Cálculo del pago

### Personal con tabulador estándar (México)
```
pago_dia = puntos(tipo_dia) × VALOR_X_PUNTO(puesto)

Ejemplo — Armador en día de Montaje:
  1.5 pts × $600 = $900

Ejemplo — Armador en día de Show:
  0.5 pts × $600 = $300
```

### Pago total por evento por persona
```
Pago operativo = BASE_FIJA(puesto)
               + Σ pago_dia por cada Turno ejecutado

Viáticos = días_presentes × VIÁTICO_DÍA(puesto)

Pago total = Pago operativo + Viáticos
```

### Armador Eventual
Su VALOR_X_PUNTO = 0, por lo que sus Turnos no generan pago variable.
Su compensación es la BASE_FIJA negociada directamente.

### Personal internacional (Sudamérica)
Monto cerrado acordado individualmente. No usa el tabulador estándar.
Se registra como monto_fijo en la Proyección.

## Ciclo de vida
```
Planeado (en Proyección) → Ejecutado (confirma trabajo realizado)
                         → Cancelado (persona no asistió)
                         
Guardia → [reporte de campo] → Convertido a Montaje (decisión Gerente Ops)
```

## Quién asigna los Turnos
El [[Project Manager]] junto con el [[Jefe de Steel]] y [[Supervisor EPS]]
durante la fase de [[Procesos/Proyeccion|Proyección]] del evento.
Los jefes de área pueden ajustar los turnos en campo según lo que realmente ocurra.

## Quién aprueba el cierre
1. [[Project Manager]] aprueba los turnos ejecutados del evento
2. [[Gerente Operaciones]] da aprobación final antes de que pasen a pago

La conversión de Guardia → Montaje la decide **exclusivamente** el Gerente de Operaciones.

## Personal de último momento
Si alguien se incorpora en campo sin estar en la Proyección, el [[Jefe de Steel]]
o [[Supervisor EPS]] lo registra en lista manual. El [[Gerente Operaciones]] sube
ese nombre a la base de datos para poder incluirlo en la Proyección retroactivamente
y procesar su pago.

## Relaciones
- Pertenece a un [[Evento]]
- Su tipo define el costo via [[Tabulador]] y [[Tipo de Dia]]
- Sus totales forman la sección PXE de la [[ODS]]
- Su aprobación desencadena el proceso en [[Pagos Por Evento (destajos)]]
