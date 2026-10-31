# Plan de Gobernanza de la Implementación

## Cliente
Biblioteca Pública Municipal de Cogua "Rubiel Valencia Cossio". Bibliotecaria: Ana Cecilia Pastrana Rodríguez.

## Integrantes del equipo (ARQUITECH)
- Jorge Alarcón
- Julián Aguirre
- Brayan Presiga

## Propósito de este documento

_Pendiente._

## Principios Arquitectónicos

> El documento de visión del Taller 0 no incluyó un borrador de principios. Por eso los cuatro principios siguientes son nuevos y se derivan de la evidencia de los Talleres 1 a 7. No hay principios confirmados, reescritos ni retirados.

| Principio | Declaración | Implicación (qué descarta) | Justificación en el proyecto (evidencia de los talleres) | Estado frente al Taller 0 |
|---|---|---|---|---|
| **P1. Koha como fuente única del catálogo** | El registro oficial de cada ejemplar de la colección es el que está en Koha. Ninguna otra herramienta mantiene una versión válida del catálogo. | Las hojas de cálculo, los cuadernos o los formularios solo se usan como apoyo temporal de captura y no reemplazan el registro en Koha. Cualquier herramienta nueva, como la app de lotes de la Fase 2, debe escribir directamente en Koha o terminar en él. Se descarta catalogar en paralelo para "subir después". | El avance hacia la meta de ~3.000 títulos (hoy de 1.100 a 1.200, de una colección de 7.000 a 8.000) solo se puede medir y consultar si todo el catálogo está en un mismo lugar. El proceso AS-IS del Taller 1 mostró que los registros dispersos duplican el trabajo y hacen que el avance no se pueda verificar. | Nuevo |
| **P2. Primero, reducir la carga de la bibliotecaria** | Entre dos opciones que cumplen el objetivo, se elige la que exige menos esfuerzo directo a la bibliotecaria. | Una solución que le sume tareas a Ana Cecilia Pastrana se descarta o se rediseña, aunque sea técnicamente superior. El trabajo operativo se traslada a los estudiantes de servicio social o a herramientas de apoyo, y la bibliotecaria queda en el rol de validación y supervisión. | El proceso depende de una sola persona con limitaciones de salud. La carga de trabajo es su principal molestia y, por eso, el criterio de mayor peso en la matriz de decisión del Taller 7. | Nuevo |
| **P3. Cuenta propia y acceso mínimo** | Cada persona que trabaja en Koha usa una cuenta personal, con los permisos estrictamente necesarios para su tarea. | Se prohíben las cuentas compartidas, incluso para agilizar la incorporación de estudiantes. Los estudiantes de servicio social tienen un perfil de catalogador sin acceso a circulación ni a datos de usuarios, y su cuenta se desactiva al terminar el servicio. | Las cuentas compartidas de Koha (R4) son uno de los dos riesgos de mayor nivel de la matriz (nivel 9). Impiden saber quién modificó cada registro y exponen los datos de los usuarios a personas que no los necesitan. | Nuevo |
| **P4. Protección de datos desde el diseño** | Todo cambio que toque datos personales debe cumplir la Ley 1581 de 2012 antes de ponerse en operación, no después. | No se integra ningún tercero, herramienta ni formulario que no demuestre cifrado y un tratamiento adecuado de los datos. Los datos de menores de edad reciben protección reforzada. Se descartan los formularios con cuentas no institucionales y el uso de cookies de sesión sin autorización formal. | La biblioteca atiende población infantil y juvenil. La matriz de riesgos identificó los datos de menores (R5), las cookies de sesión (R10) y los terceros sin evidencia de cifrado (R12) como riesgos de nivel 6, además de las brechas del Taller 5 (WP5: G4 y G6). | Nuevo |

Principios del borrador del Taller 0 que se retiran, y por qué:

| Principio retirado | Qué evidencia lo contradijo |
|---|---|
| Ninguno | El Taller 0 no incluyó borrador de principios. |

## Estándares Tecnológicos

Cualquier excepción a estos estándares se registra y se aprueba mediante una ADR en `procedimiento-cambios.md`.

| Categoría | Estándar definido | Por qué |
|---|---|---|
| Lenguaje / framework | **Kotlin**, para la app móvil Android de catalogación por lotes. | Es el lenguaje oficial de Android. Permite usar la cámara del teléfono como lector de códigos de barras, así que los estudiantes de servicio social catalogan desde su propio celular sin equipos adicionales. Esto quita carga operativa a la bibliotecaria (P2). |
| Tipo de comunicación | **API REST oficial de Koha**, con autenticación por cuenta personal. El uso de cookies de sesión queda como excepción y solo procede con autorización escrita de IDECUT. | Es la vía soportada por Koha. Cada registro queda en Koha a nombre de quien lo creó (P1, P3). Las cookies de sesión son un riesgo identificado (R10) y no ofrecen garantías de seguridad (P4). |
| Infraestructura | **Koha alojado por Biteca**, y la app y sus datos de apoyo en la **nube institucional**. El prototipo se prueba únicamente contra el Koha de pruebas del repositorio oficial. | La biblioteca no tiene personal técnico para mantener servidores propios (P2). Ningún dato real de usuarios, incluidos menores, entra al entorno de pruebas (P4). |

## Mecanismo de gobierno

_Pendiente._

## Cadencia de seguimiento

_Pendiente._

## Criterio de conformidad

_Pendiente._

## Escalamiento

_Pendiente._

## Métricas de gobierno

_Pendiente (sesión del 31/10)._
