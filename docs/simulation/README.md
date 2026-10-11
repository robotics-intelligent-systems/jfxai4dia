# Modelos científicos de alto nivel

Revisión C propuesta · 2026-10-11. Formulaciones, contratos y campañas de análisis en draw.io; ninguna simulación numérica o validación de aeronave ejecutada.

## Notación y unidades

Vistas gráficas de SysML 1.7 en draw.io, no un modelo XMI ni un programa SysML ejecutable. «satisfy» denota asignación candidata; «verify» identifica una actividad prevista. Las flechas apuntan al requisito y no declaran cumplimiento. Bindings sin flecha en par representan igualdad; la dirección de cálculo pertenece a sim. Los puertos/item flows son lógicos: tipos, unidades y límites requieren ICD.

Fuerzas/momentos en marco cuerpo B; posición y velocidad en I. R_BI transforma B→I. Gravedad g_I [m/s²], masa [kg], inercia J [kg m²], velocidad angular ω y Ω [rad/s], energía [J], potencia [W], tiempo [s], temperatura [K]. Convertir RPM y kWh en las fronteras. El modelo rígido congela masa/inercia por segmento; consumo relevante exige extensión de masa variable y términos de flujo. Parámetros ausentes son TBD, nunca cero por defecto.

## Modelos y principios físicos

| Sufijo SIM | Formulación de cribado | Entradas / salidas y dominio |
|---|---|---|
| MB | m=Σm_i; r_CG=Σ(m_i r_i)/m | Masas, coordenadas y revisión CAD → masa, CG e inercia; comprobar con pesaje y mediciones independientes. |
| FD | m dv_I/dt = m g_I + R_BI F_B; J dω/dt = M_B − ω×(Jω) | Newton–Euler rígido, inercia constante por segmento; falta integrar cinemática de actitud y validar mapas de fuerza. |
| RT | J_r dΩ/dt = Q_drive + Q_aero − Q_loss; T,Q=mapas(Ω,V,ρ,paso) | Balance de par del rotor/propulsor; AG autorrotación TBC exige Q_drive=0 tras prerrotación y equilibrio estable demostrado. |
| WI | q=ρV²/2; L=qS C_L; D=qS C_D | HG rotor–ala–propulsores; coeficientes dependientes del régimen; la ecuación de ala aislada no resuelve transición/estacionario. |
| MC | wrench=B_alloc f; T_i=mapas_i(Ω_i,V); P_ideal=T_i^(3/2)/√(2ρA_i) | EV asignación de empuje/momento; potencia ideal sólo disco aislado en hover fuera de efecto suelo, no pérdidas/interacción ni tolerancia a fallo. |
| EN | dE_b/dt=−P_b; P_gen+P_b=P_load+P_loss | P_b>0 descarga y P_b<0 carga; pérdidas no negativas; AG fuente TBC, HG híbrido, EV P_gen=0 en configuración batería. |
| TH | C_th dT/dt=P_heat−hA(T−T_amb) | C_th [J/K], hA [W/K], T [K]; modelo concentrado, no propagación de fuga térmica ni gradientes resueltos. |
| ST | M_s ü+C_s u̇+K_s u=f(t) | Estructura lineal elástica; condiciones de apoyo, cargas y propiedades TBD. Impacto/contacto/fatiga/corrosión requieren modelos adicionales. |
| HY | B=ρ_w g ∇; equilibrio B=mg; M_restore≈−mg GM φ | AG agua calma, ángulos pequeños; ∇ [m³], GM [m], φ [rad]. Estabilidad depende de geometría/CG; no oleaje, planeo o slamming. |
| CT | y_k=h(x_k)+ε_k; u_k=control(y,modo,referencia) | Sensado y control a diseñar: períodos, ruido, retraso, saturación y fallos TBD; canal de ingeniería sin autoridad de vuelo. |

Las ecuaciones son propuestas de ingeniería para organizar el análisis. Las referencias siguientes aportan contexto teórico; no validan estas configuraciones ni sustituyen la derivación y revisión de modelos específicos. Prefijos AG/HG/EV-SIM identifican cada aplicación. AG usa MB/RT/FD/EN/TH/ST/HY/CT; HG usa MB/RT/WI/FD/EN/TH/ST/CT; EV usa MB/MC/FD/EN/TH/ST/CT.

