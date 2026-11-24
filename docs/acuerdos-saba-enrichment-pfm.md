# Propuesta de acuerdos para Saba
## Integración y evolución de los dominios Enrichment y PFM

**Objetivo:** establecer responsabilidades, restricciones y compromisos de evolución entre ambos dominios, evitando duplicidad de capacidades e inversiones innecesarias.

**Estado:** propuesta pendiente de formalización.

## 1. Acuerdos de gobierno y responsabilidades

| ID | Acuerdo propuesto |
|---|---|
| AC01 | Cuentas y Tarjetas serán los únicos dominios autorizados para disponibilizar los movimientos originales. |
| AC02 | Enrichment será responsable de gobernar y disponibilizar los atributos enriquecidos de carácter transversal. |
| AC03 | PFM será responsable de las capacidades propias de finanzas personales, como insights, recomendaciones, agregaciones, dashboards y splits. |
| AC04 | Strands podrá conservar los datos originales necesarios para la operación de PFM, sujetos a las políticas de seguridad y gobierno del banco. |
| AC05 | Se restringirá el consumo de las APIs de PFM como fuente alternativa de consulta de movimientos originales. |

## 2. Acuerdos de integración

| ID | Acuerdo propuesto |
|---|---|
| AC06 | PFM continuará operando con Strands bajo su arquitectura actual. |
| AC07 | PFM publicará hacia Enrichment los tres atributos acordados: categoría, subcategoría y glosa enriquecida, incluyendo sus actualizaciones. |
| AC08 | Enrichment almacenará, gobernará y disponibilizará dichos atributos a los consumidores autorizados. |
| AC09 | PFM podrá continuar utilizando directamente los atributos generados por Strands, sin necesidad de recuperarlos desde Enrichment. |
| AC10 | Se establecerá un identificador común que permita correlacionar los movimientos originales con sus atributos enriquecidos. |

## 3. Acuerdos de evolución hacia online

| ID | Acuerdo propuesto |
|---|---|
| AC11 | Enrichment evolucionará progresivamente de procesamiento batch a procesamiento online, conforme las fuentes disponibilicen información en línea. |
| AC12 | PFM y Enrichment podrán consumir los mismos tópicos de manera independiente, siempre que atiendan responsabilidades funcionales diferentes. |
| AC13 | Las nuevas necesidades de enriquecimiento de PFM deberán evaluarse conjuntamente con Enrichment para identificar posibles solapamientos funcionales. |
| AC14 | Los datos destinados exclusivamente a potenciar las capacidades propias de PFM podrán continuar siendo procesados por PFM y Strands. |
| AC15 | Cuando PFM requiera un atributo transversal que Enrichment ya genera en batch, se priorizará evaluar su implementación online dentro de Enrichment. |
| AC16 | Enrichment disponibilizará mediante eventos los atributos online que PFM requiera consumir, evitando duplicar su generación. |
| AC17 | PFM y Enrichment deberán acordar los requisitos de latencia, disponibilidad, calidad y recuperación necesarios para garantizar la continuidad operativa. |

## 4. Acuerdos de inversión y prevención de duplicidad

| ID | Acuerdo propuesto |
|---|---|
| AC18 | Antes de contratar nuevos enriquecimientos en Strands, se evaluará si dicha capacidad existe o puede implementarse dentro de Enrichment. |
| AC19 | Se evaluará la asignación conjunta de presupuesto y recursos para acelerar la implementación de capacidades transversales online en Enrichment. |
| AC20 | Cualquier duplicidad funcional deberá contar con una justificación arquitectónica, un responsable y, cuando corresponda, una estrategia de convergencia. |

## 5. Compromisos de ejecución

| Compromiso | Responsable propuesto | Fecha |
|---|---|---|
| Formalizar el diseño de integración PFM–Enrichment | Arquitectura | Por acordar |
| Definir el contrato de los tres atributos enriquecidos | PFM / Enrichment | Por acordar |
| Identificar y migrar consumidores no autorizados de movimientos desde PFM | PFM | Por acordar |
| Presentar el alcance funcional de los nuevos tópicos que consumirá PFM | PFM | Por acordar |
| Identificar posibles solapamientos con los enriquecimientos existentes | PFM / Enrichment | Por acordar |
| Evaluar la implementación online de los atributos requeridos por PFM | Enrichment | Por acordar |
| Definir presupuesto, recursos y cronograma de evolución | Líderes de ambos dominios | Por acordar |

## 6. Posición estratégica para Saba

Se propone mantener la autonomía funcional de PFM y Enrichment, permitiendo que ambos consuman las mismas fuentes de información cuando atiendan objetivos de negocio diferentes.

Sin embargo, cuando exista una necesidad de enriquecimiento transversal compartida, se deberá priorizar la construcción de una única capacidad reutilizable, evitando duplicidad funcional, dependencia innecesaria de proveedores e inversiones redundantes.

En ese sentido, las nuevas necesidades online de PFM pueden convertirse en un habilitador para acelerar la evolución de Enrichment, mediante una estrategia conjunta de priorización, presupuesto y ejecución.

**Acuerdos prioritarios:** AC13, AC15, AC18 y AC19.

## Referencia

[Documento de arquitectura Enrichment y PFM](arquitectura-enrichment-pfm.md).
