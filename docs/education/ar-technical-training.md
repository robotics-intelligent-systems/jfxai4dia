# Capacitación técnica en realidad aumentada

Propuesta educativa · 2026-10-11. Diagramas y contratos de lección; cliente AR, asset 3D y tracking aún pendientes.

| Lección | Principio / modelo | Capa AR propuesta | Evaluación |
|---|---|---|---|
| AG: equilibrio a flote | Arquímedes y masa/CG; AG-SIM-HY/MB | CG, centro de carena y fuerzas sobre dos flotadores | Explicar por qué B=mg no demuestra estabilidad; AG-R-02/05 y AG-V-05. |
| AG: rotor | Balance de par; AG-SIM-RT | Ω y par aerodinámico por régimen | Distinguir rotor libre y motorizado; señalar AG-D-05. |
| HG: rotor–ala | Sustentación y mapas acoplados; HG-SIM-WI/RT | Vectores rotor/ala/propulsores por segmento | Explicar límites de ala aislada en transición; HG-R-03/05. |
| HG: híbrido | Conservación de potencia/energía; HG-SIM-EN/TH | Generador, batería, pérdidas y reserva | Identificar balances y límites; HG-R-04. |
| EV: sustentación | Newton–Euler y asignación; EV-SIM-MC/FD | Empuje, brazos y momentos | Explicar equilibrio/saturación sin presumir tolerancia a fallo; EV-R-03 y EV-D-05. |
| EV: batería y estructura | Energía, temperatura y elasticidad; EV-SIM-EN/TH/ST | Potencia, temperatura y cargas en brazos/patines | Distinguir mapa conceptual y resultado validado; EV-R-04/06/10. |

## Contrato de lección y contenido

Cada lesson_id enlaza concept_id, configuration_id/hash, module_id/IF, R/V, model_id, reference_id/URL, objetivos, ecuación, unidades, supuestos y dominio. El asset procede de geometría identificada, con escala, ejes y transformación T_world_model; JPG sólo sirve como panel documental, no como malla AR.

Overlays registran source_kind (synthetic / simulated / measured), run_id/fuente, sello temporal, marco, métrica/unidad, incertidumbre y estado de validación. Si tracking o calidad de dato falla, ocultar overlay espacial y conservar vista documental. Vectores y texto acompañan al color. Al seleccionar una magnitud, abrir su ecuación, referencia y requisito completos.

## Requisitos educativos propuestos

- AR-EDU-01: cada overlay resuelve configuración, requisito, modelo y referencia; revisión del manifiesto sin IDs huérfanos.
- AR-EDU-02: escala/ejes/anclaje se contrastan con fixture conocida; tolerancias y dispositivos TBD antes del piloto.
- AR-EDU-03: cada vista distingue datos sintéticos, simulados y medidos; revisión de etiquetas y casos inválidos.
- AR-EDU-04: instructor aprueba objetivos y rúbrica; comparar explicaciones antes/después de la lección, con umbral y muestra TBD.
- AR-EDU-05: modo documental ante fallo de tracking; revisión de accesibilidad/legibilidad con dispositivos seleccionados.

Estos requisitos educativos son nuevos y propuestos, separados de los requisitos de aeronave. Completar una lección no cierra R/V ni habilita operación.

## Próxima tarea

**DIA-AR-001:** prototipar una lección AG de CG, flotación y estabilidad con datos sintéticos rotulados. Preparar asset/manifest, ejercicio de unidades y rúbrica de instructor. Seleccionar tecnología y dispositivo tras aprobar necesidades; no se declara integración de hardware.

[Modelos y referencias](../simulation/README.md) · [Diagramas AR](../../MBSE/CAS/Drawio/jfxai4dia-ar-technical-training.drawio).
