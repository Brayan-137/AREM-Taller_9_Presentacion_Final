# Procedimiento de Actualización y Revisión de la Arquitectura

## Cliente
Biblioteca Pública Municipal de Cogua "Rubiel Valencia Cossio". Bibliotecaria: Ana Cecilia Pastrana Rodríguez.

## Integrantes del equipo (ARQUITECH)
- Jorge Alarcón
- Julián Aguirre
- Brayan Presiga

## Propósito de este documento

A diferencia del Plan de Implementación (que ejecuta un cambio ya decidido) y del Plan de Gobernanza (que supervisa esa ejecución), este documento cubre qué pasa **después**: cómo se mantiene la arquitectura actualizada cuando surge una necesidad de cambio nueva, una vez terminado el roadmap del curso.

## Disparadores de cambio

Liste los eventos que ameritan revisar o actualizar la arquitectura propuesta.

| Disparador | Ejemplo concreto para este cliente |
|---|---|
| Nueva regulación | |
| Cambio de proveedor tecnológico | |
| Incidente de seguridad | |
| Crecimiento inesperado de demanda | |
| Otro | |

## Proceso de cambio

Defina, paso a paso: quién puede proponer un cambio arquitectónico, quién lo evalúa, contra qué criterios (ej. objetivos estratégicos de la Ficha de Caracterización, Taller 0) y en cuánto tiempo se espera una respuesta.

## Registro de decisiones (ADR)

| Campo | ADR-001 |
|---|---|
| Título | Catalogación distribuida entre estudiantes de servicio social, primero manual y luego con la app de lotes |
| Estado | Aceptada |
| Fecha de propuesta | Semana de trabajo del Taller 7 |
| Fecha de dictamen | Una semana después, al cerrar el Taller 7 |
| Contexto | La colección tiene de 7.000 a 8.000 libros y en Koha hay de 1.100 a 1.200. Al ritmo actual (~200 libros al mes) faltan unos 9 meses para la meta de ~3.000 de noviembre. El proceso depende de una bibliotecaria con limitación de salud, apoyada por estudiantes de servicio social que dedican en promedio 5 horas semanales y catalogan de 4 a 7 libros por hora. |
| Problema | ¿Qué modelo de catalogación aumenta el ritmo sin cargar más a la bibliotecaria? |
| Decisión | Se adopta la **catalogación distribuida**: cada estudiante cataloga con su propia cuenta y la bibliotecaria valida. Se implementa en dos momentos: primero de forma manual en Koha y después con la app móvil de catalogación, cuando la integración esté habilitada. La matriz ponderada del Taller 7 le dio 4,20 con pesos 35/25/20/20. |
| Alternativas consideradas | **Catalogación asistida (3,45):** se descartó porque mantiene a la bibliotecaria en el centro del proceso y no reduce su carga en la misma medida. **Catalogación por lotes como modelo único (3,25):** se descartó como modelo principal porque depende de una integración que hoy no está habilitada. Se conserva como herramienta de la segunda etapa. |
| Consecuencias | (+) El ritmo crece con el número de estudiantes y no con las horas de la bibliotecaria, que pasa a validar y supervisar. La fase manual empieza de inmediato, sin esperar la app. (−) Con varias personas catalogando, la calidad de los registros es menos uniforme, lo que exige capacitación y revisión. La etapa con la app sigue condicionada. **Trade-off aceptado:** se sacrifica la uniformidad de un solo catalogador a cambio de velocidad. **Nota:** los pesos se validan con la bibliotecaria el 05/11. Si el peso de la carga de trabajo supera el 66,7 %, la opción por lotes supera a la asistida, pero la distribuida sigue primera. |

| Campo | ADR-002 |
|---|---|
| Título | Cuentas personales en Koha con perfil de acceso mínimo |
| Estado | Aceptada |
| Fecha de propuesta | Semana de trabajo de la matriz de riesgos (Taller 9) |
| Fecha de dictamen | Una semana después, al aprobar la matriz |
| Contexto | Hoy las personas que trabajan en Koha comparten cuentas. La matriz de riesgos lo registró como R4, con nivel 9, uno de los dos más altos. La ADR-001 suma más personas catalogando, así que el problema crece. |
| Problema | ¿Cómo dar acceso a Koha a varios estudiantes manteniendo trazabilidad y protegiendo los datos de los usuarios? |
| Decisión | Cada persona tiene una **cuenta personal** con un **perfil de catalogador** sin acceso a circulación ni a datos de usuarios. La cuenta se desactiva al terminar el servicio social. Con esto R4 se **elimina**. |
| Alternativas consideradas | **Mantener la cuenta compartida:** se descartó porque no permite saber quién modificó cada registro y expone los datos de los usuarios, incluidos menores (Ley 1581). **Una cuenta por turno o por grupo:** se descartó porque reduce el riesgo pero no lo elimina, ya que dentro del grupo tampoco se sabe quién hizo cada cambio. |
| Consecuencias | (+) Cada registro queda a nombre de quien lo creó, lo que permite revisar la calidad por persona (apoya la ADR-001). El acceso a datos personales queda limitado. (−) Crear y desactivar cuentas es una tarea nueva de administración. **Trade-off aceptado:** se sacrifica algo de agilidad y se agrega una tarea pequeña a la bibliotecaria (en tensión con P2), porque prevalecen la seguridad y la trazabilidad (P3, P4). Para mitigarlo, se usa un perfil plantilla para crear las cuentas en pocos minutos. |

## Revisión periódica completa

Indique cada cuánto se revisa toda la arquitectura contra el estado real del negocio (no solo cuando ocurre un disparador puntual).

---

_Este documento hace parte de la entrega final del Taller 9 del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
