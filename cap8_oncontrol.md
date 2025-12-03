<div id='8.1.'><h3>8.1. Experiment Planning</h3></div>
<div id='8.1.1.'><h4>8.1.1. As-Is Summary</h4></div>
El proyecto OnControl corresponde a un sistema funcional de gestión de citas médicas que permite la interacción entre pacientes, doctores y organizaciones de salud. El sistema actualmente se encuentra operativo e integra funcionalidades esenciales para la administración de citas y el seguimiento post-consulta.

<br><br>
 
**Estado Actual del Sistema:**

El sistema dispone de las siguientes características y funcionalidades principales:

- Gestión completa de citas médicas, incluyendo creación, consulta, actualización y cancelación.

- Manejo de distintos estados de cita, tales como: SCHEDULED, CONFIRMED, CANCELLED y COMPLETED.

- Implementación de un sistema de seguimiento con registro de notas post-consulta por parte del personal médico.

- Autenticación basada en roles, diferenciando entre ORGANIZATION, DOCTOR y PATIENT.

- Definición de tipos de cita, entre los cuales se incluyen: PRIMERA_CONSULTA, CONSULTA_SEGUIMIENTO y REVISION_TRATAMIENTO.

<br>

**Métricas Actuales:**

En la etapa actual del proyecto, se dispone de las siguientes métricas operativas preliminares:

- Tasa de creación exitosa de citas: 95%, con base en pruebas internas.

- Tiempo promedio de respuesta del sistema: inferior a 2 segundos.

- Tasa de cancelación de citas: no registrada.

- Uso de recordatorios automáticos: funcional, pero sin métricas de desempeño asociadas.

- Adherencia a seguimientos médicos: sin datos disponibles.

<br>

**Problemas Identificados:**

Durante la evaluación del estado actual, se han identificado las siguientes limitaciones y áreas de mejora:

- Ausencia de métricas que permitan conocer la tasa real de cancelación de citas por parte de los usuarios.

- Falta de información sobre si los pacientes consultan o leen las instrucciones de preparación previas a la cita.

- No se dispone de indicadores de efectividad de los recordatorios automáticos.

- Carencia de datos que permitan determinar cuáles son los horarios más solicitados o con mayor demanda.


En síntesis, aunque el sistema presenta una base funcional sólida y métricas positivas en cuanto al rendimiento técnico, aún carece de información analítica que permita evaluar de manera integral la experiencia del usuario y la eficiencia de los procesos administrativos y clínicos.

<div id='8.1.2.'><h4>8.1.2. Raw Material: Assumptions, Knowledge Gaps, Ideas, Claims</h4></div>

La materia prima de este proyecto comprende el conjunto de suposiciones, vacíos de conocimiento, ideas y afirmaciones de los stakeholders que servirán como base para el diseño experimental y la propuesta de mejora del sistema MedSystem.
Esta información permite orientar el proceso de análisis hacia una comprensión más profunda del comportamiento de los usuarios, las necesidades del personal médico y los posibles puntos de optimización dentro del flujo operativo del sistema de gestión de citas médicas.

#### Suposiciones (Assumptions)

En esta etapa del proyecto, se han identificado diversas suposiciones basadas en observaciones iniciales, conocimiento empírico del dominio médico y retroalimentación preliminar de usuarios:

- **Preferencia horaria de los pacientes:** Se asume que la mayoría de los pacientes prefieren agendar citas durante la mañana, entre las 8:00 a.m. y 12:00 p.m., debido a la conveniencia y menor interferencia con sus actividades diarias.

- **Efectividad de los recordatorios:** Se considera que el envío de recordatorios automáticos reduce en aproximadamente un 30% la tasa de no-show (inasistencias).

- **Impacto de las instrucciones de preparación:** Se presupone que el hecho de que los pacientes lean y sigan las instrucciones previas a la cita mejora significativamente la eficiencia y calidad de las consultas médicas, al permitir un mejor uso del tiempo disponible.

