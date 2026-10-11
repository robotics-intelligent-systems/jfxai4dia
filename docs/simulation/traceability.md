# Trazabilidad requisito → módulo → modelo → verificación

Estado: propuesto; evidencia pendiente. Fuente: especificaciones Markdown revisión B. Los modelos apoyan análisis; las actividades de revisión, demostración y ensayo se mantienen.

| Requisito | Módulo | Modelo de apoyo | Verificación | Criterio de cierre |
|---|---|---|---|---|
| AG-R-01 | AG-M-00 | Revisión / demostración; sin modelo físico asignado | AG-V-01 | CONOPS aprobado con ocupación, carga, duración, alcance y operación agua/tierra definidos. |
| AG-R-02 | AG-M-00 | AG-SIM-MB | AG-V-02 | Masa y CG de cada caso de carga y consumo dentro de límites TBD aprobados; informe y pesaje. |
| AG-R-03 | AG-M-01 | AG-SIM-RT, AG-SIM-FD | AG-V-03 | Envolvente, márgenes y tolerancia de correlación TBD satisfechos; campaña progresiva documentada. |
| AG-R-04 | AG-M-03 | AG-SIM-EN, AG-SIM-TH | AG-V-04 | Ciclo de misión y reserva TBD cubiertos sin exceder límites térmicos TBD; curvas de banco y balance. |
| AG-R-05 | AG-M-04 | AG-SIM-HY | AG-V-05 | Estabilidad, reserva de flotabilidad, oleaje y daño definidos TBD satisfechos; balance y ensayos acuáticos. |
| AG-R-06 | AG-M-01 / AG-M-02 / AG-M-03 | AG-SIM-ST | AG-V-06 | Casos de carga, márgenes, fatiga y ambiente húmedo acordados TBD satisfechos; análisis e inspección. |
| AG-R-07 | AG-M-02 | Revisión / demostración; sin modelo físico asignado | AG-V-07 | Población y escenarios definidos; acceso, visibilidad y evacuación cumplen criterios TBD; demostración. |
| AG-R-08 | AG-M-05 | AG-SIM-CT | AG-V-08 | Latencias, alertas y respuestas degradadas TBD cumplidas en integración y fallos simulados. |
| AG-R-09 | AG-M-00 | AG-SIM-MB | AG-V-09 | ICD y configuración identificados; sustitución dentro de tiempo TBD con inspección funcional conforme. |
| AG-R-10 | AG-M-00 | Revisión / demostración; sin modelo físico asignado | AG-V-10 | AG-D-02 resuelta; peligros trazados y tratamiento de riesgos residuales revisado según proceso acordado. |
| AG-R-11 | AG-M-06 | AG-SIM-MB, AG-SIM-RT, AG-SIM-FD, AG-SIM-ST, AG-SIM-HY | AG-V-11 | Error y dominio TBD cumplidos con modelos versionados y datos separados para calibración/validación. |
| AG-R-12 | AG-M-04 | AG-SIM-ST, AG-SIM-HY | AG-V-12 | AG-D-03 cerrada; si aplica tierra, apoyo, frenado y transición cumplen cargas y escenarios TBD. |
| HG-R-01 | HG-M-00 | Revisión / demostración; sin modelo físico asignado | HG-V-01 | CONOPS con ocupantes [n], carga [kg], alcance [km], duración [min] y reserva TBD aprobado. |
| HG-R-02 | HG-M-00 | HG-SIM-MB | HG-V-02 | MTOM [kg] y envolvente CG [m] TBD cumplidos en todos los casos de misión y módulos. |
| HG-R-03 | HG-M-01 | HG-SIM-RT, HG-SIM-WI, HG-SIM-FD | HG-V-03 | Régimen TBC, envolvente [m/s], RPM, viento y distancia de despegue [m] TBD cerrados; modelos correlacionados y evidencia de transición. |
| HG-R-04 | HG-M-04 | HG-SIM-EN, HG-SIM-TH | HG-V-04 | Balance de potencia [kW], energía [kWh], combustible [kg] si aplica, eficiencia y temperatura [K] TBD dentro de límites; curvas y ciclo de misión. |
| HG-R-05 | HG-M-03 | HG-SIM-WI, HG-SIM-CT | HG-V-05 | Mapa de empuje [N], asimetría, fallos y márgenes TBD satisfechos; interacciones rotor-ala-propulsores evaluadas. |
| HG-R-06 | HG-M-02 | HG-SIM-ST | HG-V-06 | Cargas [N], momentos [N m], vida y márgenes TBD satisfechos en rotor, ala, módulos y tren; informe de casos. |
| HG-R-07 | HG-M-02 | Revisión / demostración; sin modelo físico asignado | HG-V-07 | Ocupación TBC y criterios de accesibilidad, visibilidad y tiempo [s] TBD cumplidos en maqueta. |
| HG-R-08 | HG-M-05 | HG-SIM-CT | HG-V-08 | Latencias [ms], alertas, respuestas y aceptación de riesgos TBD cumplidas; fallos y trazas documentados. |
| HG-R-09 | HG-M-00 | HG-SIM-MB | HG-V-09 | ICD completos, tiempo [min] y herramientas TBD; prueba posterior conforme y nuevo balance de masa/CG. |
| HG-R-10 | HG-M-06 | HG-SIM-MB, HG-SIM-WI, HG-SIM-FD, HG-SIM-EN | HG-V-10 | Error, incertidumbre y dominio TBD satisfechos con datos independientes; COM-R-03 y COM-R-04 cumplidos. |
| EV-R-01 | EV-M-00 | Revisión / demostración; sin modelo físico asignado | EV-V-01 | Ocupación TBC, carga [kg], duración [min], radio [km], viento [m/s] y reserva TBD definidos en CONOPS. |
| EV-R-02 | EV-M-00 | EV-SIM-MB | EV-V-02 | MTOM [kg] y límites CG [m] TBD cumplidos con ocupante, batería y módulos; informe y pesaje. |
| EV-R-03 | EV-M-02 | EV-SIM-MC, EV-SIM-FD | EV-V-03 | Número de rotores TBC, empuje [N], márgenes, envolvente y fallos TBD definidos y satisfechos; interacción entre rotores evaluada. |
| EV-R-04 | EV-M-03 | EV-SIM-EN, EV-SIM-TH | EV-V-04 | Potencia [kW], energía utilizable [kWh], tensión [V], corriente [A], temperatura [K] y estado de carga [%] TBD cumplidos en ciclo de misión. |
| EV-R-05 | EV-M-04 | EV-SIM-CT | EV-V-05 | Latencias [ms], disponibilidad, pérdida de sensor/comunicación/actuador y respuesta TBD satisfechas; registros sincronizados. |
| EV-R-06 | EV-M-01 | EV-SIM-ST | EV-V-06 | Cargas [N], momentos [N m], impacto, vida y márgenes TBD satisfechos; asignación compartida con EV-M-05. |
| EV-R-07 | EV-M-01 | Revisión / demostración; sin modelo físico asignado | EV-V-07 | Población, exposición ambiental, separación de rotores y tiempo de evacuación [s] TBD evaluados en maqueta. |
| EV-R-08 | EV-M-00 | EV-SIM-MB | EV-V-08 | ICD, tiempo [min] y herramientas TBD definidos; inspección y prueba posteriores conformes; impacto masa/CG evaluado. |
| EV-R-09 | EV-M-00 | EV-SIM-CT, EV-SIM-TH | EV-V-09 | Escenarios, criterios de riesgo y respuestas TBD revisados; no se presume tolerancia a fallo de un rotor. |
| EV-R-10 | EV-M-06 | EV-SIM-MB, EV-SIM-MC, EV-SIM-FD, EV-SIM-EN, EV-SIM-ST | EV-V-10 | Error, incertidumbre, sincronización [ms] y dominio TBD satisfechos; calibración separada de validación. |