## Parámetros, acoplamiento y manifiesto de ejecución

Se requieren CAD dimensionado, geometría/masa/CG/inercia, propiedades, mapas T/Q, mission segments, ambiente, límites y reservas aprobados. Los cuatro propulsores HG son hipótesis de la lámina; rotor/regímenes HG y AG continúan TBC. EV mantiene cantidad de rotores TBC. AG mantiene apoyo terrestre condicional.

Acoplamiento propuesto: estado/ambiente → rotor/ala/agua → fuerzas y momentos → dinámica; demanda → energía/temperatura → límites/control → próximo paso. Registrar Δt e interpolación, sincronización y residuales de balance; refinamiento de paso y malla por disciplina. Interacción fuerte requiere iteración o solver monolítico por definir. La cadena de herramientas es candidata.

Cada run manifest incluirá: concept_id, configuration_id/hash, R/V aplicables, modelo/versiones, geometría/malla, parámetros con unidades/ejes, condiciones iniciales/de frontera, solver y tolerancias, semillas si aplica, datasets separados de calibración/validación, métricas/unidades, incertidumbre, avisos, resultados y revisor. Ausencia de información obligatoria bloquea la ejecución.

## Campaña y criterios

Casos nominales, extremos de carga/CG/ambiente, inválidos (unidades/ejes/masa/datos) y fallos seleccionados. AG añade flotación/estanqueidad y agua/tierra condicional; HG transición/asimetría/híbrido; EV saturación/asignación y fallos definidos. Verificación de solver, calibración y validación independiente son actividades distintas. Criterios de error, incertidumbre y dominio siguen TBD. No extrapolar resultados fuera del dominio.

Los requisitos de misión, factores humanos, mantenimiento y riesgos requieren revisión, demostración y ensayo además de simulación. La [matriz](traceability.md) cubre las 32 obligaciones específicas; COM-R-01…06 figuran en la vista común. AG-R-12 conserva su condición de aplicabilidad.

## Referencias teóricas para documentación y capacitación

- [REF-SYSML: OMG SysML 1.7](https://www.omg.org/spec/SysML/1.7/) — req, bdd, ibd, act y par; asignaciones y verificación planificadas.
- [REF-ROTOR: NASA NDARC theory (2016)](https://ntrs.nasa.gov/api/citations/20160012474/downloads/20160012474.pdf) — Dinámica y teoría de rotor; seleccionar régimen y capítulo antes de implementar. AG/HG: RT/FD; EV: MC/FD.
- [REF-LIFT: NASA Glenn: lift equation](https://www1.grc.nasa.gov/beginners-guide-to-aeronautics/lift-equation/) — HG-SIM-WI: L=ρ V² S C_L/2; coeficientes requieren datos y régimen.
- [REF-BUOY: OpenStax: Arquímedes](https://openstax.org/books/university-physics-volume-1/pages/14-4-archimedes-principle-and-buoyancy) — AG-SIM-HY: peso del fluido desplazado; no demuestra estabilidad ni oleaje.
- [REF-BAT: Modelica Standard Library 4.0.0: Batteries](https://doc.modelica.org/Modelica%204.0.0/Resources/helpDymola/Modelica_Electrical_Batteries_UsersGuide.html) — EN/TH: modelos equivalentes eléctricos y térmicos; referencia, no dependencia instalada.

Consultadas 2026-10-11. Modelica 4.0.0 es una referencia documental versionada, no una dependencia instalada. Para una lección: seleccionar principio, mostrar unidades/ecuación/supuestos y explicar qué evidencia falta antes de inferir cumplimiento.

## Próxima iteración asistida por IA

**DIA-SIM-002:** acordar un escenario AG de flotación estática en agua calma, cerrar masa/CG/geometría/ρ/GM y criterios con responsable de hidrodinámica. Implementar una fixture reproducible de equilibrio, perturbación pequeña e inputs inválidos; contrastar datos independientes antes de evaluar AG-R-05. Gate: CAD dimensionado y parámetros aprobados; no obtenerlos de píxeles.

[Diagramas](../diagrams/README.md) · [Capacitación AR](../education/ar-technical-training.md) · [Requisitos](../requirements/README.md).
