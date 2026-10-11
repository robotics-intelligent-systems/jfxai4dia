# Diagramas SysML, simulación y capacitación

Revisión C propuesta · 2026-10-11. Abrir .drawio en diagrams.net: cajas/conectores editables. Markdown conserva la fuente de las obligaciones; no hay modelo SysML ejecutable.

| Concepto | SysML | Modelos científicos | Especificación |
|---|---|---|---|
| AG | [SysML](../../MBSE/CAS/Drawio/amphibious-gyroplane-sysml-high-level.drawio) | [Simulación](../../MBSE/CAS/Drawio/amphibious-gyroplane-scientific-simulation.drawio) | [Requisitos](../requirements/concepts/amphibious-gyroplane.md) |
| HG | [SysML](../../MBSE/CAS/Drawio/hybrid-gyrodyne-sysml-high-level.drawio) | [Simulación](../../MBSE/CAS/Drawio/hybrid-gyrodyne-scientific-simulation.drawio) | [Requisitos](../requirements/concepts/hybrid-gyrodyne.md) |
| EV | [SysML](../../MBSE/CAS/Drawio/opentwin-evtol-sysml-high-level.drawio) | [Simulación](../../MBSE/CAS/Drawio/opentwin-evtol-scientific-simulation.drawio) | [Requisitos](../requirements/concepts/opentwin-evtol.md) |

[Requisitos y actividad comunes](../../MBSE/CAS/Drawio/jfxai4dia-common-engineering.drawio) · [Capacitación AR](../../MBSE/CAS/Drawio/jfxai4dia-ar-technical-training.drawio).

Cada SysML incluye siete páginas: req 1/2, req 2/2, bdd, ibd, act, par y vv. Cada modelo científico incluye sim, exp y ref. La vista común contiene req y act; AR contiene bdd y act. **Ocho archivos, 34 páginas**; 32 obligaciones específicas y seis comunes representadas, sin cierre de requisitos.

«satisfy»: bloque/modelo → requisito; «verify»: actividad → requisito. Composición lógica en bdd; conectores/item flows en ibd; igualdad en par. Unidades, supuestos y dominios: [modelos](../simulation/README.md). [Trazabilidad](../simulation/traceability.md). Notación: [OMG SysML 1.7](https://www.omg.org/spec/SysML/1.7/).

AG mantiene R/V-01…12 y antecedente revisión A; AG-R-12 es condicional. HG conserva hipótesis de cuatro propulsores y régimen rotor TBC. EV conserva cantidad de rotores TBC; no se presume redundancia.

[Lecciones AR](../education/ar-technical-training.md): capas de módulos, fuerzas, energía y evidencia, objetivos y referencias. Cliente AR pendiente.

## Verificación documental

XML, IDs y conectores contrastados; cobertura R/V revisada contra tablas fuente. Disposición y ajuste de textos revisados mediante vistas de control. No CFD, FEA, simulación de vuelo, ensayo ni prueba AR ejecutados. Modelos científicos de alto nivel significa formulación y campaña propuestas en draw.io, no un solver.