- **Duración ideal de las citas:** Los doctores manifiestan preferencia por citas de 30 minutos para primeras consultas, considerando que este tiempo es adecuado para la evaluación inicial del paciente.

- **Motivos de cancelación:** Se infiere que la principal causa de cancelación por parte de los pacientes está relacionada con conflictos de horario o cambios imprevistos en su agenda personal.

Estas suposiciones funcionan como hipótesis preliminares que deben ser verificadas mediante la recolección y el análisis de datos reales durante las fases experimentales del proyecto.

##### Vacíos de Conocimiento (Knowledge Gaps)

A pesar del funcionamiento operativo del sistema, existen varios aspectos del comportamiento de los usuarios y del rendimiento del sistema que aún no han sido medidos ni comprendidos en su totalidad. Entre los vacíos de conocimiento más relevantes se identifican los siguientes:

**Tasa real de inasistencias:** No se dispone de métricas precisas que indiquen el porcentaje de citas donde los pacientes no se presentan (no-show).

**Momento de cancelación:** Se desconoce con exactitud cuánto tiempo antes de la cita los pacientes tienden a cancelar, lo cual dificulta la implementación de estrategias efectivas de reasignación.

**Interacción con notas de seguimiento:** No se sabe si los pacientes leen o consultan las notas médicas posteriores a la cita, lo que limita la evaluación del impacto de la comunicación post-consulta.

**Demanda por especialidad:** Falta información sobre qué especialidades médicas presentan mayor demanda o concentración de citas.

**Reprogramaciones vs. cancelaciones:** No hay datos que permitan distinguir qué porcentaje de citas canceladas son posteriormente reprogramadas frente a las que se pierden definitivamente.

**Eficacia de canales de recordatorio:** Se desconoce si los recordatorios por correo electrónico son más efectivos que las notificaciones in-app, lo que podría influir en la estrategia de comunicación del sistema.

La identificación de estos vacíos de conocimiento orientará los experimentos futuros hacia la recolección de evidencia empírica que permita validar o refutar las suposiciones iniciales.

#### Ideas Propuestas

Con base en el análisis del estado actual y las suposiciones anteriores, se proponen las siguientes ideas de mejora para futuras iteraciones del sistema:

- Confirmación automática 24 horas antes de la cita, que permita reducir el no-show y facilitar la planificación del personal médico.

- Implementación de un sistema de calificación post-consulta, donde los pacientes puedan evaluar su experiencia y la atención recibida, generando indicadores de calidad.

- Funcionalidad de reprogramación directa, que evite la necesidad de cancelar completamente una cita, facilitando la gestión de cambios en la agenda.

- Sugerencia automática de horarios alternativos, cuando el horario preferido por el paciente no esté disponible, para optimizar la ocupación de los espacios de atención.

- Panel estadístico (dashboard) para doctores, con indicadores clave como número de citas atendidas, canceladas o reprogramadas, y nivel de cumplimiento de seguimiento.

- Sistema de lista de espera inteligente, que permita reasignar automáticamente los espacios liberados por cancelaciones recientes a otros pacientes interesados.

- Estas ideas servirán como insumo para el diseño experimental y la evaluación de nuevas funcionalidades orientadas a la eficiencia operativa y a la satisfacción del usuario.

#### Afirmaciones de los Stakeholders (Claims)

Durante la recopilación de información con los principales actores involucrados (pacientes, doctores y administradores del sistema), se registraron las siguientes afirmaciones que reflejan percepciones, frustraciones y expectativas sobre el sistema:

“Los pacientes abandonan el proceso si toma más de tres pasos.”
- Indica la necesidad de optimizar la usabilidad y reducir la fricción en el flujo de reserva de citas.

“Las citas de seguimiento deberían ser más cortas (15-20 minutos).”
- Sugiere una revisión de la configuración de duración predeterminada de los distintos tipos de cita.

