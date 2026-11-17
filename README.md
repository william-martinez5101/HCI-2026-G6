# HCI-2026-G6

## Datos generales

- Universidad: Universidad Técnica de Ambato.
- Carrera: Ingeniería de Software.
- Asignatura: Interacción Humano–Computador.
- Paralelo: 5A.
- Grupo: 6.
- Tema: Métodos de evaluación de interfaces (Evaluación y validación).
- APE asociado: APE 6 — Fases 3 y 4 (continuación del prototipo CaféU evaluado en Fases 1 y 2 por el Grupo 5).
- Periodo asignado: 18/11/2026 al 24/11/2026.
- Proyecto o interfaz evaluada: **CaféU** ([Prototipo web en Figma Make](https://false-wired-67481015.figma.site) · copia local en [`prototipos/prototipo.html`](prototipos/prototipo.html)).

> **Pregunta inicial del laboratorio:** *¿Una interfaz que funciona técnicamente puede ser una mala interfaz?*

## 1. Problema

**CaféU** es el prototipo de aplicación web móvil diseñado para que los estudiantes universitarios **realicen pedidos en la cafetería antes de llegar** y los retiren sin hacer fila (APE 4 → APE 5 → APE 6). Aunque el prototipo **funciona técnicamente** (navega entre pantallas, calcula totales y genera un número de pedido `#CU-104`), en las Fases 1 y 2 (Grupo 5) se evidenció que el cumplimiento técnico no garantiza una buena experiencia de uso.

Además, quedaron brechas abiertas por resolver en estas **Fases 3 y 4**:
1. Los evaluadores heurísticos del G5 no asignaron una **severidad numérica individual (1 a 4)**, lo que impidió priorizar formalmente los problemas.
2. Ningún participante de la prueba piloto utilizó el buscador ni activó el borrado sin confirmación, dejando hallazgos graves únicamente como "potenciales".
3. Faltaba consolidar la **triangulación completa**, formular los **criterios técnicos de mejora** y traducir los hallazgos en un **backlog priorizado en GitHub Issues**.

## 2. Objetivos

### Objetivo general

Aplicar, triangular y cerrar la evaluación de usabilidad del prototipo **CaféU** (Fases 3 y 4 del APE 6), combinando cinco inspecciones heurísticas independientes con pruebas empíricas de usuarios para priorizar hallazgos por severidad y generar un backlog trazable de mejoras en GitHub.

### Objetivos específicos

1. Ejecutar la Fase 3 mediante **cinco evaluaciones heurísticas independientes** con calificación de severidad (1–4) y **pruebas con usuarios** que cubran también las funciones críticas no exploradas en el pilotaje (buscador y prevención de errores).
2. Medir y consolidar las métricas de usabilidad según **ISO 9241-11:2018** (tasa de éxito, tiempo en tarea, errores y satisfacción mediante **SUS**).
3. Triangular los hallazgos de ambos métodos, clasificar su severidad por **Frecuencia, Impacto y Persistencia**, y construir el **backlog priorizado de mejoras en GitHub Issues** junto con sus criterios técnicos (Fase 4).

## 3. Integrantes y responsabilidades

| Integrante | Usuario de GitHub | Rol en Lab / Exposición | Responsabilidad en el repositorio (Orden consecutivo) |
|---|---|---|---|
| **Emilio Abril** | `@EMILIOABRIL05` | Cronometrista y Coordinador | **Paso 1 y Cierre:** Prototipo, Plan Fase 3, Tareas (`T1–T7`), Heurística E1, Backlog (`8.4`) en Issues, Guion y `README.md` maestro. |
| **William Martínez** | `@william-martinez5101` | Soporte documental | **Paso 2:** Estructura inicial del repo, Marco teórico (`docs/investigacion.md`), Consentimiento, Guía heurística (`1–4`) y Heurística E2. |
| **Manuel Cusme** | `[Por completar]` | Usuario (*Think-Aloud*) | **Paso 3:** Hoja de observación y SUS, Guía de laboratorio, Registros `P1–P3`, Heurística E3, Video de YouTube y Quiz (`.xlsx`). |
| **Pablo Lozada** | `[Por completar]` | Moderador | **Paso 4:** Heurística E4, Métricas y cálculo SUS, Matriz de hallazgos (`8.2`), Triangulación (`8.3`) y Diapositivas (`.pptx`). |
| **Jonathan Gamboa** | `[Por completar]` | Observador y Soporte (F5) | **Paso 5:** Heurística E5, Criterios técnicos (`8.5`), Conclusiones (`docs/conclusiones.md`) y Preguntas QA/UX (`docs/preguntas.md`). |

## 4. Conceptos HCI utilizados

El desarrollo teórico completo se encuentra en [`docs/investigacion.md`](docs/investigacion.md).

| Concepto | Aplicación en el proyecto |
|---|---|
| **Usabilidad (ISO 9241-11:2018)** | Marco de evaluación basado en eficacia, eficiencia y satisfacción para estudiantes universitarios usando CaféU en móvil. |
| **Verificación vs. Validación (Boehm, 1984)** | Sustenta la pregunta inicial: comprobar que el prototipo funciona técnicamente (verificación) no garantiza que el usuario perciba el feedback y logre sus metas (validación). |
| **Evaluación formativa** | Orientada a descubrir problemas reales y priorizar mejoras accionables en lugar de certificar estadísticamente. |
| **Métodos analíticos vs. empíricos** | Combinación de inspección experta (5 evaluadores heurísticos) con observación de usuarios reales (*Think-Aloud*). |
| **Heurísticas de Nielsen (1994)** | 10 principios aplicados de forma independiente por 5 evaluadores para ampliar la cobertura de la interfaz. |
| **Escala de severidad (Nielsen, 1995)** | Calificación numérica `1–4` (Cosmético, Menor, Mayor, Crítico) basada en **Frecuencia, Impacto y Persistencia**. |
| **Métricas y SUS (Brooke, 1996)** | Tasa de éxito, mediana de tiempo, errores críticos/no críticos y puntaje SUS (rango 0–100, referencia 68, no es porcentaje). |
| **Triangulación** | Contraste sistemático entre hallazgos heurísticos y evidencia de usuarios para fundamentar el backlog de mejoras. |

## 5. Métodos de evaluación seleccionados

Se seleccionaron y aplicaron dos métodos complementarios (analítico + empírico):

### Método 1: Evaluación Heurística de Nielsen (5 evaluadores)

- **Nombre:** Evaluación Heurística con calificación de severidad (`1–4`).
- **Objetivo:** Inspeccionar de forma independiente toda la interfaz de CaféU para detectar violaciones a las 10 heurísticas de Nielsen y estimar su severidad.
- **Justificación de su selección:** Según Nielsen (1993), cinco evaluadores independientes detectan aproximadamente el 75 % de los problemas de usabilidad, cubriendo pantallas y funciones que las tareas de usuario podrían no recorrer.
- **Procedimiento de aplicación:** Cada uno de los 5 integrantes (`E1–E5`) inspeccionó el prototipo por separado, registró sus hallazgos y asignó severidad (`1–4`) considerando frecuencia, impacto y persistencia.
- **Instrumentos utilizados:** [`evidencias/06-guia-evaluacion-heuristica.md`](evidencias/06-guia-evaluacion-heuristica.md) y registros individuales `resultados/heuristica-*.md`.

### Método 2: Prueba de Usabilidad con Usuarios (*Think-Aloud*)

- **Nombre:** Prueba de usabilidad moderada con protocolo de pensamiento en voz alta.
- **Objetivo:** Medir eficacia, eficiencia y satisfacción real de estudiantes universitarios nuevos ejecutando tareas críticas (`T1–T7`).
- **Justificación de su selección:** Aporta evidencia empírica directa del comportamiento real y permite validar si los problemas previstos por la heurística afectan a los usuarios (incluyendo el buscador y el control de borrado en `T7`).
- **Procedimiento de aplicación:** Sesiones individuales con consentimiento verbal anonimizado, cuatro roles definidos (Moderador, Usuario, Cronometrista y Observador), reinicio `F5` entre participantes y cuestionario SUS al cierre.
- **Instrumentos utilizados:** [`evidencias/02-consentimiento-informado.md`](evidencias/02-consentimiento-informado.md), [`evidencias/03-tareas.md`](evidencias/03-tareas.md) y `evidencias/04-hoja-de-observacion.md`.


## 6. Procedimiento

### Fase 3: Aplicación y análisis

1. **Contexto y alcance de la evaluación:** Continuación del APE 6 sobre el prototipo móvil **CaféU** (marco 390 × 844 px). Ver [`evidencias/01-plan-y-contexto-fase3.md`](evidencias/01-plan-y-contexto-fase3.md).
2. **Participantes o evaluadores:** 5 evaluadores heurísticos independientes (`E1–E5`, integrantes del Grupo 6) y participantes universitarios externos (`P1–P3`) que no diseñaron el prototipo.
3. **Tareas y escenarios evaluados:** 6 tareas base (`T1–T6`: consulta, armado, modificación y confirmación de pedido) más **1 tarea de refuerzo (`T7`)** para probar el buscador sin tilde (`"sanduche"`) y el botón `"Quitar"`. Ver [`evidencias/03-tareas.md`](evidencias/03-tareas.md).
4. **Aplicación del primer método (Evaluación Heurística):** Inspección individual de las 10 heurísticas de Nielsen asignando severidad numérica `1–4` (Frecuencia, Impacto y Persistencia).
5. **Aplicación del segundo método (Prueba de usabilidad con *Think-Aloud*):** Sesiones individuales con roles definidos (Moderador, Usuario, Cronometrista y Observador), reinicio con `F5` entre participantes y aplicación del cuestionario **SUS** al cierre.
6. **Registro de métricas y evidencias:** Captura de tasa de éxito (*Sí / Con ayuda / No*), tiempos con cronómetro, errores críticos/no críticos y puntajes SUS en `resultados/`.
7. **Análisis y comparación de resultados:** [Por completar en Paso 4 por Pablo Lozada].

### Fase 4: Priorización y cierre

1. **Clasificación de hallazgos por severidad:** [Por completar en Paso 4 por Pablo Lozada].
2. **Triangulación de resultados:** [Por completar en Paso 4 por Pablo Lozada].
3. **Elaboración del backlog de mejoras:** [Por completar en Paso 1-Cierre por Emilio Abril tras consolidación].
4. **Formulación de criterios técnicos:** [Por completar en Paso 5 por Jonathan Gamboa].
5. **Conclusiones y presentación final:** [Por completar en Paso 5 por Jonathan Gamboa].

## 7. Herramientas

| Herramienta | Uso |
|---|---|
| [Por completar] | [Por completar] |

## 8. Resultados

### 8.1. Métricas

[Por completar: definir las métricas utilizadas y sus unidades.]

| Tarea o indicador | Método | Resultado | Interpretación |
|---|---|---|---|
| [Por completar] | [Por completar] | [Por completar] | [Por completar] |

### 8.2. Matriz de hallazgos

[Por completar: definir la escala de severidad utilizada.]

| ID | Método | Hallazgo | Evidencia | Severidad | Mejora propuesta |
|---|---|---|---|---|---|
| [Por completar] | [Por completar] | [Por completar] | [Por completar] | [Por completar] | [Por completar] |

### 8.3. Comparación y triangulación

[Por completar: relacionar los resultados de ambos métodos,
identificar coincidencias y diferencias, y sustentar los hallazgos
con métricas y evidencias.]

### 8.4. Backlog priorizado de mejoras

| ID | Mejora | Hallazgo relacionado | Prioridad | Responsable | Issue |
|---|---|---|---|---|---|
| [Por completar] | [Por completar] | [Por completar] | [Por completar] | [Por completar] | [Por completar] |

### 8.5. Criterios técnicos

[Por completar: justificar las recomendaciones para mejorar
la interfaz a partir de los resultados de la evaluación.]

## 9. Evidencias y entregables

- **Interfaz o prototipo evaluado:** [CaféU en Figma Make](https://false-wired-67481015.figma.site) · respaldo local [`prototipos/prototipo.html`](prototipos/prototipo.html).
- **Instrumentos de evaluación:** [`evidencias/01-plan-y-contexto-fase3.md`](evidencias/01-plan-y-contexto-fase3.md), [`evidencias/03-tareas.md`](evidencias/03-tareas.md) *(consentimiento, hoja SUS y guía heurística en Pasos 2 y 3)*.
- **Registro de aplicación de los métodos:** [`resultados/heuristica-emilio.md`](resultados/heuristica-emilio.md) *(evaluaciones E2–E5 y sesiones P1–P3 en Pasos 2–5)*.
- **Métricas y matriz de hallazgos:** [Por completar en Paso 4].
- **Backlog priorizado de mejoras:** [Por completar al cierre con Issues de GitHub].
- **Presentación final del APE 6:** [Por completar en Paso 4 (`docs/presentacion-G6.pptx`)].
- **Video y Quiz de exposición:** [Por completar en Paso 3 (`docs/quiz-wayground-APE6.xlsx`)].

## 10. Organización del repositorio

| Carpeta o archivo | Contenido previsto |
|---|---|
| `README.md` | Descripción general y síntesis del trabajo (14 secciones). |
| `docs/investigacion.md` | Fundamentos teóricos HCI, ISO 9241-11, métodos y severidad. |
| `docs/preguntas.md` | Pregunta inicial, preguntas técnicas, objeciones y QA/UX. |
| `docs/conclusiones.md` | Conclusiones y criterios técnicos. |
| `prototipos/prototipo.html` | Prototipo CaféU evaluado (copia autocontenida). |
| `evidencias/` | Plan Fase 3, consentimiento, tareas (`T1–T7`), hoja SUS y guía heurística. |
| `src/` | Recursos técnicos de apoyo, si corresponde. |
| `resultados/` | Evaluaciones heurísticas (`E1–E5`), registros `P1–P3`, matriz y triangulación. |

## 11. Trabajo colaborativo

- **Distribución de tareas mediante Issues:** Trabajo consecutivo en 5 pasos (Emilio Abril, William Martínez, Manuel Cusme, Pablo Lozada y Jonathan Gamboa) + Issues del backlog de mejoras.
- **Commits individuales identificables:** Cada integrante registra commits propios en su rama asociada a su Issue.
- **Ramas utilizadas:**
  - `feat/emilio-prototipo-plan-backlog` (Emilio Abril — Paso 1 y cierre)
  - `docs/william-investigacion-etica-heuristica` (William Martínez — Paso 2)
  - `data/manuel-pruebas-video-quiz` (Manuel Cusme — Paso 3)
  - `data/pablo-metricas-triangulacion-ppt` (Pablo Lozada — Paso 4)
  - `docs/jonathan-criterios-conclusiones-preguntas` (Jonathan Gamboa — Paso 5)
- **Pull Requests:** Cada rama se integra hacia `main` mediante Pull Request revisado.

## 12. Preguntas técnicas y objeciones

- Pregunta técnica 1: [Por completar].
- Respuesta y evidencia: [Por completar].

- Pregunta técnica 2: [Por completar].
- Respuesta y evidencia: [Por completar].

- Objeción planteada: [Por completar].
- Respuesta y justificación técnica: [Por completar].

## 13. Conclusiones

1. [Por completar.]
2. [Por completar.]
3. [Por completar.]

## 14. Referencias

- Bangor, A., Kortum, P., & Miller, J. (2009). Determining what individual SUS scores mean: Adding an adjective rating scale. *Journal of Usability Studies, 4*(3), 114–123.
- Boehm, B. W. (1984). Verifying and validating software requirements and design specifications. *IEEE Software, 1*(1), 75–88.
- Brooke, J. (1996). SUS: A "quick and dirty" usability scale. En *Usability Evaluation in Industry* (pp. 189–194). Taylor & Francis.
- Faulkner, L. (2003). Beyond the five-user assumption: Benefits of increased sample sizes in usability testing. *Behavior Research Methods, Instruments, & Computers, 35*(3), 379–383.
- Hertzum, M., & Jacobsen, N. E. (2001). The evaluator effect: A chilling fact about usability evaluation methods. *International Journal of Human-Computer Interaction, 13*(4), 421–443.
- ISO 9241-11:2018. *Ergonomics of human-system interaction — Part 11: Usability: Definitions and concepts.*
- Nielsen, J. (1993). *Usability Engineering.* Academic Press.
- Nielsen, J. (1994). Enhancing the explanatory power of usability heuristics. *Proceedings of CHI '94*, 152–158.
- Nielsen, J. (1995). *Severity ratings for usability problems.* Nielsen Norman Group.
- Nielsen, J., & Landauer, T. K. (1993). A mathematical model of the finding of usability problems. *Proceedings of INTERCHI '93*, 206–213.
- Rubin, J., & Chisnell, D. (2008). *Handbook of Usability Testing* (2.ª ed.). Wiley.
- Sauro, J., & Lewis, J. R. (2016). *Quantifying the User Experience: Practical Statistics for User Research* (2.ª ed.). Morgan Kaufmann.
- Tullis, T. S., & Stetson, J. N. (2004). A comparison of questionnaires for assessing website usability. *Usability Professionals Association Conference.*