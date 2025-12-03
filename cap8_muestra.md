## 8.1. Experiment Planning

### 8.1.1. As-Is Summary
WasteTrack es una plataforma municipal para la gestión operativa de residuos sólidos, orientada a optimizar la recolección, supervisión y trazabilidad de contenedores. El sistema actualmente permite registrar contenedores, visualizar rutas, gestionar reportes ciudadanos y monitorear la recolección según el distrito. Sin embargo, existen brechas que limitan su eficiencia y adopción por parte de operadores municipales y supervisores de campo.

Problemas identificados:

* Baja visibilidad operativa: No existe un módulo avanzado de analítica que permita identificar contenedores críticos, rutas saturadas o zonas con alta generación de residuos.
* Escasez de herramientas predictivas: No se proyecta cuándo un contenedor alcanzará su capacidad máxima o cuándo fallará un sensor.
* Interacción limitada con reportes ciudadanos: Los usuarios municipales tienen dificultades para priorizar reportes según criticidad y patrón histórico.
* Carga inicial lenta: Algunos módulos presentan retrasos de 4–5 segundos sin un feedback claro, lo que afecta la experiencia de uso.

Objetivos de mejora:

* Implementar un sistema de analítica operativa que permita detectar contenedores críticos y predecir llenado.
* Reducir tiempos de carga mediante optimización de consultas y caché.
* Priorizar reportes ciudadanos mediante modelos básicos de severidad.
* Mejorar la gestión de rutas mediante visualización inteligente y patrones de saturación.
* Aumentar la adopción del sistema por parte de operadores municipales a través de una experiencia más clara y eficiente.


### 8.1.2. Raw Material: Assumptions, Knowledge Gaps, Ideas, Claims

Assumptions:

* Los administradores municipales necesitan visualizar contenedores críticos en tiempo real para mejorar la toma de decisiones.
* Los supervisores requieren predicciones simples sobre llenado para planificar rutas más eficientes.
* Los operadores móviles valoran vistas minimalistas y acciones rápidas al gestionar reportes ciudadanos.
* Los sensores IoT tienen un patrón predecible de fallas o inconsistencias.

Knowledge Gaps:

* ¿Qué métricas son más relevantes para los administradores: volumen, peso, frecuencia de llenado o alertas por sensor?
* ¿Qué factores determinan la priorización real de reportes ciudadanos?
* ¿Qué tipo de dashboards facilitan la gestión diaria de residuos por distrito?
* ¿Cómo influye la latencia o demora en la carga de la plataforma en la adopción del sistema?

Ideas:

* Implementar dashboards de contenedores críticos, tendencias de saturación y predicción de llenado.
* Añadir un panel de priorización inteligente de reportes ciudadanos basado en severidad e historial.
* Crear vistas optimizadas por distrito con métricas relevantes para la realidad de cada municipio.
* Habilitar una etapa de precarga (skeleton loading) para reducir fricción en módulos lentos.

Claims:

* Un dashboard de contenedores críticos puede reducir el tiempo de respuesta a incidencias en un 35%.
* La predicción de llenado puede optimizar rutas y disminuir desbordes en un 25%.
* La priorización inteligente de reportes ciudadanos puede reducir la resolución tardía en un 40%.
* Mejorar la experiencia de carga puede aumentar la adopción del sistema en un 20%.


### 8.1.3. Experiment-Ready Questions
Las siguientes preguntas guían la validación de hipótesis a través de experimentos iterativos. Se evaluaron mediante los criterios de Confianza, Riesgo, Impacto e Interés para determinar su relevancia estratégica.

| Pregunta                                                                           | Confianza | Riesgo | Impacto | Interés | Total |
| ---------------------------------------------------------------------------------- | --------- | ------ | ------- | ------- | ----- |
| ¿Mejorará la eficiencia operativa un dashboard de contenedores críticos?           | 7         | 3      | 9       | 8       | 27    |
| ¿Reducirá desbordes la predicción de llenado basada en datos históricos?           | 6         | 4      | 9       | 7       | 26    |
| ¿Aumentará la rapidez de gestión un módulo de priorización de reportes ciudadanos? | 7         | 3      | 8       | 7       | 25    |
| ¿Mejorará la adopción la optimización de carga mediante skeleton loading?          | 8         | 2      | 7       | 6       | 23    |
| ¿Incrementará la precisión de planificación segmentar métricas por distrito?       | 6         | 3      | 7       | 6       | 22    |


