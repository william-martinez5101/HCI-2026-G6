# Evaluación Heurística Individual (E4) · Prototipo CaféU

**Evaluador:** Pablo Lozada (E4)  
**Rol en el equipo:** Moderador del Laboratorio de Usabilidad / Responsable de Métricas y Triangulación  
**Método:** Inspección independiente con las 10 heurísticas de Nielsen (1994)  
**Escala de severidad (Nielsen, 1995):** `0` Sin problema · `1` Cosmético · `2` Menor · `3` Mayor · `4` Crítico  
**Criterios considerados:** Frecuencia, Impacto y Persistencia  
**Prototipo inspeccionado:** CaféU ([enlace Figma Make](https://false-wired-67481015.figma.site) / [`prototipos/prototipo.html`](../prototipos/prototipo.html))  
**Fecha de evaluación:** Noviembre de 2026  

---

## 1. Resultados de la inspección individual (10 heurísticas de Nielsen)

| # | Heurística de Nielsen | ¿Cumple? | Qué se observó en el prototipo CaféU | Severidad (1–4) | Justificación técnica (Frecuencia / Impacto / Persistencia) |
|---|---|---|---|---|---|
| **1** | **Visibilidad del estado del sistema** | **No** | Al agregar un producto desde la pantalla de detalle, la notificación flotante (*toast*) `"Producto agregado al pedido"` aparece animada pero desfasada en el marco móvil (390 px) y dura poco tiempo. Si el usuario no mira abajo en ese instante exacto, no percibe si el clic fue registrado. Además, el contador `"7 productos"` en el catálogo no se actualiza al filtrar por categoría (`"Comida"` sigue mostrando 7 en el encabezado general). | **3 (Mayor)** | **Alta frecuencia:** Sucede en cada producto agregado al carrito. **Impacto:** Genera incertidumbre, obligando al usuario a desplazarse a `"Mi pedido"` para comprobar si se agregó. **Persistencia:** Constante a lo largo de toda la sesión de compra. |
| **2** | **Coincidencia entre el sistema y el mundo real** | **Parcial** | En la pantalla de inicio, el horario de atención se presenta como `"7:00 – 19:00"`. Aunque comprensible para universitarios, el formato de 24 horas requiere una conversión mental innecesaria frente al estándar cotidiano `"7:00 a. m. – 7:00 p. m."`. El vocabulario general del menú es adecuado. | **2 (Menor)** | **Frecuencia media:** Visible solo al inicio. **Impacto bajo:** Produce una vacilación momentánea de 2 a 3 segundos, pero no bloquea la comprensión ni la tarea. |
| **3** | **Control y libertad del usuario** | **No** | En la vista de `"Mi pedido"`, al presionar el botón `"Quitar"`, el producto se elimina inmediatamente del listado sin opción de **Deshacer** (*Undo*) ni mensaje de recuperación temporal. Si el usuario se equivocó o pulsó sin querer en móvil, pierde la configuración y debe volver a buscarlo. | **3 (Mayor)** | **Impacto alto:** En pedidos con múltiples ítems o productos personalizados, un borrado accidental obliga a rehacer el flujo completo de navegación y selección. |
| **4** | **Consistencia y estándares** | **No** | Existen inconsistencias de navegación y estilo: los botones para regresar cambian de texto según la pantalla (`"Menú"`, `"Seguir comprando"` y `"Volver al menú"`). Asimismo, el botón principal `"Agregar al pedido"` utiliza fondo café oscuro (`#402a25`), mientras que las llamadas a la acción (*CTA*) primarias en Inicio y Carrito (`"Ver menú"`, `"Confirmar pedido"`) usan color terracota/naranja (`#d94716`). | **2 (Menor)** | **Frecuencia alta:** Ocurre en todas las pantallas. **Impacto moderado:** Causa leves desorientaciones visuales, pero el usuario se adapta y completa la navegación. |
| **5** | **Prevención de errores** | **No** | El botón `"Quitar"` en `"Mi pedido"` es una acción destructiva irreversible inmediata. No existe diálogo de confirmación (`"¿Seguro que deseas eliminar este producto?"`), ni mecanismo táctil de protección (como requerir doble toque o confirmación deslizante) para evitar toques accidentales en pantallas móviles reducidas. | **3 (Mayor)** | **Impacto crítico preventivo:** El diseño induce al error accidental por cercanía física a otros elementos del pedido, sin barrera de contención. |
| **6** | **Reconocer antes que recordar** | **No** | En la pantalla de detalle de producto, el selector numérico de cantidad (`− / +`) posee un tamaño reducido y bajo contraste cromático frente al fondo crema, pasando desapercibido. Como resultado, los usuarios tienden a pulsar dos o tres veces el botón grande `"Agregar al pedido"` creyendo que esa es la forma de añadir más unidades. | **3 (Mayor)** | **Frecuencia alta en pedidos múltiples:** Induce a errores no críticos que inflan el total del pedido sin que el usuario lo note de inmediato en la pantalla de producto. |
| **7** | **Flexibilidad y eficiencia de uso** | **No** | El motor de búsqueda del catálogo es de coincidencia estricta con tildes: si el usuario escribe `"sanduche"` (sin tilde), el sistema devuelve 0 resultados con el mensaje `"No encontramos productos"`, a pesar de existir `"Sánduche de queso"`. En dispositivos móviles la mayoría de estudiantes escribe sin acentos ortográficos. | **3 (Mayor)** | **Alta frecuencia e impacto:** Invalida el atajo de búsqueda rápida para usuarios ágiles, obligándolos a recurrir a la navegación por categorías o adivinar la acentuación exacta. |
| **8** | **Diseño estético y minimalista** | **Parcial** | El diseño visual general es limpio y moderno; no obstante, ciertos textos informativos secundarios (contador de ítems, etiquetas de categorías y horario) usan tamaños de fuente de 10 a 11 px, lo cual compromete la legibilidad en pantallas pequeñas bajo condiciones de iluminación variable en el campus. | **1 (Cosmético)** | **Impacto mínimo:** No impide la consecución de las metas operativas; se resuelve con ajustes de espaciado y tipografía base (mínimo 12–14 px). |
| **9** | **Ayudar a reconocer, diagnosticar y recuperarse de errores** | **Sí** | Cuando una búsqueda no arroja resultados (ej. al escribir `"pizza"`), la interfaz despliega una ilustración clara con el mensaje explicativo `"No encontramos productos"` y un botón visible y funcional `"Limpiar búsqueda"` que restablece el catálogo completo en un solo toque. | **0 (Sin problema)** | **Cumple el principio:** Diagnóstico explícito sin códigos técnicos y acción de recuperación inmediata en pantalla. |
| **10** | **Ayuda y documentación** | **No** | La aplicación no especifica en ninguna sección operativa aspectos clave del servicio: ¿cuáles son los métodos de pago aceptados (efectivo, deuna, tarjeta)?, ¿cuál es el tiempo estimado de preparación del pedido?, ni ¿en qué ventanilla o punto físico de la cafetería universitaria se retira el pedido `#CU-104`? | **2 (Menor)** | **Impacto de contexto:** Aunque la simulación web se completa técnicamente, deja vacíos operativos indispensables para el despliegue en un entorno universitario real. |

---

## 2. Síntesis de hallazgos individuales de E4 para la triangulación

1. **HE-01 (Severidad 3 - Mayor):** Búsqueda estricta insensible a tildes (`"sanduche"` sin resultados).
2. **HE-02 (Severidad 3 - Mayor):** Acción destructiva `"Quitar"` sin diálogo de confirmación ni opción `"Deshacer"`.
3. **HE-03 (Severidad 3 - Mayor):** Notificación toast `"Producto agregado"` desfasada en 390 px con visibilidad efímera.
4. **HE-04 (Severidad 3 - Mayor):** Selector de cantidad (`− / +`) con bajo contraste visual y tamaño táctil deficiente.
5. **HE-05 (Severidad 2 - Menor):** Inconsistencia en etiquetas de navegación de retorno y colores de botones principales.
6. **HE-06 (Severidad 2 - Menor):** Omisión de información sobre modalidades de pago, tiempo de preparación y punto físico de retiro.
7. **HE-07 (Severidad 2 - Menor):** Formato horario de 24 horas (`7:00 – 19:00`) que requiere conversión cognitiva.
8. **HE-08 (Severidad 1 - Cosmético):** Textos secundarios con tamaño de fuente menor a 12 px (10–11 px).
