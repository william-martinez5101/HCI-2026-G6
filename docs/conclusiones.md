# Conclusiones — APE 6, Fases 3 y 4 · Grupo 6

**Proyecto evaluado:** CaféU · **Método:** Evaluación heurística (5 evaluadores) + Prueba de usabilidad Think-Aloud (3 participantes)  
**Periodo:** 18/11/2026 – 24/11/2026 · **Paralelo:** 5A · **Grupo:** 6

---

## Conclusiones generales

1. **El prototipo CaféU es funcionalmente correcto, pero no suficientemente usable.**  
   Las tareas estándar `T1–T6` se completaron con una tasa de éxito del 100 % y una mediana de tiempo de 38.5 s, dentro del umbral de 60 s previsto. Sin embargo, la incorporación de la tarea de refuerzo `T7` —que ejercitó el buscador y el control de borrado— reveló fallos críticos que redujeron la tasa global al 85.7 %. Este resultado confirma que el cumplimiento técnico (verificación) no garantiza una experiencia de uso satisfactoria (validación), respondiendo directamente a la pregunta inicial del laboratorio: *¿Una interfaz que funciona técnicamente puede ser una mala interfaz?* **Sí puede serlo.**

2. **La triangulación metodológica validó y priorizó los hallazgos con evidencia doble.**  
   En 5 de los 8 hallazgos identificados (62.5 %) hubo concordancia directa entre la inspección heurística experta (E1–E5) y la evidencia empírica de los participantes (P1–P3). Esta convergencia elevó el nivel de confianza en la priorización del backlog: los cuatro problemas de severidad 3 —buscador sin tildes (H-01), borrado sin confirmación (H-02), toast desalineado (H-03) y selector de cantidad poco visible (H-04)— quedaron respaldados por datos cualitativos y cuantitativos de campo, no solo por juicio experto.

3. **El buscador representa el fallo crítico principal del prototipo.**  
   El hallazgo H-01 (insensibilidad del buscador a tildes Unicode) fue el único problema que produjo errores críticos bloqueantes durante las pruebas con usuarios: 0 % de éxito autónomo en T7, dos errores críticos y un abandono total. Este fallo es especialmente grave porque afecta la ruta de eficiencia del sistema, que es precisamente la funcionalidad que diferencia a CaféU de un menú estático. Su corrección mediante normalización Unicode (`normalize("NFD")`) es técnicamente trivial y de alto impacto.

4. **La satisfacción percibida refleja la experiencia dividida.**  
   El puntaje SUS promedio de 70.83 supera el umbral de referencia de la industria (68.0 puntos), pero oculta una disparidad significativa: los participantes que recorrieron flujos guiados sin obstáculos valoraron la aplicación entre 75.0 y 77.5, mientras que el participante que experimentó el bloqueo del buscador y los controles pequeños otorgó 60.0. Esto demuestra que un problema de interacción localizado puede degradar severamente la percepción global de calidad del sistema.

5. **Los criterios técnicos de mejora son precisos, trazables y priorizables.**  
   Los ocho hallazgos consolidados se tradujeron en criterios técnicos concretos (Sección 8.5 del README) que especifican qué componente modificar, con qué patrón y bajo qué estándar (WCAG 2.1, Material Design, ISO 9241-11). Esta trazabilidad entre hallazgo → criterio técnico → Issue de GitHub garantiza que el backlog de mejoras sea accionable por cualquier desarrollador, sin ambigüedad, independientemente de si participó en la evaluación.

---

## Criterios técnicos de mejora derivados

> Los criterios completos se encuentran documentados en la **Sección 8.5** del `README.md`. A continuación se presenta la síntesis ejecutiva:

| ID | Hallazgo | Criterio técnico | Estándar de referencia |
|---|---|---|---|
| H-01 | Buscador insensible a tildes | Normalizar cadenas con `normalize("NFD").replace(/[\u0300-\u036f]/g, "").toLowerCase()` antes de comparar. | — |
| H-02 | Borrado sin confirmación | Añadir diálogo modal de confirmación o snackbar con acción `"Deshacer"` (ventana de 5 s). | Material Design — Snackbar pattern |
| H-03 | Toast desalineado en 390 px | Centrar con `mx-auto inset-x-4`, ampliar duración a 3.5 s y animar el badge del carrito. | WCAG 2.1 — Timing Adjustable |
| H-04 | Selector `− / +` poco visible | Rediseñar con área táctil mínima de 44 × 44 px y ratio de contraste ≥ 4.5:1. | WCAG 2.1 SC 1.4.3 y 2.5.5 |
| H-05 | Etiquetas de retorno inconsistentes | Estandarizar con icono de flecha + texto único `"Menú"` y color terracota `#d94716`. | — |
| H-06 | Ausencia de info de retiro/pago | Agregar módulo en pantalla de confirmación: tiempo estimado (~8 min), pago y punto de retiro. | ISO 9241-11:2018 — Eficacia |
| H-07 | Horario en formato 24 h | Cambiar a `"Lunes a viernes de 7:00 a. m. a 7:00 p. m."`. | — |
| H-08 | Tipografía secundaria < 12 px | Incrementar tamaño base de etiquetas secundarias a 12–13 px. | WCAG 2.1 SC 1.4.4 |