### 8.1.4. Question Backlog
El Question Backlog prioriza las preguntas experimentales más relevantes para el desarrollo estratégico de WasteTrack. Representan las incertidumbres que, al resolverse, generan mayor aprendizaje y reducen riesgos.

| # | Pregunta                                                                           | Prioridad |
| - | ---------------------------------------------------------------------------------- | --------- |
| 1 | ¿Mejorará la eficiencia operativa un dashboard de contenedores críticos?           | 2         |
| 2 | ¿Reducirá desbordes la predicción de llenado basada en datos históricos?           | 3         |
| 3 | ¿Aumentará la rapidez de gestión un módulo de priorización de reportes ciudadanos? | 4         |
| 4 | ¿Mejorará la adopción la optimización de carga mediante skeleton loading?          | 5         |


### 8.1.5. Experiment Cards

**Experimento 1: ¿Mejorará la eficiencia operativa un dashboard de contenedores críticos?**

| Componente     | Descripción                                                                                                                                                                                                                                                                                                        |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Question**   | ¿Mejorará la eficiencia operativa un dashboard de contenedores críticos?                                                                                                                                                                                                                                           |
| **Why**        | Los administradores municipales requieren identificar rápidamente contenedores con riesgo de desborde. Actualmente deben revisar múltiples vistas, lo que ralentiza la toma de decisiones. Un dashboard centralizado permitiría detectar anomalías, priorizar acciones y asignar personal de manera más eficiente. |
| **What**       | Implementar un dashboard que muestre contenedores críticos según volumen, peso, frecuencia de llenado y fallas de sensor. Incluir alertas visuales, filtros, orden por severidad y un mapa con zonas de riesgo.                                                                                                    |
| **Hypothesis** | Con este dashboard, el tiempo de respuesta ante contenedores críticos se reducirá en un 35%, mejorando la coordinación operativa entre distritos.                                                                                                                                                                  |


**Experimento 2: ¿Reducirá desbordes la predicción de llenado basada en datos históricos?**

| Componente     | Descripción                                                                                                                                                                                                                                                           |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Question**   | ¿Reducirá desbordes la predicción de llenado basada en datos históricos?                                                                                                                                                                                              |
| **Why**        | Los desbordes generan costos adicionales, quejas ciudadanas y complicaciones operativas. Las rutas actuales no consideran el ritmo real de llenado de cada contenedor. Predecir el llenado permitiría planificar recolecciones más eficientes y evitar acumulaciones. |
| **What**       | Entrenar un modelo simple (tendencias históricas o promedios móviles) que estime cuándo un contenedor alcanzará su capacidad máxima y mostrar esta predicción en el panel principal con indicadores de riesgo.                                                        |
| **Hypothesis** | La predicción reducirá los desbordes en un 25% y permitirá optimizar las rutas de recolección.                                                                                                                                                                        |


**Experimento 3: ¿Aumentará la rapidez de gestión un módulo de priorización de reportes ciudadanos?**

| Componente     | Descripción                                                                                                                                                                                                                            |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Question**   | ¿Aumentará la rapidez de gestión un módulo de priorización de reportes ciudadanos?                                                                                                                                                     |
| **Why**        | Los administradores gestionan los reportes sin un criterio claro de urgencia, lo que causa inconsistencia en los tiempos de resolución. Un sistema de priorización automática permitiría identificar casos críticos con mayor rapidez. |
| **What**       | Implementar un algoritmo básico que clasifique los reportes en Alta, Media o Baja prioridad según tipo de reporte, zona, frecuencia histórica e impacto. Mostrar las prioridades mediante colores y ordenamiento.                      |
| **Hypothesis** | La priorización reducirá en un 40% el tiempo promedio de resolución de reportes críticos.                                                                                                                                              |