“Necesitamos recordatorios 48h y 24h antes.”
- Señala la importancia de ajustar la frecuencia y el momento del envío de notificaciones para maximizar su efectividad.

“Los doctores pierden tiempo con pacientes que no traen exámenes previos.”
- Evidencia la necesidad de reforzar las instrucciones previas y los mecanismos de confirmación de preparación del paciente.

<div id='8.1.3.'><h4>8.1.3. Experiment-Ready Questions</h4></div>

Esta sección presenta un conjunto de preguntas experimentales priorizadas, formuladas para guiar las próximas iteraciones de diseño y validación dentro del sistema MedSystem. Cada pregunta está orientada a evaluar el impacto de cambios específicos en la experiencia del usuario, la eficiencia operativa y el comportamiento de los actores del sistema.
Estas preguntas se derivan de los vacíos de conocimiento previamente identificados y de las oportunidades de mejora detectadas en el estado actual del sistema.

---

1. Confirmación de Citas

Pregunta:
¿La implementación de una confirmación obligatoria 24 horas antes de la cita reducirá el no-show en citas de primera consulta en al menos un 20%?

Objetivo del experimento:
Evaluar si exigir que el paciente confirme activamente su asistencia permite disminuir la tasa de inasistencias, especialmente en citas iniciales donde la incertidumbre es mayor.

Impacto esperado:
Reducción significativa de espacios de atención desperdiciados y mejora en la planificación diaria de los doctores.

---

2. Proceso de Agendamiento

Pregunta:
¿Reducir los pasos del proceso de creación de citas de 4 a 2 incrementará la tasa de completación del agendamiento por parte de usuarios móviles?

Objetivo del experimento:
Determinar si un proceso más rápido y simplificado disminuye la fricción y el abandono, sobre todo en dispositivos móviles donde la interacción es más sensible a la complejidad.

Impacto esperado:
Aumento measurable en el número de agendamientos completados y mejora en la experiencia de usuario móvil.

---

3. Recordatorios

Pregunta:
¿Enviar recordatorios 48 horas antes en comparación con 24 horas antes tendrá un impacto en la tasa de cancelaciones anticipadas y reducirá proporcionalmente el no-show?

Objetivo del experimento:
Identificar el momento óptimo para enviar notificaciones que permitan al paciente reorganizar su agenda sin caer en inasistencias de último minuto.

Impacto esperado:
Mejor redistribución de espacios liberados, mayor oportunidad de reasignación y disminución del no-show.

---

4. Instrucciones de Preparación

Pregunta:
¿Presentar las instrucciones de preparación mediante un popup de confirmación aumentará el nivel de cumplimiento en primera consulta?

Objetivo del experimento:
Verificar si incrementar la visibilidad de las instrucciones favorece que los pacientes lleguen preparados, especialmente cuando requieren pruebas, documentos o ayunos previos.

Impacto esperado:
Menor tiempo perdido en consultas, mayor eficiencia y mejora en la percepción de calidad por parte del personal médico.

---

5. Duración de Citas

Pregunta:
¿Ofrecer bloques de 20 minutos para consultas de seguimiento incrementará la percepción de disponibilidad por parte de los pacientes en un 30%?

Objetivo del experimento:
Explorar si ajustar la duración de consultas de seguimiento genera más opciones horarias y facilita el acceso a citas próximas.

Impacto esperado:
Mayor flexibilidad, aumento en la satisfacción de los pacientes y optimización de la agenda médica.

---

6. Reprogramación

Pregunta:
¿Permitir la reprogramación directa (sin cancelar y crear una nueva cita) reducirá el abandono del proceso en un 40%?

Objetivo del experimento:
Determinar si simplificar el flujo de cambio de horarios disminuye la frustración del usuario y evita pérdidas innecesarias en el ciclo de atención.

Impacto esperado:
Incremento en la retención de pacientes, reducción del número de citas perdidas y mejora en la continuidad de atención.

<div id='8.1.4.'><h4>8.1.4. Question Backlog</h4></div>

