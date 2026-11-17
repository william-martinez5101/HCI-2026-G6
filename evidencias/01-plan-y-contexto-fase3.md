# Plan de Aplicación y Análisis · APE 6, Fases 3 y 4

**Universidad Técnica de Ambato (UTA) · Ingeniería de Software · Paralelo 5A**  
**Grupo 6:** Emilio Abril, William Martínez, Manuel Cusme, Pablo Lozada y Jonathan Gamboa  
**Responsable de este documento (Paso 1):** Emilio Abril  
**Prototipo evaluado:** [CaféU](https://false-wired-67481015.figma.site) · copia local en [`prototipos/prototipo.html`](../prototipos/prototipo.html)

---

## 1. Alcance del Grupo 6 dentro del APE 6

De acuerdo con la matriz de la asignatura, el **APE 6** se divide en cuatro fases encadenadas entre el Grupo 5 y el Grupo 6 sobre el prototipo **CaféU** (APE 4 → APE 5 → APE 6):

| Fase | Contenido | Grupo responsable | Estado |
|---|---|---|---|
| **1. Planificación** | Contexto, objetivos, tareas, métricas, ética y registro | Grupo 5 | Completado |
| **2. Pilotaje** | Prueba piloto, hoja de observación y validación del protocolo | Grupo 5 | Completado |
| **3. Aplicación y análisis** | Aplicación formal de 2 métodos (5 evaluadores heurísticos con severidad 1–4 + prueba con usuarios incluyendo escenario de búsqueda/control), registro de métricas y triangulación | **Grupo 6** | **En ejecución** |
| **4. Priorización y cierre** | Matriz de hallazgos por severidad, backlog priorizado en GitHub Issues, criterios técnicos y conclusiones | **Grupo 6** | **En ejecución** |

---

## 2. Refuerzos metodológicos del Grupo 6 respecto al Grupo 5

Al revisar el cierre de las Fases 1 y 2 del Grupo 5 (`HCI-2026-G5`), se identificaron cuatro brechas que el Grupo 6 resuelve en estas Fases 3 y 4:

1. **Severidad numérica individual (1 a 4):** En el G5 los evaluadores solo respondieron *Sí/No* sin asignar severidad. En el G6 los **5 evaluadores** (`E1` a `E5`) califican cada problema de **1 (Cosmético) a 4 (Crítico)** según **Frecuencia, Impacto y Persistencia** (Nielsen, 1995).
2. **Cobertura de funciones críticas no probadas por usuarios:** En el G5 ningún participante usó el buscador ni intentó deshacer un borrado, dejando el fallo de tildes (`"sanduche"`) y `"Quitar"` sin confirmación solo como hallazgos potenciales. El G6 incorpora la **tarea T7** para comprobar empíricamente estas funciones.
3. **Triangulación completa y Matriz de Hallazgos:** Cruce sistemático entre las 5 inspecciones heurísticas y los resultados empíricos de los participantes.
4. **Backlog priorizado en GitHub Issues y Criterios Técnicos:** Traducción de cada hallazgo en un Issue trazable con prioridad, responsable y criterio de aceptación técnico.

---

## 3. Pregunta inicial y pregunta de evaluación

- **Pregunta inicial para el laboratorio:** *¿Una interfaz que funciona técnicamente puede ser una mala interfaz?*
- **Pregunta de evaluación (Fase 3):** *¿Qué severidad tienen los problemas de usabilidad del prototipo CaféU al triangular cinco evaluaciones heurísticas independientes con pruebas empíricas de usuarios, y qué mejoras prioritarias deben ejecutarse en el backlog?*

---

## 4. Roles del laboratorio de usabilidad (Exposición y Fase 3)

| Rol | Responsabilidad | Integrante asignado (Exposición) |
|---|---|---|
| **Moderador** | Lee el consentimiento y las tareas textualmente; **no ayuda ni sugiere dónde tocar** | Pablo Lozada |
| **Usuario (demostración)** | Ejecuta las tareas aplicando *Think-Aloud* (pensando en voz alta) | Manuel Cusme *(en pruebas de Fase 3: participantes externos P1–P3)* |
| **Registro de métricas** | Cronometra en vivo, registra éxito (*Sí / Con ayuda / No*), errores y SUS | Emilio Abril |
| **Observador y soporte** | Anota frases textuales, dudas, fricciones y reinicia el prototipo (F5) entre sesiones | Jonathan Gamboa |
| **Marco teórico y documentación** | Soporte documental del repositorio y conceptos HCI | William Martínez |

---

## 5. Entorno y reglas operativas de aplicación

- **Prototipo evaluado:** CaféU (versión web móvil publicada en Figma Make y respaldo local [`prototipos/prototipo.html`](../prototipos/prototipo.html) en marco de 390 × 844 px).
- **Criterio de éxito:** *Sí* (completa sin ayuda dentro del tiempo máximo), *Con ayuda* (requiere la pista textual única), *No* (abandona, no logra el estado final o supera el doble de la meta). **Solo "Sí" cuenta como éxito.**
- **Errores:** Se clasifican en **críticos** (impiden completar la tarea) y **no críticos** (el usuario se recupera por sí mismo).
- **Reinicio obligatorio:** Al finalizar cada participante, recargar con `F5` para restaurar el pedido vacío y reiniciar el contador de confirmación a `#CU-104`.
