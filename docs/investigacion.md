# Marco Teórico: Evaluación, Validación y Priorización de Interfaces (APE 6 — Fases 3 y 4)

**Responsable (Paso 2):** William Martínez  
**Asignatura:** Interacción Humano–Computador · Universidad Técnica de Ambato (UTA) · Paralelo 5A

---

## 1. Usabilidad y contexto de uso (ISO 9241-11:2018)

La norma **ISO 9241-11:2018** define la usabilidad como el grado en que un sistema, producto o servicio puede ser utilizado por usuarios específicos para alcanzar objetivos específicos con **eficacia**, **eficiencia** y **satisfacción** en un **contexto de uso** específico:

- **Eficacia:** Precisión y completitud con que el usuario logra sus objetivos.
- **Eficiencia:** Recursos invertidos (tiempo, esfuerzo cognitivo y físico) en relación con los resultados obtenidos.
- **Satisfacción:** Grado en que las respuestas físicas, cognitivas y emocionales del usuario al usar el sistema satisfacen sus necesidades y expectativas.

La usabilidad no es una propiedad absoluta de la interfaz, sino relativa al triángulo **usuarios – tareas – contexto**. En este estudio (prototipo **CaféU**), los usuarios son estudiantes universitarios que no participaron en el diseño, las tareas cubren la consulta de información, armado, modificación, búsqueda y confirmación de pedidos (`T1–T7`), y el contexto es realizar un pedido rápido desde móvil antes de llegar a la cafetería universitaria.

---

## 2. Verificación vs. Validación (Boehm, 1984)

Boehm (1984) distingue dos preguntas fundamentales en ingeniería de software e IHC:

- **Verificación:** *¿Estamos construyendo el producto correctamente?* (el sistema cumple su especificación técnica y no arroja errores de ejecución).
- **Validación:** *¿Estamos construyendo el producto correcto?* (el sistema sirve realmente a las necesidades de sus usuarios en su contexto real).

Esta distinción fundamenta la **pregunta inicial** del laboratorio: *"¿Una interfaz que funciona técnicamente puede ser una mala interfaz?"*. Una interfaz puede superar todas las pruebas técnicas de verificación y, aun así, fracasar en la validación si el usuario no percibe la retroalimentación, comete errores inducidos por el diseño o abandona la tarea.

---

## 3. Evaluación formativa vs. sumativa y métodos analíticos vs. empíricos

### 3.1 Propósito de la evaluación
- **Formativa:** Busca detectar problemas de usabilidad y orientar mejoras durante el ciclo de diseño. Su salida principal son hallazgos accionables priorizados.
- **Sumativa:** Busca certificar o comparar el nivel global de usabilidad frente a estándares o versiones previas mediante métricas estadísticamente representativas.

El presente estudio del APE 6 es principalmente **formativo**: utiliza métricas cuantitativas descriptivas junto con análisis cualitativo para priorizar mejoras en un **backlog en GitHub**.

### 3.2 Complementariedad de métodos
- **Método analítico — Evaluación Heurística de Nielsen:** Evaluadores independientes inspeccionan la interfaz frente a principios reconocidos (las 10 heurísticas de Nielsen, 1994). Nielsen (1993) demostró que un solo evaluador detecta en promedio ~35 % de los problemas, mientras que **cinco evaluadores independientes alcanzan ~75 %**. Su fortaleza es cubrir toda la interfaz; su limitación es el *efecto evaluador* (Hertzum & Jacobsen, 2001) y posibles falsos positivos.
- **Método empírico — Prueba de usabilidad con *Think-Aloud*:** Usuarios representativos ejecutan tareas reales verbalizando sus pensamientos mientras un moderador, un observador y un registrador de métricas capturan desempeño y fricciones (Rubin & Chisnell, 2008). Según Nielsen y Landauer (1993), muestras pequeñas (~5 usuarios) permiten descubrir la mayoría de problemas frecuentes en estudios formativos, aunque Faulkner (2003) advierte variabilidad en muestras pequeñas, por lo que las métricas se reportan como descriptivas.

---

## 4. Métricas de usabilidad y System Usability Scale (SUS)

| Métrica | Dimensión ISO | Definición operativa |
|---|---|---|
| **Tasa de éxito** | Eficacia | `(Tareas completadas sin ayuda / Tareas intentadas) × 100`. |
| **Tiempo en tarea** | Eficiencia | Segundos desde que termina la lectura de la consigna hasta el estado final (se reporta mediana por asimetría de tiempos). |
| **Errores** | Eficacia / Eficiencia | Acciones que desvían al usuario de la meta; se clasifican en **críticos** (impiden completar) y **no críticos** (el usuario se recupera solo). |
| **SUS (Brooke, 1996)** | Satisfacción | Cuestionario de 10 ítems Likert (1–5). Ítems impares: `puntaje − 1`; pares: `5 − puntaje`. La suma se multiplica por `2,5` (rango `0–100`). |

> **Nota metodológica sobre el SUS:** El puntaje SUS **no es un porcentaje**. El promedio de referencia internacional es **68** (Sauro & Lewis, 2016) y se interpreta también mediante escalas adjetivas (Bangor, Kortum & Miller, 2009). Con muestras pequeñas (menores a 12–14 participantes según Tullis & Stetson, 2004), el puntaje se toma como indicador descriptivo.

---

## 5. Las 10 Heurísticas de Nielsen y Escala de Severidad (Fases 3 y 4)

1. Visibilidad del estado del sistema.
2. Coincidencia entre el sistema y el mundo real.
3. Control y libertad del usuario.
4. Consistencia y estándares.
5. Prevención de errores.
6. Reconocer antes que recordar.
7. Flexibilidad y eficiencia de uso.
8. Diseño estético y minimalista.
9. Ayudar a reconocer, diagnosticar y recuperarse de errores.
10. Ayuda y documentación.

### Escala de severidad (Nielsen, 1995)
Cada problema se califica combinando **Frecuencia** (proporción de usuarios/evaluadores afectados), **Impacto** (facilidad o dificultad para superarlo) y **Persistencia** (si molesta una sola vez o repetidamente):

| Nivel | Etiqueta | Criterio operativo | Acción en el Backlog |
|---|---|---|---|
| **1** | **Cosmético** | Problema estético o menor que no afecta la tarea. | Corregir solo si hay tiempo disponible. |
| **2** | **Menor** | Genera vacilación o demora leve; el usuario se recupera solo. | Prioridad baja. |
| **3** | **Mayor** | Provoca errores frecuentes, frustración o demoras importantes. | **Prioridad alta.** |
| **4** | **Crítico** | Impide completar la tarea clave o induce pérdida de trabajo. | **Imperativo corregir de inmediato.** |

---

## 6. Triangulación de resultados

La triangulación cruza los hallazgos de la inspección heurística (`E1–E5`) con la evidencia empírica de los participantes (`P1–P3`):
- **Confirmado por ambos métodos:** Evidencia más sólida (principio violado + impacto real observado).
- **Solo heurística:** Problema potencial en zonas no recorridas por tareas o dependiente del contexto.
- **Solo usuarios:** Fricción real no anticipada en la inspección experta.

---

## Referencias

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