| # | Pregunta                                                                                 | Impacto | Costo | Riesgo | Prioridad |
|---|------------------------------------------------------------------------------------------|---------|-------|--------|-----------|
| 1 | ¿La confirmación obligatoria 24h reducirá el no-show en un 20%?                          | Alto    | Medio | Bajo   | 1         |
| 2 | ¿Reducir los pasos de 4 a 2 aumentará la completación del agendamiento móvil?            | Alto    | Bajo  | Bajo   | 2         |
| 3 | ¿La reprogramación directa reducirá el abandono del proceso en un 40%?                   | Alto    | Medio | Medio  | 3         |
| 4 | ¿Un popup con instrucciones de preparación mejorará el cumplimiento de los pacientes?    | Medio   | Bajo  | Bajo   | 4         |
| 5 | ¿Ofrecer slots de 20 minutos aumentará la disponibilidad percibida en un 30%?            | Medio   | Alto  | Medio  | 5         |
| 6 | ¿Enviar recordatorios 48h vs 24h impactará en la tasa de cancelación anticipada?         | Medio   | Bajo  | Bajo   | 6         |


Este Question Backlog resume y prioriza las preguntas de investigación que guiarán los experimentos del proyecto. Cada pregunta fue evaluada en cuatro dimensiones clave:

- **Impacto:** El potencial beneficio que tendría responder la pregunta en términos de eficiencia operativa, satisfacción del usuario o mejora del flujo de atención.

- **Costo:** El esfuerzo técnico, de diseño o de infraestructura necesario para implementar el experimento.

- **Riesgo:** La probabilidad de que el experimento no genere resultados significativos o afecte negativamente la experiencia del usuario.

- **Prioridad:** Orden resultante tras considerar los tres factores anteriores.

<div id='8.1.5.'><h4>8.1.5. Experiment Cards</h4></div>

#### CASO #1: CONFIRMACIÓN OBLIGATORIA DE CITAS:

TÍTULO: Sistema de Confirmación Obligatoria Pre-Cita

PREGUNTA: ¿Implementar confirmación obligatoria 24h antes reducirá 
el no-show en citas de primera consulta en un 20%?

CONTEXTO:
- Actualmente no tenemos datos de no-show
- Sistema envía recordatorios pero no requiere acción
- Doctores reportan pérdida de tiempo por inasistencias

TIPO DE EXPERIMENTO: A/B Test

HIPÓTESIS DETALLADA:
Creemos que requerir confirmación explícita 24h antes
Para pacientes con citas de PRIMERA_CONSULTA
Resultará en reducción de no-show del 20%
Lo sabremos cuando veamos la métrica de inasistencias
En un período de 4 semanas con 500+ citas

IMPLEMENTACIÓN:
Grupo A (Control): Sistema actual con recordatorio pasivo
Grupo B (Test): Recordatorio + botón "Confirmar asistencia" obligatorio

RECURSOS NECESARIOS:
- 1 Backend dev: 3 días (endpoint confirmación + lógica)
- 1 Frontend dev: 2 días (UI confirmación)
- 1 QA: 1 día (testing)
- Total: 1.5 semanas

CRITERIO DE ÉXITO:
- Reducción ≥ 20% en tasa de no-show
- No aumento en tasa de cancelación
- ≥ 80% de usuarios confirman sin fricción

MÉTRICAS:
Primaria: % de no-show
Secundarias: % confirmación, tiempo para confirmar, tasa cancelación
Guardrail: Satisfacción del usuario, quejas


---

#### CASO #2: SIMPLIFICACIÓN DE PROCESO DE AGENDAMIENTO

TÍTULO: Reducción de Pasos en Creación de Citas

PREGUNTA: ¿Reducir el proceso de agendamiento de 4 a 2 pasos 
aumentará la tasa de completación en usuarios móviles?