**Experimento 4: ¿Mejorará la adopción la optimización de carga mediante skeleton loading?**

| Componente     | Descripción                                                                                                                                                                                                     |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Question**   | ¿Mejorará la adopción la optimización de carga mediante skeleton loading?                                                                                                                                       |
| **Why**        | Algunos módulos tardan 4–5 segundos en cargar sin feedback visual, lo que genera incertidumbre y percepción de bajo rendimiento. Skeleton loading puede mejorar la experiencia percibida y reducir la fricción. |
| **What**       | Implementar skeletons y estados de carga en los módulos de reportes ciudadanos, rutas y contenedores. Medir interacción, abandono y tiempos percibidos.                                                         |
| **Hypothesis** | La adopción del sistema aumentará un 20% debido a una experiencia más fluida y clara durante la carga.                                                                                                          |


## 8.2.  Experiment Design

### 8.2.1. Hypotheses

A continuación, se presentan las hipótesis experimentales para validar las principales suposiciones del sistema WasteTrack en relación con eficiencia operativa, confiabilidad de la información, adopción de usuarios municipales y experiencia del operario.

---

<table>
  <tr>
    <th colspan="2">Eficiencia de rutas de recolección</th>
  </tr>
  <tr>
    <th>Question</th>
    <th>¿La optimización automática de rutas basada en nivel de llenado y permanencia reducirá los costos operativos municipales?</th>
  </tr>
  <tr>
    <td>Belief</td>
    <td>Cremos que utilizar datos IoT en tiempo real permitirá reducir recorridos innecesarios y mejorar el uso de combustible y horas hombre.</td>
  </tr>
  <tr>
    <td>Hypothesis</td>
    <td>Si los administradores usan el dashboard de optimización, se reducirá en al menos un 15% el tiempo total de recolección en los puntos piloto.</td>
  </tr>
  <tr>
    <td>Null Hypothesis</td>
    <td>El uso del dashboard no generará una reducción significativa en los tiempos de recolección.</td>
  </tr>
</table>

---

<table>
  <tr>
    <th colspan="2">Confiabilidad de los datos IoT</th>
  </tr>
  <tr>
    <th>Question</th>
    <th>¿La información capturada por sensores IoT será percibida como confiable para la toma de decisiones operativas?</th>
  </tr>
  <tr>
    <td>Belief</td>
    <td>Si el sistema muestra historial, calibración y estado del sensor, los administradores confiarán más en decisiones basadas en datos.</td>
  </tr>
  <tr>
    <td>Hypothesis</td>
    <td>Mostrar indicadores de confiabilidad del sensor (porcentaje de precisión, frecuencia de lectura, estado) aumentará la percepción de confianza en un 30%.</td>
  </tr>
  <tr>
    <td>Null Hypothesis</td>
    <td>Los indicadores de confiabilidad no influirán en la percepción del usuario sobre la calidad del dato.</td>
  </tr>
</table>

---

<table>
  <tr>
    <th colspan="2">Adopción de la aplicación móvil de conductores</th>
  </tr>
  <tr>
    <th>Question</th>
    <th>¿Los conductores utilizarán de manera efectiva la app móvil para seguir rutas optimizadas durante sus recorridos?</th>
  </tr>
  <tr>
    <td>Belief</td>
    <td>Cremos que una interfaz simple con navegación paso a paso aumentará el uso diario de la app por parte de los operarios.</td>
  </tr>
  <tr>
    <td>Hypothesis</td>
    <td>Si la app móvil incluye rutas guiadas y alertas claras, al menos el 80% de los conductores la utilizará durante más del 70% de su recorrido.</td>
  </tr>
  <tr>
    <td>Null Hypothesis</td>
    <td>La funcionalidad de rutas guiadas no tendrá un impacto significativo en la adopción diaria de la app.</td>
  </tr>
</table>

---

