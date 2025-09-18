### 4.1.3. Software Architecture

En esta sección, se presenta y explica la representación de la arquitectura de software para el sistema utilizando el C4 Model. A través de estos diagramas, se busca proporcionar una comprensión clara y accesible de la arquitectura, permitiendo a los miembros del equipo, stakeholders y futuros desarrolladores entender cómo se organiza y comunica el sistema a diferentes niveles.

#### 4.1.3.1. Software Architecture System Landscape Diagram

Este diagrama muestra que el sistema opera en un ecosistema compuesto por tres tipos de usuarios: Estudiantes, Administradores de Cubículos y Super Administradores. Los estudiantes utilizan el sistema para reservar cubículos y consultar su disponibilidad en tiempo real. Los Administradores de Cubículos gestionan la asignación de espacios y verifican que se cumpla la regla de ocupación mínima (no se pueden reservar cubículos con menos de 4 estudiantes). Por su parte, el Super Administrador se encargan de gestionar al personal bibliotecario. El sistema también se conecta con un servicio externo, como Twilio, para enviar notificaciones a los usuarios.

<a href="https://ibb.co/qM3NP10P"><img src="https://i.ibb.co/6R7Hfsvf/Landscape-Diagram.png" alt="Landscape-Diagram" border="0"></a>

#### 4.1.3.2. Software Architecture Context Level Diagrams

Este diagrama muestra que el sistema (representado como una única entidad) interactúa con los tres tipos de usuarios:

- Estudiantes, que buscan consultar cubículos disponibles y realizar reservas.

- Administradores de Cubículos, que gestionan los espacios disponibles y validan las reservas.

- Super Administradores, que mantienen el sistema en funcionamiento y realizan configuraciones generales.

El sistema también se comunica con dos servicios externos:

- Google Maps API, que permite mostrar las ubicaciones de las sedes UPC.

- Sensores IoT, que proveen datos en tiempo real sobre la ocupación de cubículos.

<img src="" alt="System Context en C4"/><br>

#### 4.1.3.3. Software Architecture Container Level Diagrams

Este diagrama muestra que el sistema está compuesto por cuatro contenedores principales:

- Una aplicación web accesible desde navegadores.

- Una aplicación móvil para estudiantes en dispositivos portátiles.

- Una API que concentra toda la lógica de negocio, incluyendo la validación de reglas de ocupación mínima y reservas.

- Una base de datos que almacena información de estudiantes, cubículos y reservas.

Adicionalmente, se cuenta con un módulo de sensores encargado de procesar los datos de ocupación provenientes de los dispositivos IoT instalados en los cubículos. La API también se conecta con Google Maps para mostrar la ubicación de las sedes de la universidad.

<img src="" alt="Container en C4"/><br>

#### 4.1.3.4. Software Architecture Deployment Diagrams

Este diagrama muestra que el sistema se despliega en tres entornos principales: Microsoft Azure Cloud, Dispositivos Cliente y Sedes físicas de la universidad.

En Azure, el sistema utiliza App Service para alojar la aplicación web frontend, otro App Service para la API (con documentación Swagger), Azure Database for PostgreSQL para los datos, y Azure IoT Hub para gestionar las comunicaciones con los sensores de cubículos.

Los estudiantes acceden al sistema desde navegadores web o dispositivos Android. En cada sede, los cubículos cuentan con sensores IoT conectados a un Gateway local, que transmite la información al IoT Hub en Azure. Todas las comunicaciones se realizan mediante protocolos seguros como HTTPS, MQTT/TLS o conexiones PostgreSQL.

<img src="" alt="Deployment en C4"/><br>


