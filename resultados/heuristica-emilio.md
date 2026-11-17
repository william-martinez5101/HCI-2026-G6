# Evaluación Heurística Individual (E1) · Prototipo CaféU

**Evaluador:** Emilio Abril (E1)  
**Método:** Inspección independiente con las 10 heurísticas de Nielsen (1994)  
**Escala de severidad (Nielsen, 1995):** `1` Cosmético · `2` Menor · `3` Mayor · `4` Crítico  
**Criterios considerados:** Frecuencia, Impacto y Persistencia  
**Prototipo inspeccionado:** CaféU ([enlace Figma Make](https://false-wired-67481015.figma.site) / [`prototipos/prototipo.html`](../prototipos/prototipo.html))

---

## Resultados de la inspección (10 heurísticas)

| # | Heurística de Nielsen | ¿Cumple? | Qué se observó en el prototipo | Severidad (1–4) | Justificación (Frecuencia / Impacto / Persistencia) |
|---|---|---|---|---|---|
| **1** | Visibilidad del estado del sistema | **No** | Al agregar un producto desde su detalle, el aviso `"Producto agregado al pedido"` aparece desplazado y cortado en el borde derecho del marco móvil (390 px), pasando desapercibido. Además, `"7 productos"` confunde al filtrar por categoría. | **3 (Mayor)** | Alta frecuencia (ocurre en cada pedido), impacto moderado (genera incertidumbre y re-verificación en `"Mi pedido"`), persistente en toda la sesión. |
| **2** | Coincidencia entre el sistema y el mundo real | **Parcial** | El horario se muestra en formato de 24 horas (`"7:00 – 19:00"`) en tipografía pequeña, lo que exige conversión mental a algunos usuarios. | **2 (Menor)** | Frecuencia baja-media, impacto leve (demora mínima), fácil de superar. |
| **3** | Control y libertad del usuario | **No** | En `"Mi pedido"`, el botón `"Quitar"` elimina el ítem inmediatamente sin opción de **Deshacer** ni recuperación rápida. | **3 (Mayor)** | Impacto alto si se presiona por accidente en pedidos largos; obliga a volver al menú y rearmar el producto. |
| **4** | Consistencia y estándares | **No** | Los botones de retorno cambian de etiqueta y posición según la pantalla (`"Menú"`, `"Seguir comprando"`, `"Volver al menú"`), y el botón `"Agregar al pedido"` usa color café oscuro distinto al naranja primario de `"Ver menú"` y `"Confirmar pedido"`. | **2 (Menor)** | Inconsistencia visual y verbal repetida entre pantallas, aunque el usuario logra completar el flujo. |
| **5** | Prevención de errores | **No** | `"Quitar"` ejecuta una acción destructiva (borrado del ítem) sin diálogo de confirmación ni prevención ante toques accidentales en pantalla táctil. | **3 (Mayor)** | Prevenible con confirmación o deshacer; impacto moderado-alto en usabilidad móvil. |
| **6** | Reconocer antes que recordar | **No** | El selector de cantidad (`− / +`) en el detalle del producto tiene bajo contraste y tamaño reducido, provocando que se pulse `"Agregar al pedido"` varias veces en lugar de ajustar la cantidad. | **3 (Mayor)** | Frecuencia media-alta en pedidos múltiples; genera errores no críticos y confusión con el total. |
| **7** | Flexibilidad y eficiencia de uso | **No** | El buscador es estricto con las tildes: al escribir `"sanduche"` sin tilde no arroja `"Sánduche de queso"`, mostrando estado vacío. | **3 (Mayor)** | Alta frecuencia esperada en teclados móviles sin autocorrección; bloquea la ruta rápida de búsqueda. |
| **8** | Diseño estético y minimalista | **Parcial** | Etiquetas de categoría (`10 px`), contador (`11 px`) y bloque de horario tienen tamaño de fuente reducido para lectura rápida en móvil. | **1 (Cosmético)** | Afecta legibilidad visual sin bloquear la completitud de la tarea en público universitario joven. |
| **9** | Ayudar a reconocer, diagnosticar y recuperarse de errores | **Sí** | Cuando la búsqueda no arroja resultados, muestra un mensaje claro (`"No encontramos productos"`) acompañado de una acción directa (`"Limpiar búsqueda"`). | **0 (Sin problema)** | Cumple adecuadamente con diagnóstico y recuperación clara. |
| **10** | Ayuda y documentación | **No** | No se informa el punto exacto de retiro en la cafetería, el tiempo estimado de preparación ni las modalidades de pago aceptadas antes o después de confirmar. | **2 (Menor)** | Genera dudas de contexto real de uso, aunque no impide completar la simulación del pedido. |

---

## Resumen de hallazgos críticos/mayores para triangulación (E1)
1. **H1 (`Severidad 3`):** Confirmación visual cortada al agregar producto.
2. **H3 / H5 (`Severidad 3`):** Eliminación directa en `"Mi pedido"` sin confirmación ni deshacer.
3. **H7 (`Severidad 3`):** Buscador insensible/estricto con tildes (`"sanduche"`).
4. **H6 (`Severidad 3`):** Selector de cantidad (`− / +`) poco visible.
