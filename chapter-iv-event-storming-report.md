# Capítulo IV: Solution Software Design

## 4.1. Strategic-Level Domain-Driven Design

### 4.1.1. Event Storming

Con el objetivo de comprender en profundidad el dominio del sistema, se llevó a cabo una sesión de Event Storming de aproximadamente 1 hora. Esto permitió que nosotros como equipo organizaramos nuestras ideas y pensamientos sobre sistema desde múltiples perspectivas: negocio, usuario final, administración y experiencia. A través de esta dinámica, identificamos eventos clave, comandos, usuarios y agregados que nos ayudaron a esbozar una primera visión integral del sistema.

<br>

**Se vieron los siguientes puntos en la reunión:**

- Exploración del dominio general

Se partió desde la experiencia del visitante en la landing page, avanzando por el flujo de registro e inicio de sesión como estudiante o administrador, hasta la reserva de cubiculos, visualización en tiempo real y gestión desde el panel administrativo.

- Identificación de eventos y comandos clave

Se colocaron notas naranjas para eventos, y se complementaron con comandos en azul. EL equipo seguío de las User Stories previamente realizadas, lo que aseguró la coherencia y el flujo de la solución.

<br>

- Asignación de roles y responsables

Se diferenciaron los actores como: estudiante, administrador, superadmin, visitante, para asociar claramente qué parte del sistema controlan o en qué puntos interactúan. Al dividirlo de esta manera es más fácil detectar posibles conflictos o áreas de mejora en la experiencia.<br>

#### 4.1.1.1 Candidate Context Discovery

Identificar contextos candidatos es un paso clave para gestionar la complejidad en el desarrollo de sistemas. Se trata de un análisis minucioso que busca entender los elementos centrales del sistema y sus interconexiones. A partir de ahí, se procede a agrupar estos elementos en 'contextos delimitados' lógicos y coherentes. Esta separación no solo facilita el diseño y la implementación, sino que también tiene como meta principal potenciar la escalabilidad, el desempeño y la mantenibilidad del sistema resultante.

<img src="images/Candidate-Context-Discovery/Candidate Context Discovery.png">

#### 4.1.1.2 Domain Message Flows Modeling

Para analizar y diseñar sistemas de software, se usa el Modelado de Flujos de Mensajes de Dominio, un método que ilustra la transferencia de información entre componentes mediante mensajes. Este proceso se centra en especificar los mensajes enviados y recibidos por los diferentes actores del sistema y en descifrar sus relaciones. El uso de esta metodología aporta claridad para entender y representar las vías de información del sistema, permitiendo detectar problemas potenciales más fácilmente y optimizar la estructura del diseño. A modo de ejemplo, mostraremos a continuación algunos diagramas aplicados a nuestro sistema.

<img src="images/Domain Message Flows Modeling/Domain Message Flows Modeling.jpg">

#### 4.1.1.3 Bounded Context Canvases