<table>
  <tr>
    <th colspan="2">Percepción ciudadana del servicio de limpieza</th>
  </tr>
  <tr>
    <th>Question</th>
    <th>¿Ofrecer información transparente sobre la frecuencia de recolección mejora la satisfacción ciudadana?</th>
  </tr>
  <tr>
    <td>Belief</td>
    <td>Creemos que cuando los ciudadanos pueden visualizar horarios, estado de los contenedores y alertas, perciben un servicio más eficiente.</td>
  </tr>
  <tr>
    <td>Hypothesis</td>
    <td>La disponibilidad de información en la app ciudadana aumentará en 25% la percepción positiva del servicio en la zona piloto.</td>
  </tr>
  <tr>
    <td>Null Hypothesis</td>
    <td>Proveer información del servicio no influirá significativamente en la satisfacción ciudadana.</td>
  </tr>
</table>

### 8.2.2. Domain Business Metrics

Las siguientes métricas representan los indicadores oficiales del dominio de WasteTrack. Todas las hipótesis y experimentos utilizarán únicamente estas métricas para asegurar consistencia, trazabilidad y evitar vanity metrics. Cada métrica incluye su fórmula, técnica de recolección y meta asociada.

---

**1. Operational Efficiency Metrics (Eficiencia Operativa)**

**1.1. Reduction in Collection Time (RCT)**
- Fórmula: RCT = ((Tiempo_baseline - Tiempo_post) / Tiempo_baseline) * 100
- Recolección: GPS de camiones + timestamps de inicio/fin de ruta (app móvil).
- Meta: Reducción ≥ 15% en zonas piloto.

**1.2. Fuel Consumption Reduction (FCR)**
- Fórmula: FCR = ((Combustible_baseline - Combustible_post) / Combustible_baseline) * 100
- Recolección: Declaraciones municipales, sensores de odómetro, registros semanales.
- Meta: Reducción ≥ 10%.

**1.3. Route Deviation Rate (RDR)**
- Fórmula: RDR = (Desviaciones_detectadas / Rutas_planificadas) * 100
- Recolección: Comparación GPS vs ruta generada.
- Meta: ≤ 5%.

---

**2. IoT Sensor Reliability Metrics (Calidad de Datos de Sensores)**

**2.1. Sensor Uptime Rate (SUR)**
- Fórmula: SUR = (Tiempo_sensor_activo / Tiempo_total) * 100
- Recolección: Telemetría Actuator + gateway IoT.
- Meta: ≥ 95%.

**2.2. Valid Reading Rate (VRR)**
- Fórmula: VRR = (Lecturas_validas / Lecturas_totales) * 100
- Recolección: Filtros de señal, detección de outliers.
- Meta: ≥ 90%.

**2.3. Telemetry Frequency Consistency (TFC)**
- Fórmula: TFC = (Lecturas_recibidas / Lecturas_esperadas) * 100
- Recolección: Prometheus + logs de gateway.
- Meta: ≥ 85%.

---

**3. User Adoption Metrics (Adopción Operativa)**

**3.1. Driver App Adoption Rate (DAA)**
- Fórmula: DAA = (Conductores_activos / Conductores_registrados) * 100
- Recolección: Firebase Analytics + logs de sesiones.
- Meta: ≥ 80%.

**3.2. Task Completion Without Assistance (TCWA)**
- Fórmula: TCWA = (Tareas_completadas_sin_ayuda / Tareas_totales) * 100
- Recolección: Pruebas de usabilidad + formularios de feedback.
- Meta: ≥ 90%.

---

**4. Citizen Experience Metrics (Satisfacción del Servicio)**

**4.1. Citizen Satisfaction Index (CSI)**
- Fórmula: Promedio ponderado de encuestas sobre percepción del servicio (escala 1–5)
- Recolección: Encuestas antes y después del piloto.
- Meta: Aumento ≥ 25%.

**4.2. Information Transparency Score (ITS)**
- Fórmula: ITS = (Funciones_transparentes_usadas / Funciones_transparentes_disponibles) * 100  
  (Ej.: horarios, estado de contenedores, próximas rutas)
- Recolección: GA4 + logs de la app ciudadana.
- Meta: ≥ 60% de uso sostenido.

---

