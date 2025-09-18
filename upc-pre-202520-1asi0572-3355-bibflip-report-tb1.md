<div align="center">
    <h3>Universidad Peruana de Ciencias Aplicadas</h3>
    <img src="https://upload.wikimedia.org/wikipedia/commons/f/fc/UPC_logo_transparente.png"></img><br>
    <strong>Ingeniería de Software - 7mo Ciclo</strong><br><br>
    <strong>Desarrollo de Soluciones IOT</strong><br>
    1ASI0572
    <br><strong>NRC 3355</strong><br>
    <br><strong>Profesor: David Carlos Vera Olivera</strong><br>
    <br><strong>Report</strong><br>
    <br><strong>BibFlip Startup</strong><br>
    <!--<strong>name startup</strong>-->
    <br><h3> Integrantes: </h3>
</div>

<div align="center">

| Member                              |    Code    |
| :---------------------------------- | :--------: |
| Aranda Vallejos, Oscar Gabriel      | U202218167 |
| Bernaola Pérez, André Arturo        | U202114192 |
| Gutierrez Garcia, Jose Eduardo      | U202221518 |
| Oliveira Paucar, Mauricio           | U201917831 |
| Pedraza Maldonado, Joaquin          | U202218514 |
| Soriano Medrano, Diego              | U202114793 |
| Velarde Luyo, Piero Alberto         | U20211A620 |

</div>

<h3 align="center">Mayo, 2025</h3>

<br><br>

<div align="justify">



## Registro de Versiones del Informe

En esta sección se resumen los avances y modificaciones realizadas durante el ciclo de vida de desarrollo del proyecto equivalente a un semestre.

<table>
  <thead>
    <tr>
      <th>Versión</th>
      <th>Fecha</th>
      <th>Autor</th>
      <th>Descripción de modificación</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1.0</td>
      <td>09/09/2025</td>
      <td>Aranda Vallejos, Oscar Gabriel</td>
      <td>Creación y estructuración del informe</td>
    </tr>
    <tr>
      <td>1.1</td>
      <td>11/09/2025</td>
      <td>Aranda Vallejos, Oscar Gabriel</td>
      <td>Desarrollo del capítulo I</td>
    </tr>
    <tr>
      <td>1.2</td>
      <td>14/09/2025</td>
      <td>Aranda Vallejos, Oscar Gabriel</td>
      <td>Desarrollo del event storming y bounded context canvas</td>
    </tr>
    <tr>
      <td>1.3</td>
      <td>15/09/2025</td>
      <td>Bernaola Pérez, André Arturo</td>
      <td>Desarrollo del diagrama de clases y de base de datos</td>
    </tr>
    <tr>
      <td>1.4</td>
      <td>15/09/2025</td>
      <td>Aranda Vallejos, Oscar Gabriel</td>
      <td>Cierre del capítulo I y Competidores</td>
    </tr>
    <tr>
      <td>1.5</td>
      <td>15/09/2025</td>
      <td>Soriano Medrano, Diego</td>
      <td>Desarrollo de los Domain Message Flows Modeling y del Context Mapping</td>
    </tr>
    <tr>
      <td>1.6</td>
      <td>16/09/2025</td>
      <td>Pedraza Maldonado, Joaquin</td>
      <td>Desarrollo y cierre del capítulo III</td>
    </tr>
    <tr>
      <td>1.7</td>
      <td>16/09/2025</td>
      <td>Gutierrez Garcia, Jose Eduardo</td>
      <td>Desarrollo de Software Architecture</td>
    </tr>
    <tr>
      <td>1.8</td>
      <td>16/09/2025</td>
      <td>Oliveira Paucar, Mauricio</td>
      <td>Desarrollo de Tactical-Level Domain-Driven Design</td>
    </tr>
    <tr>
      <td>1.9</td>
      <td>17/09/2025</td>
      <td>Velarde Luyo, Piero Alberto  </td>
      <td>Desarrollo del Needfinding</td>
    </tr>
    <tr>
      <td>2.0</td>
      <td>18/09/2025</td>
      <td>Aranda Vallejos, Oscar Gabriel</td>
      <td>Cierre de los capítulos II y IV</td>
    </tr>
  </tbody>
</table>
<br>


# Project Report Collaboration Insights

<br>Se utilizaron Git y Github como herramientas fundamentales para el versionamiento y gestión del proyecto, lo cual permite una mejor colaboración y visualización de cambios en tiempo real. A continuación, se proporcionan los siguientes enlaces del proyecto:

| **Descripción**            | **Enlace**                                                                 |
| :-------------------------: | :------------------------------------------------------------------------: |
| Repositorio de la documentación    | https://github.com/upc-pre-202510-1asi0572-3355-BibFlip/Report         |
| Organización del proyecto     | https://github.com/upc-pre-202510-1asi0572-3355-BibFlip                    |

<!--LO COMPLETARE DESPUES -->

<br>

# Contenido

## Tabla de Contenidos

### [Registro de Versiones del Informe](#registro-de-versiones-del-informe)

### [Project Report Collaboration Insights](#project-report-collaboration-insights)

### [Contenido](#contenido)

### [Student Outcomes](#student-outcome)

