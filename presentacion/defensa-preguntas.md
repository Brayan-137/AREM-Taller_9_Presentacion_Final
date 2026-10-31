# Preparación de la defensa — Preguntas del panel

**Equipo:** ARQUITECH · **Estado:** borrador del Punto 5 (30/10/2026). Respuestas basadas en la evidencia del proyecto, no en opinión.

## 1. La meta es ~3.000 libros en noviembre y el plan dura 6 meses. ¿Cómo cumplen?
**Evidencia:** cuenta de capacidad (plan de implementación) y R2 de la matriz de riesgos.
**Respuesta:** "Con el ritmo actual, de unos 200 libros al mes, no se llega a 3.000 en noviembre: faltan unos 1.850 libros, que equivalen a 264 a 463 horas de catalogación, y al ritmo actual tomaría unos 9 meses. Por eso proponemos acordar con la cliente hitos mensuales. Los hitos se ajustan con la línea base de libros por hora que se mide en el Quick win y se vuelven a revisar cuando Biteca o IDECUT respondan, porque la aplicación de carga por lotes es la única fase que puede multiplicar el ritmo."

## 2. Si la app de lotes es la que más reduce la carga, ¿por qué no empiezan por ella?
**Evidencia:** matriz de decisión del Taller 7 (distribuida 4,20; asistida 3,45; lotes 3,25); R9 y R10.
**Respuesta:** "La app depende de una autorización de Biteca o IDECUT que todavía no tenemos, y usar cookies de sesión sin ella sería actuar con la identidad de otro usuario. La catalogación distribuida no depende de nadie y cierra además las cuentas compartidas. No son excluyentes: el plan hace una primero y la otra después. Con los pesos propuestos gana la distribuida; los pesos se validan con la bibliotecaria el 05/11 y, si ella le da mucho más peso a la carga, el resultado puede cambiar." *(Respuesta a actualizar tras la validación de pesos.)*

## 3. ¿Qué pasa si Biteca o IDECUT no autorizan la Fase 2?
**Evidencia:** R9, R10, R13 y dependencias del plan.
**Respuesta:** "La Fase 2 no se ejecuta contra el Koha real y el resto del plan sigue igual: respaldo, lector, cuentas individuales y catalogación distribuida no dependen de esa autorización. El prototipo, construido contra una instancia de pruebas, sirve de demostración para solicitarla. Los hitos se mantienen con el ritmo sin aplicación."

## 4. Con estudiantes rotativos, ¿cómo evitan errores y duplicados?
**Evidencia:** R6; un informe reciente señaló ~80 libros con errores y al menos un duplicado.
**Respuesta:** "El problema ya existe hoy: esta semana llegó un informe con unos 80 libros con errores, y al menos uno estaba duplicado. El plan lo atiende con el lector de ISBN (menos errores de digitación), el formato corto con campos obligatorios, la búsqueda del título antes de crear un registro, una guía de catalogación y la revisión semanal de una muestra por la bibliotecaria, con un informe de errores."

## 5. ¿Cómo protegen los datos de menores si los estudiantes catalogan?
**Evidencia:** R4 y R5; Taller 5 (STRIDE) y Taller 6 (ítems 9, 11, 13 y 14); Ley 1581.
**Respuesta:** "Hoy los estudiantes usan cuentas compartidas con permisos de edición y acceso a datos de menores. El plan crea cuentas individuales con un perfil de catalogador sin acceso a usuarios ni reportes, un compromiso de confidencialidad, inducción y baja de la cuenta al terminar el servicio social. Es la fase de Corto plazo, y la elegimos pronto porque R4 es prioridad 1 y su esfuerzo es bajo."

## 6. ¿Por qué aceptan el doble registro de usuarios?
**Evidencia:** R7 (Aceptar).
**Respuesta:** "La gobernación exige usar Koha y Llave del Saber, y la migración entre ambos sistemas está fuera de alcance, por lo que el equipo no puede eliminar la causa. Aceptarlo es una decisión registrada: se monitorea con un cruce periódico por número de documento."

## 7. ¿Los pesos de la matriz están validados? ¿El perfil restringido de Koha funciona?
**Evidencia:** supuestos del Taller 7.
**Respuesta:** "Ninguno está validado todavía y lo decimos como supuesto. Los pesos se validan con la bibliotecaria el 05/11. El perfil de catalogador se prueba en el Mes 2 con una cuenta de prueba; la documentación de Koha indica que los permisos se asignan por módulo."

## 8. ¿Cuánto cuesta?
**Evidencia:** supuestos del Taller 7 (costos por cotizar).
**Respuesta:** "El diseño prioriza el bajo costo: un lector de códigos de barras (compra pequeña), un disco externo y la nube institucional de la Alcaldía; el trabajo lo hace el servicio social existente. Los valores se cotizarán antes de ejecutar."

## Pendientes
- Validar los pesos de la matriz de decisión con la bibliotecaria el jueves 05/11 (antes del ensayo del 07/11) y actualizar las respuestas 2 y 7 y el Acto 3 si cambia el resultado.
- Preguntar al profesor (31/10) si el avance ya realizado en la app cuenta para la evaluación.
- Probar el perfil de catalogador en la instancia de Koha de pruebas antes del 14/11 (refuerza la respuesta 7).
- Cotizar el lector de códigos de barras y la nube institucional.
