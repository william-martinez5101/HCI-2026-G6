# Resumen del Pilotaje · Validación de Protocolo y Transición a Fase 3

**Responsable (Paso 4):** Pablo Lozada  
**Rol:** Moderador del Laboratorio de Usabilidad / Responsable de Métricas y Triangulación  
**Asignatura:** Interacción Humano–Computador · Paralelo 5A · Universidad Técnica de Ambato  
**Contexto del documento:** Análisis de los resultados de la prueba piloto (Fase 2, heredada del Grupo 5) y formalización de las mejoras metodológicas aplicadas en la Fase 3 por el Grupo 6.  
**Prototipo evaluado:** CaféU ([Figma Make](https://false-wired-67481015.figma.site) · local [`prototipos/prototipo.html`](../prototipos/prototipo.html))  

---

## 1. Propósito y alcance de la prueba piloto (Fase 2)

La prueba piloto tuvo como propósito fundamental validar los instrumentos y el procedimiento experimental antes de la aplicación definitiva:
1. Comprobar la claridad y comprensión de las consignas leídas a los participantes.
2. Calibrar los tiempos meta estimados y los tiempos máximos tolerables para cada tarea (`T1` a `T6`).
3. Verificar la estabilidad y respuesta del prototipo interactivo CaféU en un marco simulado de teléfono móvil (390 × 844 px).
4. Probar la aplicación en vivo de la hoja de observación, el registro de errores críticos/no críticos y el cuestionario SUS de 10 ítems.

---

## 2. Resultados descriptivos del pilotaje de referencia

En la sesión piloto de referencia participaron usuarios representativos del entorno universitario con el protocolo básico de 6 tareas:

| Tarea | Consigna del pilotaje | Tasa de éxito | Tiempo observado | Desempeño y observaciones del usuario piloto |
|---|---|---|---|---|
| **T1** | Horario de atención | 100 % (Sí) | 26 s | Ubicó de inmediato el recuadro en Inicio. Dudó 2 segundos interpretando el formato de 24 horas (`"7:00 – 19:00"`). |
| **T2** | Agregar sánduche de queso | 100 % (Sí) | 41 s | Navegó por la categoría `"Comida"` y seleccionó el producto. No percibió con claridad el mensaje toast inferior porque se desvaneció rápidamente. |
| **T3** | Agregar dos cafés americanos | 100 % (Sí) | 68 s | Tuvo dificultad para identificar los botones `−` y `+` por su bajo contraste; presionó dos veces `"Agregar al pedido"`, acumulando 3 cafés en lugar de 2, corrigiendo luego en el carrito. |
| **T4** | Quitar sánduche y confirmar pedido | 100 % (Sí) | 62 s | Pulsó `"Quitar"`; el ítem desapareció al instante sin confirmación. Logró confirmar el pedido obteniendo el código `#CU-104`. |
| **T5** | Conteo de productos de comida | 100 % (Sí) | 31 s | Filtró por `"Comida"` y contó visualmente las 3 tarjetas de productos (Sánduche, Croissant y Empanada). |
| **T6** | Cotizar 3 croissants | 100 % (Sí) | 48 s | Abrió el detalle de Croissant, ajustó la cantidad a 3 y leyó el total dinámico calculado en el botón (`$5.25`). |

### Métricas síntesis del pilotaje:
- **Eficacia global (T1–T6):** 100 % de éxito con ayuda nula.
- **Eficiencia (Mediana de tiempo):** 44.5 segundos por tarea (todas concluidas antes del tiempo máximo de 2 a 3 minutos).
- **Satisfacción preliminar (SUS):** 72.5 / 100 puntos (escala adjetiva: *Aceptable / Buena*).

---

## 3. Brechas metodológicas identificadas en el pilotaje

A pesar del éxito operativo de las tareas base, el análisis crítico del pilotaje reveló cuatro deficiencias graves que limitaban la validez de la evaluación formativa:

1. **Falta de cobertura del buscador:**  
   Ningún participante del pilotaje utilizó la barra de búsqueda interactiva; todos optaron naturalmente por las pestañas de categoría (`"Bebidas"`, `"Comida"`). En consecuencia, el comportamiento del motor de búsqueda ante variaciones ortográficas (como la omisión de tildes en `"sanduche"`) quedó inexplorado por usuarios reales.
2. **Falta de verificación del borrado destructivo:**  
   En la tarea `T4`, aunque el usuario usó `"Quitar"`, lo hizo con la intención consciente de eliminar. No se evaluó el impacto de un toque accidental ni la necesidad de recuperación o confirmación de la acción destructiva.
3. **Ausencia de escala de severidad numérica en la inspección heurística:**  
   Los evaluadores del Grupo 5 se limitaron a registrar un cumplimiento dicotómico (*Sí/No*), lo que impedía clasificar, jerarquizar y priorizar técnicamente los hallazgos en un Backlog de ingeniería de software.
4. **Acumulación de estado entre sesiones:**  
   Si no se reinicia el prototipo con `F5` entre participantes, el carrito conserva los productos agregados por el usuario anterior y el número de pedido correlativo se incrementa, distorsionando las tareas de los participantes subsecuentes.

---

## 4. Ajustes y refuerzos metodológicos adoptados para la Fase 3 (Grupo 6)

Para subsanar las brechas anteriores, el Grupo 6 diseñó e incorporó las siguientes mejoras en el protocolo de la Fase 3:

| Brecha del pilotaje | Ajuste metodológico en Fase 3 | Documento de respaldo |
|---|---|---|
| Búsqueda y borrado inexplorados | Creación formal de la **Tarea T7 de refuerzo**: *"Usa el buscador para encontrar un 'sanduche' escribiéndolo sin tilde, agrégalo y luego quítalo de tu pedido."* | [`evidencias/03-tareas.md`](../evidencias/03-tareas.md) |
| Sin severidad numérica | Implementación de la **Rúbrica de Severidad 1–4 de Nielsen (1995)** evaluando Frecuencia, Impacto y Persistencia para los 5 evaluadores independientes (`E1–E5`). | [`evidencias/06-guia-evaluacion-heuristica.md`](../evidencias/06-guia-evaluacion-heuristica.md) |
| Contaminación de estados | Establecimiento de la **regla de reinicio obligatorio con `F5`** antes de iniciar cada participante para restaurar el pedido inicial `#CU-104`. | [`evidencias/01-plan-y-contexto-fase3.md`](../evidencias/01-plan-y-contexto-fase3.md) |
| Asignación de responsabilidades | Estructuración del laboratorio en **4 roles activos:** Moderador (Pablo Lozada), Cronometrista (Emilio Abril), Observador (Jonathan Gamboa) y Usuario Think-Aloud (Manuel Cusme / `P1–P3`). | [`evidencias/01-plan-y-contexto-fase3.md`](../evidencias/01-plan-y-contexto-fase3.md) |
| Triangulación formal | Adopción de la **matriz de triangulación sistemática** (cruce de inspección analítica con métricas empíricas ISO 9241-11 y SUS). | [`resultados/heuristica-consolidado.md`](heuristica-consolidado.md) y `README.md (8.3)` |

---

## 5. Conclusión del pilotaje

El pilotaje demostró que CaféU es una interfaz **técnicamente funcional**, fluida y con un aspecto visual atractivo, pero con fallas de diseño de interacción que solo una tarea de estrés cognitivo como `T7` y una inspección heurística con severidad 1–4 podían evidenciar. Los ajustes aprobados en este resumen sirvieron de base directa para la ejecución rigurosa de las pruebas con usuarios `P1`, `P2` y `P3`.