CONTEXTO:
- Proceso actual: Seleccionar doctor → Fecha → Tipo → Confirmar
- Stakeholders afirman que es muy largo para móviles
- No tenemos datos de abandono por paso

TIPO DE EXPERIMENTO: A/B Test + Analytics

HIPÓTESIS:
Creemos que reducir el flujo de creación de citas a 2 pasos
Para usuarios accediendo desde dispositivos móviles
Resultará en aumento del 25% en tasa de completación
Lo sabremos cuando veamos las métricas de funnel
En 3 semanas con 300+ intentos

IMPLEMENTACIÓN:
Grupo A: 4 pasos actuales
Grupo B: 2 pasos (Doctor+Fecha → Confirmar con tipo auto-detectado)

RECURSOS:
- 1 UX Designer: 2 días
- 1 Frontend dev: 3 días
- 1 Backend dev: 1 día (ajustes API)
- Total: 1 semana

CRITERIO DE ÉXITO:
- Aumento ≥ 25% en completación móvil
- Tiempo promedio de agendamiento < 90 segundos
- No aumento en errores de validación

MÉTRICAS:
Primaria: Tasa de completación del funnel
Secundarias: Tiempo por paso, tasa de abandono por paso, errores
Guardrail: Calidad de datos, citas incorrectas


<div id='8.2.'><h3>8.2. Experiment Design</h3></div>
<div id='8.2.1.'><h4>8.2.1. Hypotheses</h4></div>

#### HIPOTESIS #1: CONFIRMACIÓN DE CITAS

**CREEMOS QUE:**
Implementar un sistema de confirmación obligatoria 24 horas antes de la cita

**PARA:**
Pacientes con citas tipo PRIMERA_CONSULTA y CONSULTA_SEGUIMIENTO

**RESULTARÁ EN:**
- Reducción del 20% en la tasa de no-show
- Aumento del 15% en cancelaciones anticipadas (positivo)
- Mejor utilización del tiempo de los doctores

**LO SABREMOS CUANDO VEAMOS:**
- Tasa de no-show disminuir de baseline actual a -20%
- % de citas confirmadas ≥ 85%
- Tiempo promedio entre cancelación y fecha de cita aumentar
- NPS de doctores aumentar ≥ 10 puntos

**CONDICIONES:**
- Período de medición: 4 semanas
- Muestra mínima: 500 citas
- Significancia estadística: 95%
- Plataformas: Web y Móvil

**SUPOSICIONES CRÍTICAS:**
✓ Los usuarios revisan notificaciones 24h antes
✓ El proceso de confirmación toma < 30 segundos
✓ No genera fricción excesiva que aumente cancelaciones totales


---

#### HIPOTESIS #2: REPROGRAMACIÓN DIRECTA

**CREEMOS QUE:**
Agregar funcionalidad de reprogramación directa sin necesidad de cancelar primero

**PARA:**
Todos los usuarios que necesitan cambiar fecha de cita existente

**RESULTARÁ EN:**
- Reducción del 40% en abandono del proceso de cambio
- Aumento del 25% en citas reprogramadas vs canceladas definitivamente
- Mejora en satisfacción del usuario

**LO SABREMOS CUANDO VEAMOS:**
- Tasa de abandono en flujo de cambio < 20% (vs ~60% actual estimado)
- Ratio reprogramación/cancelación aumentar de 0.3 a 0.8
- Tiempo para reprogramar < 2 minutos
- CSAT post-reprogramación ≥ 4.5/5

**CONDICIONES:**
- Período: 3 semanas
- Muestra: 200+ intentos de cambio
- Tipos de cita: Todas
- Disponibilidad: Solo si hay slots en +/- 3 días

**RIESGOS:**
⚠ Podría aumentar cambios frívolos si es muy fácil
⚠ Complejidad técnica con sincronización de disponibilidad


<div id='8.2.2.'><h4>8.2.2. Domain Business Metrics</h4></div>


