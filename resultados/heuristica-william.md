# Evaluación Heurística Individual (E2) · Prototipo CaféU

**Evaluador:** William Martínez (E2)  
**Método:** Inspección independiente con las 10 heurísticas de Nielsen (1994)  
**Escala de severidad:** `0` Sin problema · `1` Cosmético · `2` Menor · `3` Mayor · `4` Crítico

---

## Resultados de la inspección

| # | Heurística de Nielsen | ¿Cumple? | Qué se observó en el prototipo | Severidad (1–4) | Justificación (Frecuencia / Impacto / Persistencia) |
|---|---|---|---|---|---|
| **1** | Visibilidad del estado del sistema | **No** | El toast de confirmación queda cortado hacia la derecha al terminar la animación y pasa inadvertido; el usuario solo nota el cambio en el contador inferior. | **3 (Mayor)** | Ocurre en cada producto agregado (alta frecuencia) y deja duda de si el clic funcionó. |
| **2** | Coincidencia entre el sistema y el mundo real | **Parcial** | El formato de 24 h (`19:00`) puede requerir una pausa breve de lectura frente al formato `7:00 p. m.` habitual. | **1 (Cosmético)** | Impacto mínimo en universitarios, aunque mejorable en claridad. |
| **3** | Control y libertad del usuario | **No** | Al presionar `"Quitar"` en el carrito no existe botón de deshacer ni recuperación rápida del ítem eliminado. | **3 (Mayor)** | Si el usuario borra por error, debe regresar al menú y volver a configurar cantidad. |
| **4** | Consistencia y estándares | **No** | Etiquetas de navegación de retorno inconsistentes (`"Menú"`, `"Seguir comprando"`, `"Volver al menú"`) y botón `"Agregar al pedido"` en color café en lugar de naranja primario. | **2 (Menor)** | Rompe la consistencia visual entre acciones principales, aunque no bloquea el flujo. |
| **5** | Prevención de errores | **No** | Falta confirmación previa antes de eliminar un producto del pedido con `"Quitar"`. | **3 (Mayor)** | Acción destructiva sin barrera de prevención en interfaz táctil. |
| **6** | Reconocer antes que recordar | **No** | El control `− / +` de cantidad pasa poco visible junto al botón principal, induciendo a agregar dos veces el producto. | **2 (Menor)** | Impacto moderado en pedidos múltiples; el usuario se da cuenta al revisar `"Mi pedido"`. |
| **7** | Flexibilidad y eficiencia de uso | **No** | El buscador exige tildes exactas: escribir `"sanduche"` no devuelve `"Sánduche de queso"`. | **3 (Mayor)** | Afecta directamente a quienes usan búsqueda rápida desde teclado móvil. |
| **8** | Diseño estético y minimalista | **Parcial** | Algunas etiquetas secundarias (`10–11 px`) resultan muy pequeñas en pantalla móvil. | **1 (Cosmético)** | Diseño limpio en general, pero con contraste/tamaño mejorable en etiquetas menores. |
| **9** | Ayudar a reconocer, diagnosticar y recuperarse de errores | **Sí** | Al buscar un producto inexistente (`"pizza"`), muestra `"No encontramos productos"` y el botón `"Limpiar búsqueda"`. | **0 (Sin problema)** | Permite diagnóstico y recuperación inmediata en un toque. |
| **10** | Ayuda y documentación | **No** | No especifica ubicación de la cafetería, método de pago ni tiempo estimado de entrega. | **2 (Menor)** | Falta información operativa para el retiro real del pedido. |
