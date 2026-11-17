# Evaluación Heurística Individual (E5) · Prototipo CaféU

**Evaluador:** Jonathan Gamboa (E5)  
**Método:** Inspección independiente con las 10 heurísticas de Nielsen (1994)  
**Escala de severidad (Nielsen, 1995):** `0` Sin problema · `1` Cosmético · `2` Menor · `3` Mayor · `4` Crítico  
**Criterios considerados:** Frecuencia, Impacto y Persistencia  
**Prototipo inspeccionado:** CaféU ([enlace Figma Make](https://false-wired-67481015.figma.site) / [`prototipos/prototipo.html`](../prototipos/prototipo.html))

---

## Resultados de la inspección (10 heurísticas)

| # | Heurística de Nielsen | ¿Cumple? | Qué se observó en el prototipo | Severidad (1–4) | Justificación (Frecuencia / Impacto / Persistencia) |
|---|---|---|---|---|---|
| **1** | Visibilidad del estado del sistema | **No** | El mensaje toast `"Producto agregado al pedido"` aparece cortado hacia el borde derecho en el marco de 390 px; el usuario no puede confirmar visualmente si la acción tuvo efecto sin abrir `"Mi pedido"` manualmente. | **3 (Mayor)** | Alta frecuencia (ocurre en cada producto agregado); impacto moderado-alto (genera re-verificación innecesaria); persistente en toda la sesión de pedido. |
| **2** | Coincidencia entre el sistema y el mundo real | **Parcial** | El horario se expresa en formato de 24 horas (`7:00 – 19:00`) cuando el público universitario está más familiarizado con `a. m. / p. m.`. La terminología del menú (ej. `"Sánduche"`) es local y adecuada. | **1 (Cosmético)** | Frecuencia baja; el impacto es mínimo dado el perfil joven del usuario. No bloquea ninguna tarea. |
| **3** | Control y libertad del usuario | **No** | El botón `"Quitar"` en la pantalla `"Mi pedido"` elimina el ítem de forma inmediata sin ofrecer un paso de deshacer ni una confirmación emergente. Si el usuario actúa por error, debe regresar al menú y reconfigurar el producto. | **3 (Mayor)** | Impacto alto en pedidos con varios ítems; la ausencia de recuperación genera ansiedad y desconfianza en la interfaz táctil. |
| **4** | Consistencia y estándares | **No** | Las etiquetas de retorno varían entre pantallas (`"Menú"`, `"Seguir comprando"`, `"Volver al menú"`). El botón `"Agregar al pedido"` usa un color café oscuro diferente al terracota primario (`#d94716`) de `"Ver menú"` y `"Confirmar pedido"`. | **2 (Menor)** | Frecuencia media (presente en cada pantalla de detalle y en el carrito); impacto leve porque el usuario puede completar las tareas pese a la inconsistencia. |
| **5** | Prevención de errores | **No** | La acción de borrado con `"Quitar"` es destructiva e irreversible sin ningún diálogo preventivo. En pantallas táctiles, un toque accidental puede eliminar un producto sin que el usuario tenga tiempo de reaccionar. | **3 (Mayor)** | Alta persistencia (el riesgo existe en cada ítem del carrito); impacto moderado-alto: produce errores operativos difíciles de recuperar sin reiniciar el flujo. |
| **6** | Reconocer antes que recordar | **No** | El control de cantidad `− / +` en la vista de detalle del producto presenta bajo contraste cromático y un área táctil inferior a los 44 × 44 px recomendados por WCAG 2.1, lo que induce al usuario a pulsar `"Agregar al pedido"` repetidas veces. | **3 (Mayor)** | Frecuencia media-alta en pedidos con más de un ítem; genera errores no críticos (duplicación de productos) que alteran el subtotal del pedido. |
| **7** | Flexibilidad y eficiencia de uso | **No** | El buscador aplica coincidencia literal de cadenas Unicode: ingresar `"sanduche"` (sin tilde) no devuelve `"Sánduche de queso"`, presentando un estado vacío que lleva al usuario a abandonar la ruta rápida de búsqueda. | **3 (Mayor)** | Alta frecuencia en teclados móviles que suprimen tildes; impacto crítico (bloqueo total de la función de búsqueda); persistente porque afecta a cualquier término acentuado del catálogo. |
| **8** | Diseño estético y minimalista | **Parcial** | Algunas etiquetas secundarias (categorías, contadores) usan tamaños de 10–11 px, que se encuentran por debajo del mínimo de 12 px recomendado para legibilidad en pantallas móviles en condiciones de alta luminosidad. | **1 (Cosmético)** | Impacto visual leve; no impide completar las tareas en el perfil de usuario universitario joven, pero reduce el confort de lectura. |
| **9** | Ayudar a reconocer, diagnosticar y recuperarse de errores | **Sí** | Cuando una búsqueda no arroja resultados, el sistema muestra el mensaje `"No encontramos productos"` junto al botón `"Limpiar búsqueda"`, proporcionando diagnóstico claro y una salida directa al estado anterior. | **0 (Sin problema)** | El mecanismo de recuperación es claro, inmediato y no requiere acción adicional del usuario. |
| **10** | Ayuda y documentación | **No** | La pantalla de confirmación del pedido (`#CU-104`) no indica el punto físico de retiro en la cafetería, el tiempo estimado de preparación ni las modalidades de pago aceptadas (efectivo, transferencia), información esencial para completar la experiencia real. | **2 (Menor)** | Frecuencia alta (todos los usuarios finalizan en esta pantalla); impacto moderado (genera consultas fuera del sistema al moderador o al personal de la cafetería). |

---

## Resumen de hallazgos para triangulación (E5)

| ID | Heurística | Severidad | Hallazgo principal |
|---|---|:---:|---|
| H-01 | H7 — Flexibilidad y eficiencia | **3 (Mayor)** | Buscador insensible a tildes: `"sanduche"` no encuentra `"Sánduche de queso"`. |
| H-02 | H3, H5 — Control y prevención | **3 (Mayor)** | Borrado destructivo con `"Quitar"` sin confirmación ni opción de deshacer. |
| H-03 | H1 — Visibilidad del estado | **3 (Mayor)** | Toast de confirmación cortado en 390 px, pasa desapercibido. |
| H-04 | H6 — Reconocer antes que recordar | **3 (Mayor)** | Selector `− / +` con bajo contraste y área táctil insuficiente. |
| H-05 | H4 — Consistencia | **2 (Menor)** | Etiquetas de retorno inconsistentes y variación de color en botones primarios. |
| H-06 | H10 — Ayuda y documentación | **2 (Menor)** | Ausencia de información de retiro, pago y tiempo estimado en la confirmación. |
| H-07 | H2 — Mundo real | **1 (Cosmético)** | Horario en formato de 24 h (`7:00 – 19:00`) en tipografía pequeña. |
| H-08 | H8 — Diseño minimalista | **1 (Cosmético)** | Etiquetas secundarias en 10–11 px, por debajo del mínimo recomendado. |
| — | H9 — Recuperación de errores | **0 (Sin problema)** | Estado vacío y `"Limpiar búsqueda"` cumplen correctamente. |

> **Nota del evaluador:** Los cuatro hallazgos de severidad 3 (H-01 a H-04) coinciden con los reportados por los evaluadores E1–E4, lo que refuerza la solidez de la triangulación y justifica su clasificación como prioridad alta en el backlog de mejoras de la Fase 4.