### Booking Management
[![booking-management-canva.jpg](https://i.postimg.cc/2SDTDHPZ/booking-management-canva.jpg)](https://postimg.cc/nC3qK1VF)

### Cubicle Management
[![cubicle-management-canva.png](https://i.postimg.cc/3Jp9zMbh/cubicle-management-canva.png)](https://postimg.cc/1fmpNdQ7)

### IoT Monitoring
<a href="https://ibb.co/MxjxwgWw"><img src="https://i.ibb.co/Txnxjwpj/Bounded-Context-Canvases-Iot-Monitoring.jpg" alt="Bounded-Context-Canvases-Iot-Monitoring" border="0"></a><br>


### Headquarter Management
<a href="https://ibb.co/HTX3nqcQ"><img src="https://i.ibb.co/ZzN7WxQC/Bounded-Context-Canvases-Headquarter-Management.jpg" alt="Bounded-Context-Canvases-Headquarter-Management" border="0"></a><br>

### 4.1.2. Context Mapping

En esta sección desarrollamos un conjunto de context maps para visualizar las relaciones entre los bounded contexts del sistema. A partir de la información recolectada, exploramos distintas alternativas de diseño, cuestionando cómo cambiaría la estructura si reubicamos, dividimos o agrupamos capabilities. Finalmente, evaluamos cada propuesta considerando patrones como Anti-corruption Layer, Conformist, Customer/Supplier y Shared Kernel, con el fin de definir la mejor aproximación para la arquitectura del dominio. A continucación presentaremos las opciones que contemplamos para el sistema y la estructura final.

**Opción 1**

En esta estructura mantenemos los cinco bounded contexts separados con relaciones claramente definidas. Las ventajas de este tipo de contexto son por un lado la clara separación de responsabilidades y por otro lado, se especifica que cada contexto se enfoca en una funcionalidad específica. Una de las principales desventajas es que hay una mayor complejidad en la sincronización entre contextos.

<img src="images/context_diagrams/opcion1.png">

<br>

**Opción 2**

Esta alternativa propone unir los contextos de IoT Monitoring y Cubicle Management en un solo bounded context. Al hacerlo, se elimina la necesidad de sincronización externa entre ambos, manteniendo relaciones similares con los demás contextos del sistema. <br> Esta combinación presenta ventajas como la simplificación de la arquitectura al disminuir la cantidad de bounded contexts, una comunicación más directa entre la detección de ocupación de los cubículos y la gestión de reservas. <br> No obstante, una desventajas es la combinación de responsabilidades distintas, ya que una parte se enfoca en la infraestructura de sensores y la otra en procesos administrativos. Esto podría dificultar que el personal de la universidad realice la instalación del sistema en menos de una hora sin ayuda técnica, y además genera el riesgo de que un solo contexto asuma demasiadas funciones.

<img src="images/context_diagrams/opcion2.png"> <br>

<br>

**Opcion 3** 

Esta alternativa propone una arquitectura compuesta por cinco bounded contexts bien definidos, con relaciones claras entre ellos. La estructura busca equilibrar la separación de responsabilidades, para permitir que el sistema escale y se mantenga con facilidad. Además, facilita la instalación sin asistencia técnica y asegura tiempos de respuesta adecuados, lo que contribuye directamente a mejorar la experiencia de los estudiantes en el uso del sistema.

* Headquarter Management se comunica con Student Management y Cubicle Management, proporcionando la información de las sedes. Student Management adapta su contenido según cada sede, y Cubicle Management utiliza la información organizativa que viene de Headquarter. En ambos casos, la relación es del tipo Customer/Supplier, donde Headquarter es el proveedor.

* Cubicle Management y Booking Management comparten el modelo de “cubículo” y su disponibilidad. Por eso, tienen una relación de tipo Shared Kernel, lo que asegura que ambos usen los mismos conceptos para evitar errores o confusión, incluyendo la validación de que solo se permitan reservas con grupos completos de estudiantes (4 o 5 por cubículo).

* Booking Management también se relaciona con Student Management, pero en este caso la relación es Conformist. Booking utiliza información de los estudiantes, pero se adapta a su estructura sin modificarla.

* IoT Monitoring se conecta con Cubicle Management mediante una Anti-corruption Layer. Esta capa traduce los datos que vienen de los sensores a un formato que Cubicle Management pueda entender. Así, se protege el sistema de los detalles técnicos del IoT y se facilita la instalación del sistema sin ayuda especializada.
  
<img src="images/context_diagrams/opcion3.png">

<br>

**Elección** <br>
Elegimos la opción 3, ya que proporciona el mejor equilibrio entre la separación de responsabilidades, la fácil de implementación y el cumplimiento de los requisitos del sistema. <br>
Al definir cinco bounded contexts con relaciones claras, se facilita la evolución independiente de cada parte del sistema, lo que mejora su escalabilidad y mantenibilidad. Además, al separar gestiones, como la de gestión de IoT mediante una Anti-corruption Layer, se simplifica la instalación. Asimismo, esta estructura garantiza tiempos de respuesta rápidos y optimiza la gestión de cubículos, reservas y estudiantes, brindando una experiencia más fluida y eficiente para los usuarios y el personal.
