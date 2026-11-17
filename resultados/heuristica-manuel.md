# Evaluación heurística E3 — Manuel Cusme

**Prototipo:** CaféU · **Método:** diez heurísticas de Nielsen · **Escala:** 0 sin problema, 1 cosmético, 2 menor, 3 mayor, 4 crítico.  
**Criterio de evaluación:** inspección con las diez heurísticas de Nielsen y valoración de severidad según frecuencia, impacto y persistencia.

| # | Heurística | Cumplimiento | Severidad | Elemento evaluado | Justificación técnica |
|---|---|---|---:|---|---|
| 1 | Visibilidad del estado del sistema | No | 3 | Mensaje al agregar producto a 390 px | Un aviso parcialmente oculto obliga a volver al pedido para confirmar la acción. |
| 2 | Coincidencia con el mundo real | Parcial | 1 | Lectura de horario 7:00–19:00 | El formato es correcto, aunque puede exigir interpretación adicional. |
| 3 | Control y libertad del usuario | No | 3 | Borrado con «Quitar» | No se aprecia opción inmediata de deshacer; rearmar el pedido exige pasos extra. |
| 4 | Consistencia y estándares | Parcial | 2 | Etiquetas «Menú», «Seguir comprando», «Volver al menú» | Cambian los términos y estilos para acciones de navegación semejantes. |
| 5 | Prevención de errores | No | 3 | Eliminación de un producto | Un toque accidental puede quitar el producto sin confirmación. |
| 6 | Reconocimiento antes que recuerdo | Parcial | 2 | Selector de cantidad −/+ | Un control poco notorio puede generar ajustes de cantidad equivocados. |
| 7 | Flexibilidad y eficiencia | No | 3 | Búsqueda «sanduche» sin tilde | Una búsqueda literal puede omitir «Sánduche de queso» y dificultar la localización. |
| 8 | Diseño estético y minimalista | Parcial | 1 | Etiquetas de 10–11 px en móvil | La legibilidad de información secundaria puede mejorarse. |
| 9 | Reconocer y recuperarse de errores | Sí | 0 | Buscar «pizza», mensaje y «Limpiar búsqueda» | El estado vacío y la recuperación proporcionan una salida clara. |
| 10 | Ayuda y documentación | Parcial | 2 | Retiro, forma de pago, tiempo de preparación | Faltan indicaciones útiles para el uso del servicio en un contexto real. |

## Síntesis técnica

Los principales problemas registrados se concentran en la **visibilidad de la confirmación**, el **control del borrado** y la **tolerancia a tildes del buscador** (severidad 3). Se recomienda mejorar el mensaje de confirmación, incorporar una opción para deshacer eliminaciones y normalizar tildes en la búsqueda. Estos hallazgos aportan criterios para la triangulación con P1–P3 y la priorización de mejoras.