Las siguientes métricas representan los indicadores clave para evaluar el rendimiento, eficiencia y calidad del sistema MedSystem desde una perspectiva de negocio. Estas métricas permitirán monitorear el comportamiento del sistema, identificar oportunidades de mejora y medir el impacto de futuras iteraciones.

---

### Métricas de Eficiencia Operacional

#### 1. Utilización de Agenda
- **Descripción:** Mide el porcentaje de ocupación de los slots disponibles para citas médicas.  
- **Target:** > 85%  
- **Fórmula:**  
  `(Citas confirmadas / Total slots) * 100`

---

#### 2. Tasa de No-Show
- **Descripción:** Porcentaje de pacientes que no asisten a su cita sin cancelarla previamente.  
- **Target:** < 10%  
- **Fórmula:**  
  `(No-shows / Total citas programadas) * 100`

---

#### 3. Tiempo de Inactividad
- **Descripción:** Minutos o tiempo total perdido por cancelaciones con menos de 24 horas de anticipación.  
- **Target:** < 5% del tiempo total de agenda  
- **Fórmula:**  
  `Σ(duración de citas canceladas <24h) / Tiempo total agenda`

---

### Métricas de Experiencia del Usuario

#### 4. Tasa de Completación de Agendamiento
- **Descripción:** Porcentaje de usuarios que completan el proceso de reserva de cita.  
- **Target:** > 80%  
- **Fórmula:**  
  `(Citas creadas / Intentos iniciados) * 100`

---

#### 5. Tiempo Hasta Primera Cita
- **Descripción:** Días promedio entre el registro del usuario y su primera consulta médica.  
- **Target:** < 7 días  
- **Fórmula:**  
  `AVG(fecha_cita - fecha_registro)`

---

#### 6. Net Promoter Score (NPS)
- **Descripción:** Mide la satisfacción general y la probabilidad de que los usuarios recomienden el sistema.  
- **Target:** > 50  
- **Segmentos:** Pacientes y doctores de forma independiente.  

---

### Métricas de Engagement

#### 7. Tasa de Reprogramación
- **Descripción:** Porcentaje de citas reprogramadas en comparación con las canceladas.  
- **Target:** > 60%  
- **Fórmula:**  
  `(Reprogramaciones / (Reprogramaciones + Cancelaciones)) * 100`

---

#### 8. Adherencia a Seguimientos
- **Descripción:** Porcentaje de pacientes que agendan la consulta de seguimiento recomendada por su médico.  
- **Target:** > 70%  
- **Fórmula:**  
  `(Seguimientos agendados / Seguimientos recomendados) * 100`

---

#### 9. Uso de Notas de Preparación
- **Descripción:** Porcentaje de pacientes que visualizan o confirman lectura de instrucciones previas a la consulta.  
- **Target:** > 85%  
- **Método:** Implementación de tracking de visualización.  

---

### Métricas de Calidad

#### 10. Calidad de Consultas
- **Descripción:** Calificación promedio otorgada por los pacientes al finalizar la consulta.  
- **Target:** > 4.3 / 5  
- **Desglose:** Por doctor, tipo de consulta y especialidad.  

---

#### 11. Cumplimiento de Instrucciones
- **Descripción:** Porcentaje de pacientes que llegan preparados según las indicaciones médicas.  
- **Target:** > 80%  
- **Método:** Feedback del doctor tras la cita.  

---

#### 12. Tasa de Resolución en Primera Consulta
- **Descripción:** Proporción de casos resueltos sin necesidad de consultas adicionales.  
- **Target:** > 60%  
- **Indicador:** Efectividad diagnóstica y calidad clínica.  

---

<div id='8.2.3.'><h4>8.2.3. Measures</h4></div>


Estas son las **medidas específicas** que se deben recolectar para validar cada experimento. No son métricas de negocio, sino **datos instrumentados directamente** desde los eventos, logs y estados del sistema.

---

### Experimento 1 — Confirmación Obligatoria