**5. System Stability & Performance Metrics**

**5.1. API Response Time (ART)**
- Fórmula: Promedio de latencia de los endpoints críticos (ms)
- Recolección: Prometheus + APM.
- Meta: ≤ 500 ms promedio.

**5.2. Error Rate (ER)**
- Fórmula: ER = (Errores_5xx / Requests_totales) * 100
- Recolección: Logs del backend + Grafana.
- Meta: ≤ 1%.

**5.3. Mobile Crash-Free Users (CFU)**
- Fórmula: CFU = (Usuarios_sin_crashes / Usuarios_totales) * 100
- Recolección: Firebase Crashlytics.
- Meta: ≥ 98%.

---

Estas métricas serán las únicas fuentes válidas para evaluar hipótesis, diseñar experimentos y tomar decisiones durante el desarrollo, piloto municipal y fases posteriores de adopción.

### 8.2.3. Measures

Las siguientes medidas permiten validar empíricamente cada hipótesis planteada, conectando preguntas clave con los indicadores que serán monitoreados durante el experimento.

---

Medida 1: Eficiencia de rutas de recolección

<table border="1" cellspacing="0" cellpadding="8" style="border-collapse:collapse; width:100%;">
  <tr>
    <th style="width:20%;">Question</th>
    <td>¿La optimización automática de rutas basada en nivel de llenado y permanencia reducirá los costos operativos municipales?</td>
  </tr>
  <tr>
    <th>Measure</th>
    <td>
      Comparar los tiempos reales de recolección antes y después del uso del dashboard de optimización.  
      Medir la reducción de duración de ruta, el consumo de combustible y el número de paradas innecesarias.  
      Registrar desvíos respecto a la ruta sugerida mediante GPS y compararlos contra el baseline municipal.
    </td>
  </tr>
</table>

---

Medida 2: Confiabilidad percibida de los datos IoT

<table border="1" cellspacing="0" cellpadding="8" style="border-collapse:collapse; width:100%;">
  <tr>
    <th style="width:20%;">Question</th>
    <td>¿La información capturada por sensores IoT será percibida como confiable para la toma de decisiones operativas?</td>
  </tr>
  <tr>
    <th>Measure</th>
    <td>
      Aplicar encuestas de percepción a administradores antes y después de mostrar indicadores de salud del sensor (uptime, frecuencia de lectura, precisión).  
      Medir el uso de funciones de confiabilidad (historial del sensor, verificación de lecturas).  
      Comparar el nivel de confianza reportado usando una escala Likert y el número de consultas a datos históricos.
    </td>
  </tr>
</table>

---

Medida 3: Adopción de la app móvil por parte de conductores

<table border="1" cellspacing="0" cellpadding="8" style="border-collapse:collapse; width:100%;">
  <tr>
    <th style="width:20%;">Question</th>
    <td>¿Los conductores utilizarán de manera efectiva la app móvil para seguir rutas optimizadas durante sus recorridos?</td>
  </tr>
  <tr>
    <th>Measure</th>
    <td>
      Registrar sesiones activas, duración del uso y frecuencia con la que siguen rutas sugeridas (Firebase Analytics).  
      Medir adherencia a rutas comparando rutas completadas vs. desvíos detectados por GPS.  
      Realizar pruebas de usabilidad para validar tareas completadas sin asistencia.
    </td>
  </tr>
</table>

---

Medida 4: Percepción ciudadana del servicio de limpieza

<table border="1" cellspacing="0" cellpadding="8" style="border-collapse:collapse; width:100%;">
  <tr>
    <th style="width:20%;">Question</th>
    <td>¿Ofrecer información transparente sobre horarios y estado de contenedores mejora la satisfacción ciudadana?</td>
  </tr>
  <tr>
    <th>Measure</th>
    <td>
      Realizar encuestas antes y después del piloto para medir cambios en satisfacción (escala 1–5).  
      Analizar métricas de uso en la app ciudadana: vistas de estado del contenedor, consultas a horarios y revisiones de rutas próximas (GA4).  
      Comparar zonas piloto vs. zonas sin acceso a esta información para evaluar impacto.
    </td>
  </tr>
