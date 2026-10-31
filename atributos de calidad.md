# Atributos de calidad (ISO 25010)

## Priorización de los 9 atributos de primer nivel

1. Usabilidad
2. Fiabilidad
3. Adecuación funcional
4. Mantenibilidad
5. Eficiencia de Desempeño
6. Compatibilidad
7. Seguridad
8. Portabilidad
9. Flexibilidad

## Métricas de los 3 atributos más importantes

### Usabilidad
- **Métrica:** Tiempo de ejecución de la tarea principal y tasa de finalización sin asistencia.
- **Cómo se mide:** Se cuantifica el tiempo que le toma a un operario en terreno buscar una torre en el sistema y completar su respectivo checklist desde un dispositivo móvil. Dado el contexto industrial de la fábrica, la interfaz debe minimizar la carga cognitiva y evitar flujos complejos. El criterio de éxito es que la tarea completa tome menos de 3 minutos y que el 95% de los trabajadores logre finalizarla sin requerir manuales ni asistencia de terceros.

### Fiabilidad
- **Métrica:** Porcentaje de disponibilidad (Uptime) durante el horario operativo de la fábrica.
- **Cómo se mide:** Se calcula mediante herramientas de monitoreo conectadas al entorno de producción de los contenedores. La meta es mantener un 99.9% de uptime durante los turnos de trabajo. Este atributo es crítico para el negocio: si el sistema pierde disponibilidad, no se puede emitir el PDF de la Guía de Despacho, lo que detiene físicamente la salida de los camiones y genera un cuello de botella logístico.

### Adecuación funcional
- **Métrica:** Tasa de exactitud en la validación de la regla de negocio de despacho.
- **Cómo se mide:** Se evalúa la proporción entre las Guías de Despacho (PDF) generadas y las torres que efectivamente tienen su checklist registrado al 100% en la base de datos. El sistema tiene la responsabilidad de bloquear lógicamente el botón de exportación si falta la verificación de al menos un panel. La métrica se audita contrastando los documentos generados contra los logs transaccionales. El nivel de aceptación exigido es del 100% (cero falsos positivos).
