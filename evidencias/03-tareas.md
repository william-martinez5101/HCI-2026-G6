# Tareas y Escenarios Evaluados · Fase 3 · Prototipo CaféU

**Responsable de este documento (Paso 1):** Emilio Abril  
**Prototipo:** https://false-wired-67481015.figma.site (respaldo local: [`prototipos/prototipo.html`](../prototipos/prototipo.html))

El moderador lee cada consigna **tal como está escrita**. No explica dónde tocar ni nombra botones o pantallas.

---

## 1. Matriz de tareas (T1–T6 base + T7 de refuerzo Fase 3)

| ID | Escenario que se le lee al usuario | Meta | Tiempo máx. | Criterio de éxito | Uso |
|---|---|---|---|---|---|
| **T1** | *"¿En qué horario atiende la cafetería?"* | 60 s | 2 min | Dice `"lunes a viernes, de 7:00 a 19:00"` (o `"7 a 7 entre semana"`). | Pruebas Fase 3 y exposición |
| **T2** | *"Agrega un sánduche de queso a tu pedido."* | 60 s | 2 min | `"Mi pedido"` contiene 1 Sánduche de queso. | Pruebas Fase 3 |
| **T3** | *"Agrega también dos cafés americanos."* | 60 s | 2 min | `"Mi pedido"` contiene 1 Sánduche de queso y 2 Café americano (total `$5,75`). | Pruebas Fase 3 |
| **T4** | *"Ya no quieres el sánduche. Quítalo, confirma tu pedido y dime tu número de pedido."* | 90 s | 3 min | Se muestra `"¡Pedido confirmado!"` con 2 Café americano (`$3,00`) y dice **`#CU-104`**. | Pruebas Fase 3 |
| **T5** | *"¿Cuántos productos de comida ofrece la cafetería?"* | 60 s | 2 min | Dice **`3`** (Sánduche de queso, Croissant y Empanada de pollo). | Pruebas Fase 3 y exposición |
| **T6** | *"¿Cuánto pagarías por 3 croissants?"* | 90 s | 3 min | Dice **`$5,25`**. | Pruebas Fase 3 y exposición |
| **T7** *(Refuerzo G6)* | *"Usa el buscador para encontrar un 'sanduche' escribiéndolo sin tilde, agrégalo y luego quítalo de tu pedido."* | 90 s | 3 min | Observa el comportamiento del buscador sin tilde (`"sanduche"`) y verifica si el usuario percibe o duda al usar `"Quitar"` sin confirmación ni deshacer. | Pruebas Fase 3 (cubre brecha del G5) |

---

## 2. Justificación del refuerzo T7 en la Fase 3

En el pilotaje del Grupo 5 (Fases 1 y 2), **ningún participante utilizó el buscador** (todos navegaron por los filtros de categoría) ni cometió errores al usar `"Quitar"`. Por esa razón, dos violaciones heurísticas graves detectadas por los evaluadores (`HE-5`: buscador sensible a tildes; `HE-2/HE-4`: borrado sin confirmación ni opción de deshacer) quedaron clasificadas únicamente como *problemas potenciales*.

Al incorporar **T7** en la Fase 3, el Grupo 6 somete ambas funcionalidades a prueba empírica directa para confirmar su impacto real en eficacia, errores y tiempo, y así sustentar su severidad en el Backlog.

---

## 3. Respuestas correctas y pista única permitida

| Tarea | Respuesta / Estado esperado | Ubicación en CaféU |
|---|---|---|
| **T1** | Lunes a viernes · 7:00 – 19:00 | Pantalla Inicio → recuadro `"Horario de atención"` |
| **T3** | Total `$5,75` (`2,75 + 2 × 1,50`) | Mi pedido → Total |
| **T4** | **`#CU-104`** y total **`$3,00`** | Pantalla `"¡Pedido confirmado!"` (requiere recarga previa F5) |
| **T5** | **`3`** productos | Menú → filtro `"Comida"` |
| **T6** | **`$5,25`** (`3 × $1,75`) | Menú → Croissant → cantidad `3` → `"Agregar al pedido · $5.25"` |
| **T7** | Sin resultados al escribir `"sanduche"` sin tilde; borrado inmediato sin confirmación al pulsar `"Quitar"` | Menú → Buscador; Mi pedido → `"Quitar"` |

### Pista única permitida
- **Texto exacto:** *"Vuelve a leer la tarea y revisa las opciones que tienes en pantalla."*
- **Cuándo se entrega:** Solo si el usuario la solicita explícitamente o tras **30 segundos sin avanzar**.
- **Regla:** Máximo una vez por tarea. Si la completa tras la pista, se registra como *Con ayuda* (no cuenta como éxito). Queda prohibido señalar la pantalla o nombrar botones.