### Métrica Primaria
#### **No-Show Rate**
Datos necesarios:
- `appointment.status`
- Total de citas programadas
- Total de citas marcadas como `NO_SHOW`

---

### Métricas Secundarias

#### 1. **Tasa de Confirmación**
Eventos:
- `confirmation_clicked`
Campos:
- `confirmed_at`
- `reminder_sent_at`
- `confirmation_completed_at`

#### 2. **Tiempo de Respuesta a la Confirmación**
Campos:
- `timestamp_reminder`
- `timestamp_confirmation`

#### 3. **Cancelación Anticipada (>24h)**
Datos:
- `cancelled_at`
- `appointment_start_time`

#### 4. **Tiempo entre Confirmación y Cita**
Campos:
- `confirmed_at`
- `appointment_time`

---

### Guardrails

- **Total Cancellation Rate**  
  Campo: `appointment.status = CANCELLED`

- **Tasa de Completación de Confirmación**  
  Campo: `confirmed_at != NULL`

- **Support Tickets Relacionados**
  - Categorías: recordatorios, confirmación, fricción

- **Carga del Sistema**
  - Emails enviados vs entregados
  - Email open rate
  - Performance backend (<500ms)

---

### Instrumentación del Experimento

Eventos a recolectar:
- `reminder_sent`
- `reminder_opened`
- `confirmation_clicked`
- `confirmation_completed`
- `no_show_recorded`

Campos backend:
- `confirmed_at`
- `reminder_sent_at`
- `status`
- `experiment_group`

---

## Experimento 2 — Simplificación del Flujo (4 pasos → 2 pasos)

### Métrica Primaria
#### **Funnel Completion Rate**
Datos requeridos:
- Evento `funnel_started`
- Evento `appointment_created`
- Conteo de pasos completados
- Intentos totales

---

### Métricas Secundarias

#### 1. **Tiempo Total de Completación**
Eventos:
- `first_click`
- `appointment_created`
Campo:
- `total_time`

#### 2. **Abandono por Paso**
Eventos:
- `step_completed`
- `step_abandoned`
Campos:
- `step_number`
- `time_on_step`
- `reason`

#### 3. **Errores de Validación**
Datos:
- Conteo de errores
- Tipo de error por paso

#### 4. **Reintentos**
Datos:
- `session_id`
- Secuencia de eventos del usuario
- Detección de retorno tras abandono

---

### Guardrails

- **Calidad de las Citas**
  - Tipo correcto de cita
  - % cancelaciones <1h después de crear

- **Satisfacción del Usuario**
  - Encuesta post-agendamiento: “¿Fue fácil agendar?”

- **Performance del Sistema**
  - Tiempo de carga por paso <1s
  - Errores 5xx < 0.1%

---

### Instrumentación del Experimento

Eventos:
- `funnel_started`
- `step_completed`
- `step_abandoned`
- `appointment_created`

Campos:
- `variant` (A o B)
- `device`
- `timestamp`
- `time_on_step`
- `total_time`
- `corrections_made`

---

## Resumen Global de Measures

| Experimento | Métrica Primaria | Métricas Secundarias | Guardrails | Instrumentación |
|------------|------------------|-----------------------|------------|------------------|
| **Confirmación Obligatoria** | No-Show Rate | Tasa de confirmación, tiempo de respuesta, cancelación anticipada, tiempo entre confirmación y cita | Cancelaciones totales, tickets, carga del sistema | reminder_sent, confirmation_clicked, no_show_recorded |
| **Simplificación del Flujo** | Funnel Completion Rate | Tiempo total, abandono por paso, errores, reintentos | Calidad de citas, satisfacción, performance | funnel_started, step_completed, appointment_created |


<div id='8.2.4.'><h4>8.2.4. Conditions</h4></div>

Las métricas y experimentos de la plataforma OnControl se evaluarán bajo las siguientes condiciones y limitaciones contextuales:

* **Dependencia Tecnológica:** La precisión de los datos vitales está sujeta a la correcta calibración de los sensores IoT (pulsioxímetro, monitor cardíaco, termómetro) y a la conectividad estable (Bluetooth/Wi-Fi) del dispositivo móvil del paciente.

* **Contexto del Paciente:** Se debe considerar la variabilidad en la alfabetización digital y el estado físico/emocional de los pacientes oncológicos. Estos factores pueden influir directamente en la consistencia y adherencia al uso de la aplicación móvil.

* **Contexto Clínico:** La adopción de la plataforma web por parte del personal médico está condicionada por su alta carga laboral. OnControl es una herramienta de optimización y seguimiento, no un sistema de atención de emergencias.

* **Hipótesis Operativas:** Todos los experimentos se fundamentan en las hipótesis Lean UX (Sección 1.2.2.3), que asumen que el monitoreo constante y la centralización de datos (citas, signos vitales) aportan valor tangible tanto al paciente como al médico.

* **Supuestos de Adherencia:** Se asume que los pacientes utilizarán los sensores siguiendo las indicaciones para garantizar la integridad de los datos, y que el personal médico revisará las alertas generadas de forma oportuna.

<div id='8.2.5.'><h4>8.2.5. Scale Calculations and Decisions</h4></div>

Para asegurar la validez estadística de los experimentos en OnControl, todas las pruebas de hipótesis (A/B testing) se regirán por los siguientes parámetros estándar de la industria:

* **Nivel de Significancia ($\alpha$):** Se establece en **5% (0.05)**. Esto limita al 5% la probabilidad de cometer un error de Tipo I (un falso positivo), asegurando que los cambios implementados tengan una base estadística sólida.
* **Potencia Estadística ($1-\beta$):** El objetivo de potencia se fija en un mínimo de **80%**. Esto garantiza que tengamos la capacidad suficiente para detectar correctamente un efecto real si este existe, minimizando los errores de Tipo II (falsos negativos).
* **Efecto Mínimo Detectable (MDE):** Se definirá de forma específica para cada experimento (p. ej., un aumento del 10% en la adherencia al tratamiento). Este valor representa la magnitud de cambio mínima que consideraremos relevante para el negocio y la atención al paciente.

Las decisiones de implementación se basarán en los resultados de estas pruebas aplicadas a las métricas clave del proyecto:

1.  **Índice de Adherencia al Tratamiento (IAT):**
    * **Cálculo:**
        $$\text{IAT} = \frac{\text{Registros completados (medicamentos, síntomas)}}{\text{Registros programados}} \times 100$$
    * **Decisión:** Un MDE positivo y estadísticamente significativo (ej. +10%) en este índice validará las hipótesis sobre la efectividad de los recordatorios y la facilidad de uso de la app móvil.

2.  **Tasa de Sincronización de Sensores (TSS):**
    * **Cálculo:**
        $$\text{TSS} = \frac{\text{Pacientes que sincronizan datos vitales} \ge 3 \text{ veces/semana}}{\text{Total de pacientes activos con IoT}} \times 100$$
    * **Decisión:** Alcanzar la meta definida (ej. 65% de usuarios) confirmará la hipótesis de que los pacientes perciben valor y seguridad en el monitoreo constante.

3.  **Tasa de Retención de Pacientes (TRP):**
    * **Cálculo:**
        $$\text{TRP} = \frac{\text{Usuarios activos al final del período}}{\text{Usuarios activos al inicio del período}} \times 100$$
    * **Decisión:** Una alta retención validará la utilidad a largo plazo de la plataforma como herramienta de acompañamiento durante el tratamiento.

4.  **Tasa de Interacción Médica (TIM):**
    * **Cálculo:**
        $$\text{TIM} = \frac{\text{Médicos que consultan historial o datos vitales} > 1 \text{ vez/semana/paciente}}{\text{Total de médicos activos}} \times 100$$
    * **Decisión:** Validará la hipótesis de que la plataforma centralizada reduce la fricción y optimiza la organización del médico.
