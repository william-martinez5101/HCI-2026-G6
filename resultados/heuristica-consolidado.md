# Consolidación de Evaluación Heurística (E1–E5) · Prototipo CaféU

**Responsable de consolidación (Paso 4):** Pablo Lozada  
**Rol:** Moderador del Laboratorio de Usabilidad / Responsable de Métricas y Triangulación  
**Evaluadores independientes:**
- **E1:** Emilio Abril (Coordinador y Cronometrista)
- **E2:** William Martínez (Soporte documental)
- **E3:** Manuel Cusme (Usuario Think-Aloud)
- **E4:** Pablo Lozada (Moderador)
- **E5:** Jonathan Gamboa (Observador y QA)

**Método:** Inspección heurística independiente con los 10 principios de Nielsen (1994) y calificación numérica de severidad de 0 a 4 (Nielsen, 1995) según **Frecuencia**, **Impacto** y **Persistencia**.  
**Fundamento metodológico:** Según Nielsen & Landauer (1993), un panel de 5 evaluadores independientes permite descubrir entre el 75 % y el 85 % de los problemas de usabilidad de una interfaz, mitigando el *efecto evaluador* (*evaluator effect*, Hertzum & Jacobsen, 2001).  
**Prototipo inspeccionado:** CaféU ([Figma Make](https://false-wired-67481015.figma.site) · [`prototipos/prototipo.html`](../prototipos/prototipo.html))  

---

## 1. Matriz comparativa de severidad individual (E1 a E5)

Escala: `0` Sin problema · `1` Cosmético · `2` Menor · `3` Mayor · `4` Crítico

| # | Heurística de Nielsen | E1 | E2 | E3 | E4 | E5 | Promedio | Mediana | Severidad Consensuada | Nivel de Coincidencia |
|---|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **H1** | Visibilidad del estado del sistema | 3 | 3 | 3 | 3 | 3 | **3.0** | 3 | **3 (Mayor)** | 100 % (5/5) |
| **H2** | Coincidencia con el mundo real | 2 | 1 | 1 | 2 | 1 | **1.4** | 1 | **1 (Cosmético)** | 100 % detectado (3/5 sev 1, 2/5 sev 2) |
| **H3** | Control y libertad del usuario | 3 | 3 | 3 | 3 | 3 | **3.0** | 3 | **3 (Mayor)** | 100 % (5/5) |
| **H4** | Consistencia y estándares | 2 | 2 | 2 | 2 | 2 | **2.0** | 2 | **2 (Menor)** | 100 % (5/5) |
| **H5** | Prevención de errores | 3 | 3 | 3 | 3 | 3 | **3.0** | 3 | **3 (Mayor)** | 100 % (5/5) |
| **H6** | Reconocer antes que recordar | 3 | 2 | 3 | 3 | 2 | **2.6** | 3 | **3 (Mayor)** | 100 % detectado (3/5 sev 3, 2/5 sev 2) |
| **H7** | Flexibilidad y eficiencia de uso | 3 | 3 | 3 | 3 | 3 | **3.0** | 3 | **3 (Mayor)** | 100 % (5/5) |
| **H8** | Diseño estético y minimalista | 1 | 1 | 1 | 1 | 1 | **1.0** | 1 | **1 (Cosmético)** | 100 % (5/5) |
| **H9** | Ayudar a reconocer y recuperarse de errores | 0 | 0 | 0 | 0 | 0 | **0.0** | 0 | **0 (Sin problema)** | 100 % (5/5) |
| **H10** | Ayuda y documentación | 2 | 2 | 2 | 2 | 2 | **2.0** | 2 | **2 (Menor)** | 100 % (5/5) |

---

## 2. Descripción técnica de los hallazgos consolidados

### Hallazgos de Severidad 3 (Problemas Mayores / Críticos para corrección inmediata)

#### HE-01: Motor de búsqueda estricto e insensible a tildes (H7)
- **Principio violado:** H7 — Flexibilidad y eficiencia de uso.
- **Severidad consensuada:** **3 (Mayor)** (Promedio: 3.0 / Mediana: 3).
- **Descripción consolidada:** Al escribir una palabra sin tilde ortográfica en el cuadro de búsqueda (ej. `"sanduche"`), el filtro de búsqueda realiza una comparación literal estricta y devuelve 0 coincidencias con el mensaje `"No encontramos productos"`, a pesar de existir `"Sánduche de queso"`.
- **Justificación (F/I/P):**
  - *Frecuencia:* Muy alta. En dispositivos móviles más del 80 % de los usuarios omite tildes por agilidad.
  - *Impacto:* Severo. Invalida la principal vía de navegación directa para usuarios que saben exactamente qué desean pedir.
  - *Persistencia:* Se repite cada vez que se busca un producto acentuado.
- **Recomendación técnica:** Implementar normalización de cadenas Unicode (`string.normalize("NFD").replace(/[\u0300-\u036f]/g, "").toLowerCase()`) previo al filtrado.

#### HE-02: Borrado destructivo inmediato sin confirmación ni función "Deshacer" (H3 y H5)
- **Principios violados:** H3 — Control y libertad del usuario; H5 — Prevención de errores.
- **Severidad consensuada:** **3 (Mayor)** (Promedio: 3.0 / Mediana: 3).
- **Descripción consolidada:** En la pantalla `"Mi pedido"`, el enlace/botón `"Quitar"` elimina el producto de la comanda de forma instantánea al pulsar, sin un diálogo de confirmación previo ni un mecanismo de recuperación (*Undo* / *Deshacer*) posterior.
- **Justificación (F/I/P):**
  - *Frecuencia:* Media-alta en dispositivos táctiles donde los toques imprecisos son habituales.
  - *Impacto:* Crítico. Destruye el trabajo de selección y personalización del usuario, obligándolo a navegar nuevamente por el catálogo.
  - *Persistencia:* Si ocurre accidentalmente durante un pedido numeroso, produce frustración extrema y riesgo de abandono.
- **Recomendación técnica:** Añadir un modal o diálogo flotante de confirmación (`"¿Eliminar producto del pedido?"`) o un toast con acción `"Deshacer"` disponible durante 5 segundos.

#### HE-03: Notificación de confirmación de adición (Toast) visualmente deficiente (H1)
- **Principio violado:** H1 — Visibilidad del estado del sistema.
- **Severidad consensuada:** **3 (Mayor)** (Promedio: 3.0 / Mediana: 3).
- **Descripción consolidada:** Al presionar `"Agregar al pedido"`, el mensaje toast inferior (`"Producto agregado al pedido"`) se anima fuera del centro óptico en la resolución de 390 px, apareciendo parcialmente desplazado hacia la derecha y con una duración muy breve. Si el usuario aparta la vista un segundo, no sabe si la acción tuvo efecto hasta que revisa el icono del carrito en el footer.
- **Justificación (F/I/P):**
  - *Frecuencia:* Muy alta. Se reproduce en cada adición de ítem al pedido.
  - *Impacto:* Moderado-alto. Induce desconfianza sobre si el sistema procesó la instrucción.
  - *Persistencia:* Presente en toda la experiencia de compra.
- **Recomendación técnica:** Centrar el componente toast (`inset-x-4` con `mx-auto`), aumentar su contraste y duración a 3.5 segundos, e incrementar una microanimación en el badge numérico del carrito.

#### HE-04: Controles de selección de cantidad (− / +) con bajo contraste y tamaño reducido (H6)
- **Principio violado:** H6 — Reconocer antes que recordar.
- **Severidad consensuada:** **3 (Mayor)** (Promedio: 2.6 / Mediana: 3).
- **Descripción consolidada:** En la ficha de detalle de producto, el botón de incremento (`+`) y decremento (`−`) tiene un tamaño menor a las pautas táctiles mínimas recomendadas (menor a 44 × 44 px) y utiliza tonos grises tenues sobre fondo crema. Los usuarios no perciben que pueden modificar la cantidad antes de agregar y tienden a oprimir el botón grande `"Agregar al pedido"` reiteradamente.
- **Justificación (F/I/P):**
  - *Frecuencia:* Alta en pedidos de 2 o más unidades de un mismo producto.
  - *Impacto:* Moderado. Provoca pedidos erróneos con cantidades no deseadas que deben corregirse después en el carrito.
- **Recomendación técnica:** Rediseñar el control de cantidad como un componente destacado con botones táctiles de al menos 44 × 44 px, borde definido y tipografía en semibold de 16 px.

---

### Hallazgos de Severidad 2 (Problemas Menores / Prioridad Media en Backlog)

#### HE-05: Inconsistencia en navegación de retorno y color del botón de acción principal (H4)
- **Principio violado:** H4 — Consistencia y estándares.
- **Severidad consensuada:** **2 (Menor)** (Promedio: 2.0 / Mediana: 2).
- **Descripción consolidada:** La aplicación utiliza tres etiquetas dispares para retroceder en la jerarquía: `"Menú"` en detalle de producto, `"Seguir comprando"` en el carrito y `"Volver al menú"` en confirmación. Asimismo, el botón primario `"Agregar al pedido"` utiliza fondo café espresso (`#402a25`), mientras que `"Ver menú"` y `"Confirmar pedido"` emplean color terracota brillante (`#d94716`).
- **Recomendación técnica:** Unificar los botones de retroceso con el patrón estándar de flecha izquierda acompañada siempre de `"Menú"`, y estandarizar el color naranja terracota para todos los botones de acción principal (CTA).

#### HE-06: Falta de información operativa sobre formas de pago, preparación y punto de retiro (H10)
- **Principio violado:** H10 — Ayuda y documentación.
- **Severidad consensuada:** **2 (Menor)** (Promedio: 2.0 / Mediana: 2).
- **Descripción consolidada:** Al generar el pedido confirmado con el código `#CU-104`, la pantalla no indica si el usuario debe pagar en caja o mediante transferencia (Deuna/Banco), cuánto tiempo aproximado tardará la orden ni en qué ventanilla física del campus se recoge.
- **Recomendación técnica:** Agregar una sección informativa en la pantalla de confirmación: tiempo estimado (ej. `"Listo en ~8 min"`), modalidades de pago aceptadas y ubicación física (`"Retira en Ventanilla 2 · Bloque A"`).

---

### Hallazgos de Severidad 1 (Problemas Cosméticos / Prioridad Baja)

#### HE-07: Formato horario de 24 horas (`7:00 – 19:00`) (H2)
- **Principio violado:** H2 — Coincidencia con el mundo real.
- **Severidad consensuada:** **1 (Cosmético)** (Promedio: 1.4 / Mediana: 1).
- **Descripción:** Notación militar que demanda conversión cognitiva menor.
- **Recomendación:** Cambiar a `"Lunes a viernes de 7:00 a. m. a 7:00 p. m."`.

#### HE-08: Tipografía de tamaño reducido (10–11 px) en etiquetas secundarias (H8)
- **Principio violado:** H8 — Diseño estético y minimalista.
- **Severidad consensuada:** **1 (Cosmético)** (Promedio: 1.0 / Mediana: 1).
- **Descripción:** Textos pequeños de categoría y etiquetas que reducen la legibilidad en pantallas de baja resolución o alta luminosidad.
- **Recomendación:** Establecer 12 px como tamaño de fuente mínimo admisible.

---

### Hallazgo sin problema (Severidad 0)

#### HE-09: Manejo adecuado de estados vacíos de búsqueda (H9)
- **Principio verificado:** H9 — Ayudar a reconocer, diagnosticar y recuperarse de errores.
- **Severidad consensuada:** **0 (Sin problema)** (Promedio: 0.0 / Mediana: 0).
- **Evaluación:** Cumple excelentemente. Muestra mensaje humanizado sin tecnicismos y botón `"Limpiar búsqueda"` que recupera el catálogo inmediatamente.

---

## 3. Síntesis y distribución de severidad para el Backlog

| Nivel de Severidad | Cantidad de Heurísticas | Códigos de Hallazgo | Acción recomendada |
|---|:---:|---|---|
| **4 (Crítico)** | 0 | — | Ninguno con severidad 4 pura en heurística individual, pero HE-01 escala a crítico al triangularse con fallos de usuarios. |
| **3 (Mayor)** | 4 | HE-01, HE-02, HE-03, HE-04 | **Prioridad Alta (Sprint inmediato de mejoras).** |
| **2 (Menor)** | 2 | HE-05, HE-06 | **Prioridad Media.** |
| **1 (Cosmético)** | 2 | HE-07, HE-08 | **Prioridad Baja (Refinamiento visual).** |
| **0 (Sin problema)** | 1 | HE-09 | Mantener patrón de diseño existente. |
| **Total evaluado** | **10** | | |
