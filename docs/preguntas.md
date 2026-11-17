# Preguntas técnicas y QA/UX — APE 6 · Grupo 6

**Proyecto:** CaféU · **Responsable:** Jonathan Gamboa (E5, Observador)  
**Contexto:** Preguntas preparadas para la sesión de exposición grupal, cobertura de QA/UX y posibles objeciones del evaluador.

---

## Pregunta inicial del laboratorio

> **¿Una interfaz que funciona técnicamente puede ser una mala interfaz?**

**Respuesta con evidencia del proyecto:**  
Sí. CaféU demuestra esto de forma concreta: las tareas estándar `T1–T6` se completaron con 100 % de éxito, confirmando que el prototipo *funciona*. Sin embargo, el buscador —que aplica coincidencia literal de cadenas Unicode— bloqueó completamente la tarea `T7` (0 % de éxito autónomo, 2 errores críticos, 1 abandono). La distinción entre **verificación** (Boehm, 1984: ¿el sistema hace lo que se especificó?) y **validación** (¿el sistema hace lo que el usuario necesita?) es exactamente el núcleo teórico que este resultado ejemplifica.

---

## Preguntas técnicas de exposición

### Pregunta técnica 1
**¿Por qué se eligió la evaluación heurística con 5 evaluadores en lugar de hacer más pruebas con usuarios?**

**Respuesta y evidencia:**  
Según Nielsen y Landauer (1993), 5 evaluadores expertos detectan aproximadamente el 75 % de los problemas de usabilidad, con un costo significativamente menor que ampliar la muestra de usuarios. La combinación de ambos métodos (analítico + empírico) fue deliberada: la heurística cubrió pantallas y funciones que las tareas con usuarios no recorrieron (por ejemplo, la lectura de textos secundarios en H-08), mientras que las pruebas con usuarios aportaron la validación empírica de los hallazgos catalogados como "potenciales" en el pilotaje —concretamente H-01 y H-02, que pasaron de supuestos a **severidad mayor comprobada** tras la tarea T7.

### Pregunta técnica 2
**¿Cómo se calculó el puntaje SUS y qué significa 70.83 en términos reales?**

**Respuesta y evidencia:**  
El System Usability Scale (Brooke, 1996) utiliza 10 ítems en escala Likert (1–5). La fórmula es: `[(Suma ítems impares − 5) + (25 − Suma ítems pares)] × 2.5`. El puntaje de **70.83** supera el umbral de referencia global de **68.0 puntos** (Sauro & Lewis, 2016), ubicándose en la categoría adjetiva de *Bueno* según Bangor et al. (2009). Sin embargo, este promedio oculta una disparidad: P2, que experimentó el bloqueo del buscador, otorgó **60.0** (*Regular / Marginal alto*), mientras que P1 y P3, que no encontraron obstáculos graves, calificaron con 75.0 y 77.5 respectivamente. Esto confirma que los problemas localizados degradan la percepción global del sistema.

---

## Objeción anticipada

**Objeción planteada:**  
*"Con solo 3 participantes, los resultados de las pruebas con usuarios no son estadísticamente representativos."*

**Respuesta y justificación técnica:**  
La evaluación tiene carácter **formativo**, no estadístico. El objetivo es detectar problemas de usabilidad accionables, no generalizar con significancia estadística. Según Faulkner (2003), 3–5 participantes son suficientes para identificar los problemas de usabilidad más frecuentes en fases de prototipado. Además, los hallazgos más graves (buscador, borrado) fueron detectados de forma convergente por los **5 evaluadores heurísticos independientes** y los **3 participantes empíricos**, lo que, mediante triangulación metodológica, otorga solidez suficiente para fundamentar el backlog de la Fase 4 sin necesidad de una muestra estadísticamente significativa.

---

## Preguntas de QA/UX para la exposición

Estas preguntas son para verificar la comprensión técnica del equipo durante la defensa:

| # | Pregunta QA/UX | Respuesta esperada |
|---|---|---|
| 1 | ¿Cuál es la diferencia entre un error crítico y un error no crítico en este contexto? | Un error **crítico** bloquea el cumplimiento de la tarea sin ayuda externa (ej. buscador en T7). Un error **no crítico** retrasa pero no impide la compleción (ej. doble clic en "Agregar al pedido"). |
| 2 | ¿Por qué se usó la mediana en lugar del promedio para medir tiempos? | La mediana es más robusta ante valores atípicos. Con solo 3 participantes, un tiempo extremo (ej. 145 s de P2 en T7) inflaría el promedio distorsionando la métrica de eficiencia. |
| 3 | ¿Qué heurística de Nielsen cubre el fallo del buscador (H-01)? | La **H7: Flexibilidad y eficiencia de uso**. El buscador no ofrece un atajo eficiente para usuarios que no usan tildes, forzando el recorrido manual por categorías. |
| 4 | ¿Qué significa que el SUS esté por encima de 68 pero uno de los participantes haya puntuado por debajo? | Que la experiencia de usuario no es uniforme: el sistema es aceptable en su flujo principal, pero un fallo localizado es suficiente para que un subgrupo de usuarios lo perciba como deficiente. |
| 5 | ¿Cómo se trasladaría el criterio técnico H-01 a código concreto? | Reemplazando la comparación de cadenas en el filtro del buscador por: `str.normalize("NFD").replace(/[\u0300-\u036f]/g, "").toLowerCase()` tanto en la entrada del usuario como en el catálogo de productos. |
