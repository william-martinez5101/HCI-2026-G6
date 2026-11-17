# Guía de Evaluación Heurística Individual con Escala de Severidad (1–4)

**Responsable (Paso 2):** William Martínez  
**Evaluadores del Grupo 6:** E1 Emilio Abril · E2 William Martínez · E3 Manuel Cusme · E4 Pablo Lozada · E5 Jonathan Gamboa  
**Prototipo:** https://false-wired-67481015.figma.site · [`prototipos/prototipo.html`](../prototipos/prototipo.html)

---

## Reglas para los 5 evaluadores

1. Inspeccionar el prototipo **de forma individual** sin ver las respuestas de los demás compañeros hasta terminar (evita sesgos y reduce el *efecto evaluador*).
2. Probar cada acción directamente en el prototipo navegable.
3. Para cada heurística responder **Sí / Parcial / No**, describir el hallazgo concreto y asignar obligatoriamente una **severidad numérica de 1 a 4** (o `0` si cumple sin problema).
4. Guardar el archivo individual como `resultados/heuristica-<nombre>.md`.

---

## Rúbrica de Severidad (Nielsen, 1995)

| Valor | Nivel | Frecuencia + Impacto + Persistencia |
|---|---|---|
| **0** | Sin problema | La heurística se cumple satisfactoriamente. |
| **1** | **Cosmético** | Detalle visual o de redacción menor; no afecta el flujo. |
| **2** | **Menor** | Causa duda o demora leve; el usuario se recupera por sí mismo. |
| **3** | **Mayor** | Causa errores frecuentes, confusión importante o requiere trabajo extra repetido. |
| **4** | **Crítico** | Impide completar una tarea clave o provoca pérdida grave del progreso. |

---

## Las 10 preguntas guía de inspección

| # | Heurística de Nielsen | Qué probar en CaféU | Pregunta de control |
|---|---|---|---|
| **1** | Visibilidad del estado del sistema | Agregar un producto desde su detalle | ¿Se percibe claramente el aviso de confirmación y el conteo por categoría? |
| **2** | Coincidencia con el mundo real | Leer horario en Inicio y nombres del menú | ¿El formato horario (`7:00 – 19:00`) y los nombres son naturales para todo estudiante? |
| **3** | Control y libertad del usuario | Pulsar `"Quitar"` en `"Mi pedido"` | ¿Existe opción de deshacer o revertir un borrado accidental? |
| **4** | Consistencia y estándares | Comparar botones de volver y colores de botones principales | ¿Tienen la misma etiqueta, ubicación y color en todas las pantallas? |
| **5** | Prevención de errores | Pulsar `"Quitar"` en `"Mi pedido"` | ¿Se pide confirmación antes de ejecutar una acción destructiva? |
| **6** | Reconocer antes que recordar | Ver selector de cantidad (`− / +`) en detalle del producto | ¿Se distingue de inmediato para pedir varias unidades sin repetir clics en "Agregar"? |
| **7** | Flexibilidad y eficiencia de uso | Escribir **`sanduche`** (sin tilde) en el buscador | ¿El buscador tolera palabras sin tilde para acelerar la búsqueda? |
| **8** | Diseño estético y minimalista | Revisar jerarquía y tamaños de texto en móvil (390 px) | ¿Todos los textos informativos son legibles sin competir con elementos secundarios? |
| **9** | Ayudar a recuperarse de errores | Buscar **`pizza`** en el menú | ¿El estado vacío explica qué ocurrió y ofrece una acción clara para recuperarse? |
| **10** | Ayuda y documentación | Revisar Inicio, Mi pedido y Confirmación | ¿Se informa cómo se paga, dónde se retira y cuánto tarda el pedido? |