</table>

### 8.2.4. Conditions

A continuación se definen las condiciones experimentales y de control para cada una de las hipótesis de WasteTrack. Estas condiciones orientan cómo se configurarán los pilotos y qué cambios se introducirán en cada escenario.

---

Condiciones para la hipótesis: Eficiencia de rutas de recolección

<table border="1" cellspacing="0" cellpadding="8" style="border-collapse:collapse; width:100%;">
  <tr>
    <th style="width:20%;">Question</th>
    <td>¿La optimización automática de rutas basada en nivel de llenado y permanencia reducirá los costos operativos municipales?</td>
  </tr>
  <tr>
    <th>Condición Experimental</th>
    <td>
      Las rutas se generan utilizando el algoritmo de optimización de WasteTrack.  
      Los conductores siguen las rutas sugeridas desde la app móvil durante todo el piloto.
    </td>
  </tr>
  <tr>
    <th>Condición de Control</th>
    <td>
      Las rutas se planifican mediante el esquema tradicional de la municipalidad (rutas fijas o planificación manual), sin apoyo del algoritmo de WasteTrack.  
      Los equipos no reciben instrucciones optimizadas en la app.
    </td>
  </tr>
</table>

---

Condiciones para la hipótesis: Confiabilidad percibida de los datos IoT

<table border="1" cellspacing="0" cellpadding="8" style="border-collapse:collapse; width:100%;">
  <tr>
    <th style="width:20%;">Question</th>
    <td>¿La información capturada por sensores IoT será percibida como confiable para la toma de decisiones operativas?</td>
  </tr>
  <tr>
    <th>Condición Experimental</th>
    <td>
      El dashboard muestra indicadores de confiabilidad del sensor: uptime, frecuencia de lectura, histórico, alertas de fallos y último mantenimiento.  
      Los administradores pueden revisar estos datos antes de tomar decisiones operativas.
    </td>
  </tr>
  <tr>
    <th>Condición de Control</th>
    <td>
      El dashboard solo muestra el nivel de llenado del contenedor sin indicadores de salud del sensor.  
      No se presentan métricas de calidad de datos ni alertas de fallos.
    </td>
  </tr>
</table>

---

Condiciones para la hipótesis: Adopción de la app móvil de conductores

<table border="1" cellspacing="0" cellpadding="8" style="border-collapse:collapse; width:100%;">
  <tr>
    <th style="width:20%;">Question</th>
    <td>¿Los conductores utilizarán de manera efectiva la app móvil para seguir rutas optimizadas durante sus recorridos?</td>
  </tr>
  <tr>
    <th>Condición Experimental</th>
    <td>
      La app incluye navegación guiada paso a paso, alertas de contenedores críticos y confirmación de cada parada.  
      Se realiza una capacitación inicial y se mide el uso durante la operación real.
    </td>
  </tr>
  <tr>
    <th>Condición de Control</th>
    <td>
      La app solo muestra un listado simple de puntos sin navegación guiada ni alertas.  
      Los conductores dependen de métodos tradicionales (mapas estáticos, rutas conocidas, instrucciones verbales).
    </td>
  </tr>
</table>

---

Condiciones para la hipótesis: Percepción ciudadana del servicio de limpieza

<table border="1" cellspacing="0" cellpadding="8" style="border-collapse:collapse; width:100%;">
  <tr>
    <th style="width:20%;">Question</th>
    <td>¿Ofrecer información transparente sobre horarios y estado de contenedores mejora la satisfacción del ciudadano?</td>
  </tr>
  <tr>
    <th>Condición Experimental</th>
    <td>
      En la zona piloto, los ciudadanos acceden a la app o portal donde pueden ver:  
      - horarios estimados de recolección  
      - estado de los contenedores  
      - alertas relevantes  
      La municipalidad comunica activamente este acceso.
    </td>
  </tr>
  <tr>
    <th>Condición de Control</th>
    <td>
      En la zona de control, los ciudadanos no reciben acceso a información en tiempo real ni funcionalidades adicionales de transparencia.  
      Se mantiene la comunicación tradicional existente.
    </td>
  </tr>