### [Capítulo I: Introducción](#capítulo-i-introducción)
  - [1.1. Startup Profile](#11-startup-profile)
    - [1.1.1. Descripción de la Startup](#111-descripción-de-la-startup)
    - [1.1.2. Perfiles de integrantes del equipo](#112-perfiles-de-integrantes-del-equipo)
  - [1.2. Solution Profile](#12-solution-profile)
    - [1.2.1. Antecedentes y problemática](#121-antecedentes-y-problemática)
    - [1.2.2. Lean UX Process](#122-lean-ux-process)
      - [1.2.2.1. Lean UX Problem Statements](#1221-lean-ux-problem-statements)
      - [1.2.2.2. Lean UX Assumptions](#1222-lean-ux-assumptions)
          - [**Business Outcomes:**](#business-outcomes)
          - [**Users:**](#users)
          - [**User Outcomes \& Benefits:**](#user-outcomes--benefits)
          - [**Feature Assumptions:**](#feature-assumptions)
          - [**Business Assumptions:**](#business-assumptions)
          - [**User Assumptions:**](#user-assumptions)
      - [1.2.2.3. Lean UX Hypothesis Statements](#1223-lean-ux-hypothesis-statements)
      - [1.2.2.4. Lean UX Canvas](#1224-lean-ux-canvas)
  - [1.3. Segmentos objetivo](#13-segmentos-objetivo)

### [Capítulo II: Requirements Elicitation & Analysis](#capítulo-ii-requirements-elicitation--analysis)
- [2.1. Competidores](#21-competidores)
  - [2.1.1. Análisis competitivo](#211-análisis-competitivo)
  - [2.1.2. Estrategias y tácticas frente a competidores](#212-estrategias-y-tácticas-frente-a-competidores)
- [2.2. Entrevistas](#22-entrevistas)
  - [2.2.1. Diseño de entrevistas](#221-diseño-de-entrevistas)
  - [2.2.2. Registro de entrevistas](#222-registro-de-entrevistas)
  - [2.2.3. Análisis de entrevistas](#223-análisis-de-entrevistas)
- [2.3. Needfinding](#23-needfinding)
  - [2.3.1. User Personas](#231-user-personas)
  - [2.3.2. User Task Matrix](#232-user-task-matrix)
  - [2.3.3. User Journey Mapping](#233-user-journey-mapping)
  - [2.3.4. Empathy Mapping](#234-empathy-mapping)
  - [2.3.5. As-is Scenario Mapping](#235-as-is-scenario-mapping)
- [2.4. Ubiquitous Language](#24-ubiquitous-language)

### [Capítulo III: Requirements Specification](#capítulo-iii-requirements-specification)
- [3.1. To-Be Scenario Mapping](#31-to-be-scenario-mapping)
- [3.2. User Stories](#32-user-stories)
- [3.3. Impact Mapping](#33-impact-mapping)
- [3.4. Product Backlog](#34-product-backlog)

### [Capítulo IV: Solution Software Design](#capítulo-iv-solution-software-design)
- [4.1. Strategic-Level Domain-Driven Design](#41-strategic-level-domain-driven-design)
  - [4.1.1. Event Storming](#411-event-storming)
    - [4.1.1.1 Candidate Context Discovery](#4111-candidate-context-discovery)
    - [4.1.1.2 Domain Message Flows Modeling](#4112-domain-message-flows-modeling)
    - [4.1.1.3 Bounded Context Canvases](#4113-bounded-context-canvases)
  - [4.1.2. Context Mapping](#412-context-mapping)
  - [4.1.3. Software Architecture](#413-software-architecture)
    - [4.1.3.1. Software Architecture System Landscape Diagram](#4131-software-architecture-system-landscape-diagram)
    - [4.1.3.2. Software Architecture Context Level Diagrams](#4132-software-architecture-context-level-diagrams)
    - [4.1.3.3. Software Architecture Deployment Diagrams](#4133-software-architecture-deployment-diagrams)
- [4.2. Tactical-Level Domain-Driven Design](#42-tactical-level-domain-driven-design)
  - [4.2.1. Bounded Context: IAM](#421-bounded-context-iam)
    - [4.2.1.1. Domain Layer](#4211-domain-layer)
    - [4.2.1.2. Interface Layer](#4212-interface-layer)
    - [4.2.1.3. Application Layer](#4213-application-layer)
    - [4.2.1.4. Infrastructure Layer](#4214-infrastructure-layer)
    - [4.2.1.6. Bounded Context Software Architecture Component Level Diagrams](#4216-bounded-context-software-architecture-component-level-diagrams)
    - [4.2.1.7. Bounded Context Software Architecture Code Level Diagrams](#4217-bounded-context-software-architecture-code-level-diagrams)
      - [4.2.1.7.1. Bounded Context Domain Layer Class Diagrams](#42171-bounded-context-domain-layer-class-diagrams)
      - [4.2.1.7.2. Bounded Context Database Design Diagram](#42172-bounded-context-database-design-diagram)
  - [4.2.2. Bounded Context: Table Management](#422-bounded-context-table-management)
    - [4.2.2.1. Domain Layer](#4221-domain-layer)
    - [4.2.2.2. Interface Layer](#4222-interface-layer)
    - [4.2.2.3. Application Layer](#4223-application-layer)
    - [4.2.2.4. Infrastructure Layer](#4224-infrastructure-layer)
    - [4.2.2.6. Bounded Context Software Architecture Component Level Diagrams](#4226-bounded-context-software-architecture-component-level-diagrams)
    - [4.2.2.7. Bounded Context Software Architecture Code Level Diagrams](#4227-bounded-context-software-architecture-code-level-diagrams)
      - [4.2.2.7.1. Bounded Context Domain Layer Class Diagrams](#42271-bounded-context-domain-layer-class-diagrams)
      - [4.2.2.7.2. Bounded Context Database Design Diagram](#42272-bounded-context-database-design-diagram)
  - [4.2.3. Bounded Context: Branching](#423-bounded-context-branching)
    - [4.2.3.1. Domain Layer](#4231-domain-layer)
    - [4.2.3.2. Interface Layer](#4232-interface-layer)
    - [4.2.3.3. Application Layer](#4233-application-layer)
    - [4.2.3.4. Infrastructure Layer](#4234-infrastructure-layer)
    - [4.2.3.6. Bounded Context Software Architecture Component Level Diagrams](#4236-bounded-context-software-architecture-component-level-diagrams)
    - [4.2.3.7. Bounded Context Software Architecture Code Level Diagrams](#4237-bounded-context-software-architecture-code-level-diagrams)
      - [4.2.3.7.1. Bounded Context Domain Layer Class Diagrams](#42371-bounded-context-domain-layer-class-diagrams)
      - [4.2.3.7.2. Bounded Context Database Design Diagram](#42372-bounded-context-database-design-diagram)
  - [4.2.4. Bounded Context: Booking](#424-bounded-context-booking)
    - [4.2.4.1. Domain Layer](#4241-domain-layer)
    - [4.2.4.2. Interface Layer](#4242-interface-layer)
    - [4.2.4.3. Application Layer](#4243-application-layer)
    - [4.2.4.4. Infrastructure Layer](#4244-infrastructure-layer)
    - [4.2.4.6. Bounded Context Software Architecture Component Level Diagrams](#4246-bounded-context-software-architecture-component-level-diagrams)
    - [4.2.4.7. Bounded Context Software Architecture Code Level Diagrams](#4247-bounded-context-software-architecture-code-level-diagrams)
      - [4.2.4.7.1. Bounded Context Domain Layer Class Diagrams](#42471-bounded-context-domain-layer-class-diagrams)
      - [4.2.4.7.2. Bounded Context Database Design Diagram](#42472-bounded-context-database-design-diagram)
  - [4.2.5. Bounded Context: IoT Device Monitoring](#425-bounded-context-iot-device-monitoring)
  <!-- Breve Descripción nada más -->

### [Conclusiones](#conclusiones)
### [Bibliografía](#bibliografía)
### [Anexos](#anexos)

---

# Student Outcome

<!-- Yo me encargo de completar sus student outcomes muchachos -->


# Capítulo I: Introducción

## 1.1. Startup Profile

### 1.1.1. Descripción de la Startup

En el 2020, se reportaron matrículas con aproximadamente 1.3 millones de estudiantes de pregrado y 95 mil de posgrado en universidades peruanas (SUNEDU, 2022). Estos índices, a su vez, provocan una alta demanda de espacios de estudio y problemas con la disponibilidad de las bibliotecas. Un claro ejemplo de ello se puede observar en la Universidad Nacional Mayor de San Marcos. Esta institución universitaria, siendo una de las más grandes del país, cuenta con la infraestructura necesaria para poder atender 2500 estudiantes de manera simultánea (Montoro, 2024). Sin embargo, esto resulta insuficiente debido a la gran cantidad de alumnos. Este problema no está exento de instituciones privadas, ya que universidades como la UPC también han demostrado tener ciertas deficiencias con sus plataformas. Sobre ello, el 31 de marzo de 2025, estudiantes de la UPC denunciaron un colapso total durante el proceso de matrícula en su nueva plataforma conocida como Banner. Esto comenzó el 24 de marzo cuando una gran cantidad de alumnos intentaron acceder al sistema, pero múltiples fallas impidieron completar el proceso, obligando a la universidad a suspender temporalmente la matrícula y forzando a los estudiantes a hacer largas colas presenciales (Diario UNO, 2025). Esta situación logró solventarse gracias a la participación masiva de la manifestación del alumnado y la actualización continúa del sistema. No obstante, esta solución solo abarcó las principales funcionalidades de la plataforma y hasta el día de hoy mantiene algunas en espera de mejora, lo cual ocasionó que el personal universitario simplemente tuviera que adaptarse a los cambios. 

Una de estas funcionalidades que quedaron deprecadas componen el sistema de reserva de cubículos y espacios de estudio pertencientes a la biblioteca. Por ello, baje ese contexto, presentamos Bib Flip como una solución tecnológica desarrollada para mejorar la experiencia del uso de cubículos estudiantiles en universidades peruanas. Para ello, la propuesta deberá incluir una aplicación web y móvil con dispositivos IoT integrados. Además, nuestro enfoque es principalmente resolver problemas relacionados con la disponibilidad y la ocupación de cubículos universitarios en tiempo real para reducir tiempos de espera. 

Bib Flip brindará a los estudiantes la posibilidad de verificar la disponibilidad de espacios individuales y grupales, hacer reservas y revisar sus detalles. Además, ofrecerá un mapa interactivo para ubicar las sedes disponibles, así como la opción de registrar nuevos usuarios para acceder a los servicios de la aplicación. Además, contará con un panel exclusivo para que administradores seleccionados puedan gestionar los cubículos de estudio y visualizar las reservas activas, permitiendo un control actualizado del uso de cubículos, planificar la distribución de recursos de manera eficiente y optimizar la organización operativa.

Misión:
Ofrecer una solución tecnológica eficiente y accesible en la gestión de espacios de estudio para mejorar la experiencia académica y las operaciones de la biblioteca.

Visión:
Consolidarse como la principal solución digital en el Perú para la gestión de procesos en bibliotecas universitarias, promoviendo una experiencia de estudio más ordenada, ágil y satisfactoria para los estudiantes, y una gestión más eficiente para las instituciones educativas.


### 1.1.2. Perfiles de integrantes del equipo

|           Photo                        |                                                                                                                                                                                                                                                                                                    Description                                                                                                                                                                                                                                                                                                    |
| :------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| <img src="https://i.postimg.cc/6qRCcvNF/Captura-de-pantalla-2024-09-08-151747.png"> | **Aranda Vallejos, Oscar Gabriel** <br> Tengo 20 años y soy estudiante de la carrera de Ingeniería de Software, poseo conocimientos básicos en Unity, C++ y diseño web. Me considero una persona preparada y perseverante en cumplir con los objetivos del proyecto; además, siempre estoy dispuesto a aprender nuevos conceptos.            |
| [![bernaola.jpg](https://i.postimg.cc/PxhJpyCd/bernaola.jpg)](https://postimg.cc/hJycN98Y) | **Bernaola Pérez, André Arturo** <br> Estoy cursando la carrera de Ingeniería de Software, me gusta jugar videojuegos y aprender cosas nuevas en mis ratos libres. Aspiro a trabajar como desarrollador fullstack y me interesa mantenerme actualizado en nuevas tecnologías, buenas prácticas de programación y metodologías ágiles. |
| [![Josepfp.png](https://i.postimg.cc/kMYMqqvJ/Josepfp.png)](https://postimg.cc/3WpQZMqV) | **Gutierrez Garcia, José Eduardo** <br> Tengo 21 años, actualmente me encuentro cruzando mi 7mo ciclo de la carrera de ingeniería de software en la UPC. Me gusta jugar videojuegos y practicar natación, soy un gran aficionado de la tecnología y del ensamblaje de computadoras. Me considero una persona dispuesta siempre a aprender tecnologías nuevas, creativa y responsable.         |
| [![68747470733a2f2f696d6775722e636f6d2f657646596870372e706e67.png](https://i.postimg.cc/hGCC5yVG/68747470733a2f2f696d6775722e636f6d2f657646596870372e706e67.png)](https://postimg.cc/qt3XtGbf) | **Oliveira Paucar, Mauricio** <br> Me gusta mucho aprender cosas nuevas sobre mi carrera, trabajar en equipo de manera proactiva y lograr los objetivos junto a mis compañeros. Me considero una persona ambiciosa, ya que mi meta es llegar a obtener un alto cargo en una empresa que me agrade o formar mi propia empresa relacionada al software. Gracias a ello siempre podré trabajar en algo que me guste y llevar una vida cómoda. Cuento con conocimientos de C + + y HTML. |
| [![Joaquin.jpg](https://i.postimg.cc/Z5ynp32z/Joaquin.jpg)](https://postimg.cc/ZW4Jh9Jw) | **Pedraza Maldonado Joaquin** <br>  Estudio Ing. Software. Me considero que soy una persona perseverante, entusiasta en aprender cosas nuevas. Me gusta ayudar a los demás y sé trabajar en equipo. Cuento con conocimientos en lenguajes de Programación como C++, Python,CSS, JavaScript. |
| [![pierovelarde.jpg](https://i.postimg.cc/pdj5nykJ/pierovelarde.jpg)](https://postimg.cc/Y4pC5r5v) | **Velarde Luyo, Piero Alberto** <br> Soy Piero, estudio la carrera de ingeniería de software en la Universidad Peruana de Ciencias Aplicadas. Escogí esta carrera por mi facilidad en el uso de las computadoras. Asímismo, por mi interés en el funcionamiento de las anteriores mencionadas y todo respecto a la programación y las tecnologías emergentes. |


## 1.2. Solution Profile

### 1.2.1. Antecedentes y problemática

**What (¿Qué problema abordamos?)**
<br><br>La administración ineficaz de los espacios de estudio en las bibliotecas universitarias peruanas es el problema principal. Los alumnos experimentan incertidumbre con respecto a la disponibilidad de cubículos, se frustran cuando no encuentran espacios libres y deben esperar mucho tiempo. Asimismo, el sistema que las universidades suelen otorgar para la reserva de espacios de estudio conlleva un proceso lento y poco eficiente en la mayoría de situaciones.<br>

**Why (¿Por qué existe este problema?)**
<br><br>La raíz del problema surge del crecimiento exponencial de la matrícula universitaria, infraestructura insuficiente para atender la demanda real y procesos deficientes para la administración de reservas.<br>

**Where (¿Dónde ocurre el problema?)**
<br><br>El problema surge en las bibliotecas de instituciones universitarias peruanas. Para ello, nos centraremos principalmente en la sede San Miguel de la Universidad Peruana de Ciencias Aplicadas.<br>

**When (¿Cuándo se intensifica el problema?)**
<br><br>La problemática se agudiza en diferentes períodos como las semanas de entregas de trabajos parciales y finales, semanas de presentación y envío de avances académicos y en horarios con gran concurrencia de alumnos (mañana y tarde).<br>

**Who (¿Quién está afectado?)**
<br><br>Se indentifican entre los principales afectados a los estudiantes universitarios que experimentan dificultades para acceder a espacios de estudio cuando los necesitan, especialmente durante períodos altamente concurridos como en semanas de trabajos parciales y finales. En segundo lugar, también tenemos al personal de bibliotecas universitarias que enfrentan desafíos en la gestión de cubículos.<br>

**How (¿Cómo?)**
<br><br>La solución se llevará a cabo integrando sensores de medición de peso para cada asiento del cubículo, los cuales estarán vinculados por medio de una red IoT que envíe datos en tiempo real a un sistema centralizado para la gestión bibliotecaria. Además, los estudiantes podrán visualizar la disponibilidad y el personal del establecimiento podrá gestionar la ocupación de manera óptima y recibir alertas en caso de anomalías a través de una aplicación móvil y web.<br>

**How much (¿Cuánto?)**
<br><br>*¿Cuánto afecta este problema?*
<br>La gestión ineficiente de espacios de estudio genera pérdidas académicas significativas para las instituciones universitarias debido a la disminución en la satisfacción estudiantil, lo cual se traduce en una menor productividad académica por parte de los estudiantes.
<br><br>*¿Cuánto costará resolver este problema?*
<br>La problemática identificada no requiere una reestructuración completa del sistema bibliotecario universitario, sino una intervención tecnológica específica que resuelva los principales obstáculos: el acceso rápido a información de disponibilidad en tiempo real y una mejor planificación anticipada de espacios de estudio. En este sentido, la solución propuesta no busca reemplazar los procesos académicos tradicionales, sino complementarlos con herramientas digitales que permitan a las bibliotecas universitarias peruanas operar con mayor eficiencia, transparencia y satisfacción estudiantil.
<br>Por ello, el costo de implementación variará según el número de cubículos y la infraestructura tecnológica requerida para la instalación y mantenimiento de los sensores, así como el desarrollo de la plataforma digital integrada al sistema bibliotecario existente.
<br><br>*¿Cuántas personas se beneficiarán?*
<br>Esta solución beneficiará directamente a estudiantes universitarios y al personal bibliotecario, con un impacto indirecto en toda la comunidad académica. Se estima que, en bibliotecas universitarias de tamaño mediano, la implementación de esta tecnología podría mejorar la eficiencia en la asignación de espacios en un 35-45%, beneficiando diariamente a cientos de estudiantes y optimizando las labores del personal bibliotecario.


### 1.2.2. Lean UX Process

#### 1.2.2.1. Lean UX Problem Statements

**Problem Statement 1 - Personal de Bibliotecas**:
Los sistemas utilizados para la administración de cubículos en bibliotecas universitarias no aprovechan las tecnologías actuales con las que contamos y presentan deficiencias en su rendimiento. Por ello, nuestra propuesta abordará esta brecha mediante un panel de administración integral que proporcione una gestión óptima y análisis de datos en tiempo real; además, estará dirigido al personal de la sede San Miguel de la UPC.<br>

**Problem Statement 2 - Estudiantes Universitarios:**
El estado actual para la reservación de espacios de estudio en bibliotecas universitarias se compone principalmente de procesos poco eficientes. Los servicios existentes no permiten que los estudiantes puedan revisar la disponibilidad de los cubículos o realizar reservas de manera rápida y cómoda. Por ello, nuestra propuesta abordará esta brecha mediante una plataforma digital integrada con dispositivos IoT y nuestro enfoque estará dirigido a estudiantes universitarios de la sede San Miguel de la UPC<br>

#### 1.2.2.2. Lean UX Assumptions

##### **Business Outcomes:**

- Aumento del 30% en la eficiencia de utilización de cubículos en las bibliotecas que adopten la solución.
- Reducción del 80% en el tiempo promedio de búsqueda de espacios de estudio disponibles.
- Incremento del 25% en la satisfacción de los estudiantes, medido a través de encuestas de experiencia.
- Reducción del 40% en incidencias por ocupación indebida y problemas de asignación de cubículos.
- Mejora del 35% en la planificación y distribución de recursos bibliotecarios.

##### **Users:**

Los usuarios se dividen en estos segmentos:

- Personal de biblioteca: Administradores y operadores de 25 a 55 años responsables de la gestión diaria de cubículos.
- Estudiantes universitarios: Jóvenes de 17 a 35 años que buscan espacios de estudio para optimizar su rendimiento académico y reunirse en equipo.

##### **User Outcomes & Benefits:**

Personal de Biblioteca:

- Control óptimo del uso y ocupación de cubículos en tiempo real.
- Acceso a estadísticas e informes detallados que faciliten la toma de decisiones estratégicas.
- Optimización en la distribución de recursos y planificación operativa.
- Escalabilidad para el registro de nuevos cubículos en el sistema

Estudiantes:

- Información precisa y en tiempo real sobre la disponibilidad de cubículos de estudio.
- Reducción significativa de tiempos de espera y búsqueda de espacios disponibles.
- Mejora en la planificación de sesiones de estudio mediante reservas anticipadas.
- Mayor certeza y tranquilidad al acceder a espacios de estudio cuando los necesitan.

##### **Feature Assumptions:**

- Visualización en tiempo real del estado de ocupación de cubículos individuales y grupales.
- Funcionalidad de reservas digitales con confirmación automática y recordatorios.
- Mapas interactivos de ubicación de cubículos disponibles por sede universitaria.
- Panel de gestión integral para administradores con métricas de utilización.
- Sistema de notificaciones push para estudiantes y personal administrativo.
- Integración con dispositivos IoT para detección automática de ocupación.

##### **Business Assumptions:**

1. Creemos que nuestros usuarios necesitan un sistema automatizado y en tiempo real que facilite la gestión de cubículos de estudio en bibliotecas universitarias.
2. Creemos que estas necesidades se pueden satisfacer mediante la implementación de sensores IoT y el desarrollo de una plataforma digital accesible desde dispositivos móviles y computadoras.
3. El valor más importante que un cliente quiere de nuestros servicios es la capacidad de optimizar la ocupación de cubículos en tiempo real, garantizando tanto la eficiencia operativa como la satisfacción estudiantil.
4. El cliente también va obtener beneficios adicionales como la recopilación de datos para análisis de patrones de uso y planificación estratégica.
5. Vamos a obtener la mayoría de nuestros clientes mediante estrategias de marketing directo a universidades, participación en ferias educativas y colaboraciones con asociaciones universitarias.
6. Vamos a obtener ingresos mediante licencias institucionales y servicios de implementación de la solución IoT.
7. Nuestra competencia principal son los sistemas tradicionales de control manual de espacios y soluciones básicas de reserva existentes.
8. Vamos a tener ventaja frente a nuestra competencia debido a la optimización de sistemas, la integración IoT y la facilidad de uso, lo que mejora significativamente la experiencia académica.
9. El mayor riesgo del servicio es la posible resistencia institucional a la adopción de nuevas tecnologías y los costos de implementación inicial.
10. Lo resolveremos mediante demostraciones prácticas, pilotos gratuitos y estrategias de capacitación para asegurar una transición suave y adopción exitosa.

##### **User Assumptions:**

¿Quién es el usuario?<br>
Los usuarios son personal administrativo de bibliotecas encargado de la gestión operativa diaria de espacios, y estudiantes universitarios activos que requieren cubículos de estudio de manera regular.

¿Qué problemas tiene nuestro producto que resolver?<br>
El principal problema es la falta de información en tiempo real sobre la disponibilidad de cubículos de estudio, lo que genera tiempos perdidos en búsqueda, frustración por espacios no disponibles y gestión ineficiente de recursos. Nuestra solución automatiza este proceso, eliminando la incertidumbre y optimizando la experiencia académica.

¿Qué características son importantes?<br>
- Monitoreo en tiempo real de la ocupación mediante sensores de peso.
- Interfaz intuitiva y amigable en la aplicación móvil y web.
- Sistema de reservas con confirmación automática y recordatorios.
- Reportes históricos y analytics para análisis de patrones de uso.
- Integración con sistemas académicos existentes de la universidad.

¿Dónde encaja nuestro producto en su trabajo o vida?<br>
La solución se integra en la operación continua de las bibliotecas para el personal administrativo y en la rutina de estudio diaria de los estudiantes, facilitando tanto la gestión administrativa como la experiencia académica.

¿Cuándo y cómo es nuestro producto usado?<br>
El producto es utilizado continuamente durante horarios académicos, especialmente durante períodos de exámenes y alta demanda, permitiendo a las bibliotecas gestionar espacios eficientemente y a los estudiantes planificar sus sesiones de estudio.

¿Cómo debe verse nuestro producto y cómo debe comportarse?<br>
La interfaz debe ser moderna, limpia e intuitiva, con visualizaciones claras del estado de cubículos y navegación simple. El sistema debe ser rápido, confiable y accesible desde múltiples dispositivos, garantizando una experiencia fluida tanto para administradores como para estudiantes.

#### 1.2.2.3. Lean UX Hypothesis Statements

Hypothesis Statement 1:

Creemos que el personal administrativo de bibliotecas necesita una herramienta automatizada que les permita gestionar cubículos y generar reportes dinámicos en tiempo real.
Sabremos que hemos tenido éxito cuando al menos el 75% del personal administrativo informe una mejora del 30% en la eficiencia operativa y una reducción del 40% en tareas manuales de gestión.

Hypothesis Statement 2:

Creemos que los estudiantes universitarios valorarán disponer de información actualizada sobre la disponibilidad de cubículos y la capacidad de realizar reservas mediante una aplicación móvil y web.
Sabremos que hemos tenido éxito cuando el 80% de los estudiantes reporten una reducción significativa en el tiempo de búsqueda de espacios y una mejora del 25% en su satisfacción con el uso de bibliotecas.

Hypothesis Statement 3:

Creemos que la implementación de sensores IoT integrados en cubículos, que transmitan datos en tiempo real a una plataforma centralizada, facilitará la gestión automatizada de espacios y optimizará la experiencia de estudio.
Sabremos que hemos tenido éxito cuando las bibliotecas vean un incremento del 30% en la utilización efectiva de cubículos y una recuperación de la inversión en menos de 18 meses.

Hypothesis Statement 4:

Creemos que una interfaz intuitiva y amigable en la aplicación digital fomentará la adopción tanto por parte del personal administrativo como de estudiantes, simplificando el proceso de gestión y reserva de espacios.
Sabremos que hemos tenido éxito cuando el 85% de los usuarios completen tareas básicas en la aplicación sin necesidad de asistencia y mantengan un alto nivel de satisfacción en evaluaciones posteriores.

Hypothesis Statement 5:

Creemos que la funcionalidad de mapas interactivos y navegación dentro de bibliotecas mejorará significativamente la experiencia de localización de cubículos disponibles para los estudiantes.
Sabremos que hemos tenido éxito cuando el 70% de los estudiantes utilicen activamente esta funcionalidad y reporten una reducción del 60% en el tiempo necesario para localizar y acceder a sus cubículos reservados.
#### 1.2.2.4. Lean UX Canvas

[![lean-ux-canvas.jpg](https://i.postimg.cc/BngMMX5R/lean-ux-canvas.jpg)](https://postimg.cc/4YY634S1)

## 1.3. Segmentos objetivo

Para el desarrollo de nuestra propuesta, se han identificado dos segmentos objetivo principales que representan los stakeholders clave del sistema propuesto.

---

### Segmento 1: Personal de bibliotecas universitarias
Este segmento está conformado por el personal administrativo y operativo de las bibliotecas universitarias, quienes son responsables de la gestión diaria de los espacios de estudio y servicios bibliotecarios. Además, para este segmento se tomará como caso de prueba al personal de la Universidad Peruana de Ciencias Aplicadas en la sede San Miguel. Esto debido a su alta demanda como una de las mejores instituciones privadas en el Perú. 

#### Características Demográficas

- Edad: Personal adulto, entre los 25 y 55 años
- Educación: Técnica o universitaria
- Perfil: Personal con experiencia en gestión de servicios bibliotecarios y atención al usuario

#### Características Geográficas

- Ubicación: Lima, Perú


---

### Segmento 2: Estudiantes universitarios
Este segmento está compuesto por estudiantes que utilicen regularmente los espacios de estudio de las bibliotecas universitarias. Además, se tomará como caso de prueba a los estudiantes de la UPC. Esto debido a los casos recientes sobre el reporte de fallos con el nuevo sistema. 

#### Características Demográficas

- Edad: Principalmente entre los 17 y 35 años
- Educación: Estudiantes de pregrado y posgrado de diversas carreras profesionales
- Perfil: Estudiantes con familiaridad en el uso de aplicaciones móviles y sistemas digitales

#### Características Geográficas

- Ubicación: Lima, Perú

---


# Capítulo II: Requirements Elicitation & Analysis

## 2.1. Competidores

### 2.1.1. Análisis competitivo

<!-- Contenido del análisis competitivo -->

### 2.1.2. Estrategias y tácticas frente a competidores

<!-- Contenido de estrategias y tácticas frente a competidores -->

## 2.2. Entrevistas

### 2.2.1. Diseño de entrevistas

<!-- Contenido del diseño de entrevistas -->

### 2.2.2. Registro de entrevistas

<!-- Contenido del registro de entrevistas -->

### 2.2.3. Análisis de entrevistas

<!-- Contenido del análisis de entrevistas -->

## 2.3. Needfinding

### 2.3.1. User Personas

<!-- Contenido de User Personas -->

### 2.3.2. User Task Matrix

<!-- Contenido de User Task Matrix -->

### 2.3.3. User Journey Mapping

<!-- Contenido de User Journey Mapping -->

### 2.3.4. Empathy Mapping

<!-- Contenido de Empathy Mapping -->

### 2.3.5. As-is Scenario Mapping

<!-- Contenido de As-is Scenario Mapping -->

## 2.4. Ubiquitous Language

<!-- Contenido de Ubiquitous Language -->

---

# Capítulo III: Requirements Specification

## 3.1. To-Be Scenario Mapping

<!-- Contenido de To-Be Scenario Mapping -->

## 3.2. User Stories

<!-- Contenido de User Stories -->

## 3.3. Impact Mapping

<!-- Contenido de Impact Mapping -->

## 3.4. Product Backlog

<!-- Contenido de Product Backlog -->

---

# Capítulo IV: Solution Software Design

## 4.1. Strategic-Level Domain-Driven Design

### 4.1.1. Event Storming

#### 4.1.1.1 Candidate Context Discovery

<!-- Contenido de Candidate Context Discovery -->

#### 4.1.1.2 Domain Message Flows Modeling

<!-- Contenido de Domain Message Flows Modeling -->

#### 4.1.1.3 Bounded Context Canvases

<!-- Contenido de Bounded Context Canvases -->

### 4.1.2. Context Mapping

<!-- Contenido de Context Mapping -->

### 4.1.3. Software Architecture

#### 4.1.3.1. Software Architecture System Landscape Diagram

<!-- Contenido de Software Architecture System Landscape Diagram -->

#### 4.1.3.2. Software Architecture Context Level Diagrams

<!-- Contenido de Software Architecture Context Level Diagrams -->

#### 4.1.3.3. Software Architecture Deployment Diagrams

<!-- Contenido de Software Architecture Deployment Diagrams -->



## 4.2. Tactical-Level Domain-Driven Design

### 4.2.1. Bounded Context: IAM

#### 4.2.1.1. Domain Layer

<!-- Contenido del Domain Layer para IAM -->

#### 4.2.1.2. Interface Layer

<!-- Contenido del Interface Layer para IAM -->

#### 4.2.1.3. Application Layer

<!-- Contenido del Application Layer para IAM -->

#### 4.2.1.4. Infrastructure Layer

<!-- Contenido del Infrastructure Layer para IAM -->

#### 4.2.1.6. Bounded Context Software Architecture Component Level Diagrams

<!-- Contenido de los diagramas de componentes para IAM -->

#### 4.2.1.7. Bounded Context Software Architecture Code Level Diagrams

##### 4.2.1.7.1. Bounded Context Domain Layer Class Diagrams

<!-- Contenido de los diagramas de clases del Domain Layer para IAM -->

##### 4.2.1.7.2. Bounded Context Database Design Diagram

<!-- Contenido del diagrama de base de datos para IAM -->




### 4.2.2. Bounded Context: Table Management

#### 4.2.2.1. Domain Layer

<!-- Contenido del Domain Layer para Table Management -->

#### 4.2.2.2. Interface Layer

<!-- Contenido del Interface Layer para Table Management -->

#### 4.2.2.3. Application Layer

<!-- Contenido del Application Layer para Table Management -->

#### 4.2.2.4. Infrastructure Layer

<!-- Contenido del Infrastructure Layer para Table Management -->

#### 4.2.2.6. Bounded Context Software Architecture Component Level Diagrams

<!-- Contenido de los diagramas de componentes para Table Management -->

#### 4.2.2.7. Bounded Context Software Architecture Code Level Diagrams

##### 4.2.2.7.1. Bounded Context Domain Layer Class Diagrams

<!-- Contenido de los diagramas de clases del Domain Layer para Table Management -->

##### 4.2.2.7.2. Bounded Context Database Design Diagram

<!-- Contenido del diagrama de base de datos para Table Management -->




### 4.2.3. Bounded Context: Branching

#### 4.2.3.1. Domain Layer

<!-- Contenido del Domain Layer para Branching -->

#### 4.2.3.2. Interface Layer

<!-- Contenido del Interface Layer para Branching -->

#### 4.2.3.3. Application Layer

<!-- Contenido del Application Layer para Branching -->

#### 4.2.3.4. Infrastructure Layer

<!-- Contenido del Infrastructure Layer para Branching -->

#### 4.2.3.6. Bounded Context Software Architecture Component Level Diagrams

<!-- Contenido de los diagramas de componentes para Branching -->

#### 4.2.3.7. Bounded Context Software Architecture Code Level Diagrams

##### 4.2.3.7.1. Bounded Context Domain Layer Class Diagrams

<!-- Contenido de los diagramas de clases del Domain Layer para Branching -->

##### 4.2.3.7.2. Bounded Context Database Design Diagram

<!-- Contenido del diagrama de base de datos para Branching -->




### 4.2.4. Bounded Context: Booking

#### 4.2.4.1. Domain Layer

<!-- Contenido del Domain Layer para Booking -->

#### 4.2.4.2. Interface Layer

<!-- Contenido del Interface Layer para Booking -->

#### 4.2.4.3. Application Layer

<!-- Contenido del Application Layer para Booking -->

#### 4.2.4.4. Infrastructure Layer

<!-- Contenido del Infrastructure Layer para Booking -->

#### 4.2.4.6. Bounded Context Software Architecture Component Level Diagrams

<!-- Contenido de los diagramas de componentes para Booking -->

#### 4.2.4.7. Bounded Context Software Architecture Code Level Diagrams

##### 4.2.4.7.1. Bounded Context Domain Layer Class Diagrams

<!-- Contenido de los diagramas de clases del Domain Layer para Booking -->

##### 4.2.4.7.2. Bounded Context Database Design Diagram

<!-- Contenido del diagrama de base de datos para Booking -->




### 4.2.5. Bounded Context: IoT Device Monitoring
El Bounded Context de IoT Device Monitoring se encarga de manejar la interacción con los dispositivos IoT ubicados en las bibliotecas, como los sensores de peso en las sillas. Su función principal es recopilar, procesar y analizar los datos enviados por estos dispositivos para identificar en tiempo real el estado de ocupación de las mesas. Además, incluye herramientas para la configuración y supervisión de los dispositivos, garantizando su correcto funcionamiento y la precisión de los datos obtenidos.

# Conclusiones

<!-- Contenido de las conclusiones -->

---

# Bibliografía

<!-- Contenido de la bibliografía -->

Montoro, R. (2024). *Esta es la segunda biblioteca más grande del Perú y se encuentra en una prestigiosa universidad*. Infobae. https://www.infobae.com/peru/2024/12/10/esta-es-la-segunda-biblioteca-mas-grande-del-peru-y-se-encuentra-en-una-prestigiosa-universidad/

SUNEDU. (2022). *III Informe bienal sobre la realidad universitaria en el Perú*. https://repositorio.minedu.gob.pe/handle/20.500.12799/7913

---

# Anexos

### Entrevistas

Needfinding: https://upcedupe-my.sharepoint.com/:v:/g/personal/u202218167_upc_edu_pe/EbipDl3neqpBkcsL2Ewh0tIBwZL3w3QbSfnV5e7A5g833w?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=h1Nh0k

### TB1

Exposición: 