</table>

### 8.2.5. Scale Calculations and Decisions

Este enfoque utiliza métricas para evaluar el cumplimiento de las hipótesis en WasteTrack.  
Cada hipótesis se asocia con un indicador de éxito:

- Se considera **desfavorable** cuando el valor está por debajo del mínimo esperado.
- **Aceptable** cuando se encuentra entre el mínimo y el valor objetivo.
- **Ideal** cuando la métrica alcanza plenamente el objetivo planteado.
- **Excelente** cuando el valor supera el objetivo en un 25% o más, indicando un éxito significativo.

Este esquema permite tomar decisiones fundamentadas en métricas para validar, ajustar o escalar las hipótesis del proyecto.

<table border="1" cellspacing="0" cellpadding="8" style="border-collapse:collapse; width:100%; text-align:center;">
  <thead>
    <tr>
      <th style="width:30%;">Scale Calculation</th>
      <th style="width:30%;">Decision</th>
      <th style="width:10%;">Desfavorable</th>
      <th style="width:10%;">Aceptable</th>
      <th style="width:10%;">Ideal</th>
      <th style="width:10%;">Excelente</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left;">
        Creemos que al utilizar el algoritmo de optimización de rutas de WasteTrack, se reducirá el tiempo total de recolección (RCT) en al menos 15% y el consumo de combustible (FCR) en al menos 10% en las zonas piloto.  
        Sabremos que esto es cierto cuando los indicadores RCT y FCR se mantengan dentro o por encima de esas metas durante el piloto.
      </td>
      <td style="text-align:left;">
        Si los resultados alcanzan o superan los objetivos, se recomienda escalar el uso de WasteTrack a más rutas y distritos municipales. En caso contrario, revisar parámetros del algoritmo y la capacitación a conductores.
      </td>
      <td></td>
      <td></td>
      <td><strong>X</strong></td>
      <td></td>
    </tr>
    <tr>
      <td style="text-align:left;">
        Creemos que al mostrar indicadores de confiabilidad de sensores (SUR, VRR, TFC) los administradores percibirán los datos como más confiables y usarán con mayor frecuencia el dashboard para la toma de decisiones.  
        Sabremos que esto es cierto cuando SUR ≥ 95%, VRR ≥ 90% y aumente la frecuencia de consultas al dashboard.
      </td>
      <td style="text-align:left;">
        Si las métricas de confiabilidad se mantienen altas y la percepción de confianza mejora, se consolidará esta vista como estándar y se priorizará inversión en mantenimiento preventivo de sensores.
      </td>
      <td></td>
      <td><strong>X</strong></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td style="text-align:left;">
        Creemos que al ofrecer rutas guiadas y una app móvil simple, la tasa de adopción de conductores (DAA) será de al menos 80% y el porcentaje de rutas completadas siguiendo la optimización será mayor al 70%.  
        Sabremos que esto es cierto cuando la mayoría de conductores utilice activamente la app durante sus recorridos.
      </td>
      <td style="text-align:left;">
        Si la adopción es alta, se validará el diseño actual de la app y se podrá introducir gradualmente funcionalidades avanzadas. Si es baja, se revisarán la interfaz, la capacitación y las condiciones de uso en campo.
      </td>
      <td></td>
      <td><strong>X</strong></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td style="text-align:left;">
        Creemos que al brindar información transparente al ciudadano (estado de contenedores y horarios de recolección), el Citizen Satisfaction Index (CSI) aumentará al menos en 25% en las zonas piloto frente a la línea base.  
        Sabremos que esto es cierto cuando las encuestas de satisfacción muestren esta mejora sostenida.
      </td>
      <td style="text-align:left;">
        Si la satisfacción mejora, se recomendará integrar WasteTrack como herramienta de transparencia y comunicación estándar en el distrito, y considerar nuevas funcionalidades de participación ciudadana.
      </td>
      <td></td>
      <td></td>
      <td><strong>X</strong></td>
      <td></td>
    </tr>
  </tbody>
</table>