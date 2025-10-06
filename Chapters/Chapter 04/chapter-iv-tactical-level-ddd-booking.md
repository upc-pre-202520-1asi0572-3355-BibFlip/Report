### 4.2.4 Bounded Context: Booking Bounded Context

El Booking Bounded Context es responsable de gestionar las reservas de cubículos en el sistema. Este contexto asegura que los estudiantes puedan realizar reservas de manera eficiente, gestionando la disponibilidad de cubículos, horarios y slots de tiempo. Además, permite a los administradores supervisar y gestionar las reservas activas, asegurando que las operaciones relacionadas con las reservas sean consistentes y cumplan con los estándares de calidad y precisión requeridos.

#### 4.2.4.1. Domain Layer

La Domain Layer del Booking Bounded Context encapsula la lógica de negocio relacionada con la gestión de reservas de cubículos. En esta capa, se definen los elementos principales del dominio, como agregados, entidades, objetos de valor, comandos, consultas y eventos, que representan los conceptos clave del sistema.

#### **Aggregates**

1. **Booking**
   - **Propósito**: Representa una reserva realizada por un grupo de estudiantes para un cubículo específico en una fecha y horario determinado.
   - **Atributos**:
     - `userId`: Identificador del estudiante que genera la reserva, representado como un objeto de valor `UserId`.
     - `cubicleId`: Cubículo reservado, representado como una referencia a la entidad `Cubicle`.
     - `bookingDate`: Fecha de la reserva.
     - `bookingSlots`: Conjunto de intervalos de tiempo reservados, representados como una colección de entidades `BookingSlot`.
   - **Características**:
     - Extiende `AuditableAbstractAggregateRoot`, lo que permite auditar cambios en las reservas.
     - Gestiona la relación entre el estudiante que genera la reserva, el cubículo y los slots reservados, asegurando consistencia y validación.

2. **Cubicle**
   - **Propósito**: Representa un cubículo en una sede específica, incluyendo su disponibilidad y detalles.
   - **Atributos**:
     - `cubicleDetails`: Detalles del cubículo, como número de cubículo y cantidad de asientos, representados como un objeto de valor `CubicleDetails`.
     - `headquarterId`: Identificador de la sede a la que pertenece el cubículo, representado como un objeto de valor `HeadquarterId`.
     - `status`: Estado actual del cubículo (`AVAILABLE`, `RESERVED`, `OCCUPIED`), representado como un objeto de valor `TableStatus`.
     - `availabilitySlots`: Conjunto de slots de disponibilidad generados para el cubículo, representados como una colección de entidades`AvailabilitySlot`.
   - **Características**:
     - Extiende `AuditableAbstractAggregateRoot`, lo que permite auditar cambios en los cubículos.
     - Gestiona la generación y actualización de slots de disponibilidad.

#### **Entities**

1. **AvailabilitySlot**
   - **Propósito**: Representa un intervalo de tiempo disponible para un cubículo en una fecha específica.
   - **Atributos**:
     - `dateOfSlot`: Fecha del slot.
     - `timeInterval`: Intervalo de tiempo del slot, representado como un objeto de valor `TimeSlot`.
     - `status`: Estado del slot (`AVAILABLE`, `RESERVED`), representado como un objeto de valor `ScheduleSlotStatus`.
   - **Métodos**:
     - `updateStatus(ScheduleSlotStatus status)`: Actualiza el estado del slot.

2. **BookingSlot**
   - **Propósito**: Representa un intervalo de tiempo reservado por un estudiante o grupo de estudiantese.
   - **Atributos**:
     - `timeInterval`: Intervalo de tiempo reservado, representado como un objeto de valor `TimeSlot`.

#### **Value Objects**

1. **UserId**
   - **Propósito**: Representa el identificador único de un estudiante.
   - **Validaciones**:
     - El identificador no puede ser negativo.

2. **HeadquarterId**
   - **Propósito**: Representa el identificador único de una sede.
   - **Validaciones**:
     - El identificador no puede ser nulo ni negativo.

3. **CubicleDetails**
   - **Propósito**: Representa los detalles de un cubículo, como su número y cantidad de asientos.
   - **Validaciones**:
     - El número de cubículo no puede ser negativo.
     - El número no puede ser negativo y la capacidad debe ser mayor a cero.

4. **CubicleStatus**
   - **Propósito**: Enumera los estados posibles de un cubículo (`AVAILABLE`, `RESERVED`, `OCCUPIED`).

5. **TimeSlot**
   - **Propósito**: Representa un intervalo de tiempo con una hora de inicio y una hora de fin.
   - **Validaciones**:
     - La hora de inicio y la hora de fin no pueden ser nulas.
     - La hora de inicio debe ser anterior a la hora de fin.

6. **ScheduleSlotStatus**
   - **Propósito**: Enumera los estados posibles de un slot de disponibilidad (`AVAILABLE`, `RESERVED`).

7. **MaximumDuration**
   - **Propósito**: Representa la duración máxima permitida para una reserva.
   - **Validaciones**:
     - La duración debe ser un número positivo.
     - La duración no puede exceder las 2 horas.

#### **Commands**

1. **CreateBookingCommand**
   - **Propósito**: Representa la solicitud para crear una nueva reserva.
   - **Atributos**:
     - `clientId`: Identificador del estudiante.
     - `cubibleId`: Identificador del cubiculo.
     - `bookingDate`: Fecha de la reserva.
     - `slotIds`: Lista de identificadores de slots reservados.

2. **CreateCubibleCommand**
   - **Propósito**: Representa la solicitud para crear un nuevo cubiculo.
   - **Atributos**:
     - `cubicleNumber`: Número del cubiculo.
     - `seats`: Cantidad de asientos.
     - `headquartersId`: Identificador de la sede.

3. **CreateTableScheduleCommand**
   - **Propósito**: Representa la solicitud para generar los slots de disponibilidad de un cubiculo.
   - **Atributos**:
     - `cubicleId`: Identificador del cubiculo.

#### **Queries**

1. **GetAllBookingsQuery**
   - **Propósito**: Recupera todas las reservas registradas en el sistema.

2. **GetAllCubiclesQuery**
   - **Propósito**: Recupera todas los cubiculos registradas en el sistema.

3. **GetBookingByIdQuery**
   - **Propósito**: Recupera una reserva específica por su identificador.

4. **GetCubicleByIdQuery**
   - **Propósito**: Recupera un cubiculo específica por su identificador.

5. **GetCubicleScheduleByIdAndDateQuery**
   - **Propósito**: Recupera los slots de disponibilidad de un cubiculo para una fecha específica.

#### **Events**

1. **SingleCubicleAvailabilitySlotsGeneratedEvent**
   - **Propósito**: Evento que se dispara cuando se generan los slots de disponibilidad para un cubiculo.
   - **Atributos**:
     - `tableId`: Identificador del cubiculo.

#### **Relaciones entre componentes**

- El agregado `Booking` actúa como el núcleo del dominio, gestionando las relaciones con las entidades `BookingSlot` y `Cubicle`.
- El agregado `Cubicle` gestiona la generación y actualización de los slots de disponibilidad (`AvailabilitySlot`).
- Los objetos de valor encapsulan datos inmutables y validaciones específicas, asegurando consistencia en el dominio.
- Los comandos y consultas permiten interactuar con el sistema de manera estructurada, facilitando la creación de reservas y la recuperación de información.
- Los eventos aseguran que las operaciones críticas, como la generación de slots de disponibilidad, sean comunicadas de manera eficiente a otros componentes del sistema.

Esta estructura asegura que la lógica de negocio relacionada con la gestión de reservas sea robusta, consistente y fácil de mantener, cumpliendo con los requisitos del sistema.

#### 4.2.4.2. Interface Layer

La **Interface Layer** del Booking Bounded Context expone los puntos de entrada al sistema a través de controladores REST. Esta capa permite la interacción con las entidades del dominio mediante solicitudes HTTP, facilitando la comunicación entre los clientes y el sistema. Además, incluye recursos y transformadores que aseguran una representación adecuada de los datos y su conversión entre las capas de la aplicación.

#### **Controllers**

Los controladores son responsables de manejar las solicitudes HTTP y delegar la lógica de negocio a los servicios correspondientes. A continuación, se describen los principales controladores:

1. **BookingController**
   - **Propósito**: Gestiona las operaciones relacionadas con las reservas de cubículos.
   - **Endpoints**:
     - `POST /api/v1/bookings`: Crea una nueva reserva.
     - `GET /api/v1/bookings/{id}`: Obtiene los detalles de una reserva específica por su ID.
     - `GET /api/v1/bookings`: Obtiene la lista de todas las reservas.
   - **Dependencias**:
     - `BookingCommandService`: Servicio encargado de manejar los comandos relacionados con las reservas.
     - `BookingQueryService`: Servicio encargado de manejar las consultas relacionadas con las reservas.

2. **CubicleController**
   - **Propósito**: Gestiona las operaciones relacionadas con los cubículos.
   - **Endpoints**:
     - `POST /api/v1/cubicles`: Crea un nuevo cubículo.
     - `GET /api/v1/cubicles/{cubicleId}`: Obtiene los detalles de un cubículo específico por su ID.
     - `GET /api/v1/cubicles`: Obtiene la lista de todos los cubículos.
     - `GET /api/v1/cubicles/{cubicleId}/schedule`: Obtiene los slots de disponibilidad de un cubículo para una fecha específica.
   - **Dependencias**:
     - `CubicleCommandService`: Servicio encargado de manejar los comandos relacionados con los cubículos.
     - `CubicleQueryService`: Servicio encargado de manejar las consultas relacionadas con los cubículos.

#### **Resources**

Los recursos representan los datos que se exponen a través de la API REST. Estos recursos son utilizados para estructurar las respuestas de los controladores y asegurar una representación clara y consistente de los datos. A continuación, se describen los principales recursos:

1. **AvailabilitySlotResource**
   - **Propósito**: Representa un slot de disponibilidad de un cubículo.
   - **Atributos**:
     - `id`: Identificador único del slot.
     - `date`: Fecha del slot.
     - `startTime`: Hora de inicio del slot.
     - `endTime`: Hora de fin del slot.
     - `status`: Estado del slot (`AVAILABLE`, `RESERVED`).

2. **BookingResource**
   - **Propósito**: Representa una reserva en el sistema.
   - **Atributos**:
     - `id`: Identificador único de la reserva.
     - `clientId`: Identificador del estudiante que realizó la reserva.
     - `cubicleId`: Identificador del cubículo reservado.
     - `bookingDate`: Fecha de la reserva.
     - `bookingSlots`: Lista de slots reservados.

3. **BookingSlotResource**
   - **Propósito**: Representa un slot reservado por un estudiante.
   - **Atributos**:
     - `startTime`: Hora de inicio del slot reservado.
     - `endTime`: Hora de fin del slot reservado.

4. **CreateBookingResource**
   - **Propósito**: Representa los datos necesarios para crear una nueva reserva.
   - **Atributos**:
     - `clientId`: Identificador del estudiante.
     - `cubicleId`: Identificador del cubículo.
     - `bookingDate`: Fecha de la reserva.
     - `slotIds`: Lista de identificadores de slots reservados.

5. **CreateCubicleResource**
   - **Propósito**: Representa los datos necesarios para crear un nuevo cubículo.
   - **Atributos**:
     - `headquarterId`: Identificador de la sede a la que pertenece el cubículo.
     - `cubicleNumber`: Número del cubículo.
     - `capacity`: Capacidad máxima del cubículo.

6. **CubicleResource**
   - **Propósito**: Representa un cubículo en el sistema.
   - **Atributos**:
     - `id`: Identificador único del cubículo.
     - `headquarterId`: Identificador de la sede a la que pertenece el cubículo.
     - `cubicleNumber`: Número del cubículo.
     - `capacity`: Capacidad máxima del cubículo.
     - `status`: Estado actual del cubículo (`AVAILABLE`, `RESERVED`, `OCCUPIED`, `MAINTENANCE`).

#### **Transformers**

Los transformadores son responsables de convertir las entidades del dominio en recursos y viceversa. Esto asegura que los datos expuestos a través de la API REST sean consistentes y estén en el formato esperado. A continuación, se describen los principales transformadores:

1. **AvailabilitySlotResourceFromEntityAssembler**
   - **Propósito**: Convierte una entidad `AvailabilitySlot` en un recurso `AvailabilitySlotResource`.
   - **Métodos principales**:
     - `toResourceFromEntity(AvailabilitySlot entity)`: Transforma un slot de disponibilidad en un recurso.
     - `toResourceListFromEntities(List<AvailabilitySlot> entities)`: Transforma una lista de slots de disponibilidad en una lista de recursos.

2. **BookingResourceFromEntityAssembler**
   - **Propósito**: Convierte una entidad `Booking` en un recurso `BookingResource`.
   - **Método principal**:
     - `toResourceFromEntity(Booking booking)`: Transforma una reserva en un recurso.

3. **CreateBookingCommandFromResourceAssembler**
   - **Propósito**: Convierte un recurso `CreateBookingResource` en un comando `CreateBookingCommand`.
   - **Método principal**:
     - `toCommandFromResource(CreateBookingResource resource)`: Transforma los datos de creación de una reserva en un comando.

4. **CreateCubicleCommandFromResourceAssembler**
   - **Propósito**: Convierte un recurso `CreateCubicleResource` en un comando `CreateCubicleCommand`.
   - **Método principal**:
     - `toCommandFromResource(CreateCubicleResource resource)`: Transforma los datos de creación de un cubículo en un comando.

5. **CubicleResourceFromEntityAssembler**
   - **Propósito**: Convierte una entidad `Cubicle` en un recurso `CubicleResource`.
   - **Método principal**:
     - `toResourceFromEntity(Cubicle entity)`: Transforma un cubículo en un recurso.

#### **Relaciones entre componentes**

- Los controladores (`BookingController`, `CubicleController`) utilizan los servicios de comandos y consultas para delegar la lógica de negocio.
- Los transformadores convierten las entidades del dominio en recursos para las respuestas HTTP y viceversa para las solicitudes entrantes.
- Los recursos estructuran los datos expuestos a los clientes, asegurando una representación clara y consistente.

Esta estructura asegura que la **Interface Layer** sea modular, reutilizable y fácil de mantener, facilitando la interacción entre los clientes y el sistema.

#### 4.2.4.3. Application Layer

La **Application Layer** del Booking Bounded Context actúa como un intermediario entre la **Domain Layer** y las capas externas, como la **Interface Layer** y la **Infrastructure Layer**. Su propósito principal es coordinar las operaciones de negocio, manejar comandos y consultas, orquestar la lógica de aplicación y garantizar que las reglas del dominio se cumplan de manera consistente. Además, esta capa incluye manejadores de eventos y servicios externos (ACL) para interactuar con otros contextos delimitados.


#### **Command Services**

Los servicios de comandos son responsables de ejecutar operaciones que modifican el estado del sistema. A continuación, se describen los principales servicios de comandos:

1. **BookingCommandServiceImpl**
   - **Propósito**: Gestiona las operaciones relacionadas con la creación de reservas de cubículos.
   - **Métodos principales**:
     - `handle(CreateBookingCommand command)`: Crea una nueva reserva, validando la disponibilidad de los slots y asegurando que las reglas de negocio, como la duración máxima de la reserva y la capacidad mínima del cubículo, se cumplan.
   - **Validaciones**:
     - Verifica que el estudiante exista utilizando el servicio externo `ExternalUserService`.
     - Valida que los slots solicitados estén disponibles y sean consecutivos.
     - Asegura que la duración total de la reserva no exceda las 2 horas.
     - Valida que la reserva incluya al menos 3 estudiantes.
   - **Dependencias**:
     - `BookingRepository`: Persistencia de reservas.
     - `CubicleRepository`: Gestión de cubículos y sus slots de disponibilidad.
     - `ExternalUserService`: Verifica la existencia de los estudiantes.

2. **CubicleCommandServiceImpl**
   - **Propósito**: Gestiona las operaciones relacionadas con la creación de cubículos y la generación de slots de disponibilidad.
   - **Métodos principales**:
     - `handle(CreateCubicleCommand command)`: Crea un nuevo cubículo en una sede específica, validando que la sede exista y que no haya duplicados.
     - `handle(CreateCubicleScheduleCommand command)`: Genera los slots de disponibilidad para un cubículo, basándose en los horarios y el intervalo de la sede.
   - **Validaciones**:
     - Verifica que la sede exista utilizando el servicio externo `ExternalHeadquarterService`.
     - Asegura que no existan cubículos duplicados en la misma sede.
   - **Dependencias**:
     - `CubicleRepository`: Persistencia de cubículos y sus slots de disponibilidad.
     - `ExternalHeadquarterService`: Obtiene información de la sede, como horarios y intervalos.


#### **Query Services**

Los servicios de consultas son responsables de recuperar información del sistema sin modificar su estado. A continuación, se describen los principales servicios de consultas:

1. **BookingQueryServiceImpl**
   - **Propósito**: Gestiona las consultas relacionadas con las reservas.
   - **Métodos principales**:
     - `handle(GetBookingByIdQuery query)`: Recupera una reserva específica por su ID.
     - `handle(GetAllBookingsQuery query)`: Recupera todas las reservas registradas en el sistema.
   - **Dependencias**:
     - `BookingRepository`: Persistencia de reservas.

2. **CubicleQueryServiceImpl**
   - **Propósito**: Gestiona las consultas relacionadas con los cubículos y sus slots de disponibilidad.
   - **Métodos principales**:
     - `handle(GetCubicleByIdQuery query)`: Recupera un cubículo específico por su ID.
     - `handle(GetAllCubiclesQuery query)`: Recupera todos los cubículos registrados en el sistema.
     - `handle(GetCubicleScheduleByIdAndDateQuery query)`: Recupera los slots de disponibilidad de un cubículo para una fecha específica.
   - **Dependencias**:
     - `CubicleRepository`: Persistencia de cubículos y sus slots de disponibilidad.

#### **Event Handlers**

Los manejadores de eventos son responsables de reaccionar a eventos específicos del sistema. A continuación, se describe el principal manejador de eventos:

1. **SingleCubicleAvailabilitySlotsGeneratedEventHandler**
   - **Propósito**: Maneja el evento `SingleCubicleAvailabilitySlotsGeneratedEvent`, que se dispara cuando se generan los slots de disponibilidad para un cubículo.
   - **Método principal**:
     - `on(SingleCubicleAvailabilitySlotsGeneratedEvent event)`: Genera los slots de disponibilidad para un cubículo específico.
   - **Dependencias**:
     - `CubicleCommandService`: Servicio encargado de manejar los comandos relacionados con los cubículos.


#### **Outbound Services (ACL)**

Los servicios externos proporcionan funcionalidades auxiliares que no forman parte del dominio principal. A continuación, se describen los principales servicios externos:

1. **ExternalHeadquarterService**
   - **Propósito**: Interactúa con el Branching Bounded Context para obtener información de las sedes.
   - **Métodos principales**:
     - `getHeadquarterOpeningTime(Long headquarterId)`: Obtiene la hora de apertura de una sede.
     - `getHeadquarterClosingTime(Long headquarterId)`: Obtiene la hora de cierre de una sede.
     - `getHeadquarterIntervalMinutes(Long headquarterId)`: Obtiene el intervalo de servicio en minutos de una sede.
     - `existsHeadquarter(Long headquarterId)`: Verifica si una sede existe.

2. **ExternalUserService**
   - **Propósito**: Interactúa con el IAM Bounded Context para verificar la existencia de estudiantes.
   - **Método principal**:
     - `existUserById(Long userId)`: Verifica si un estudiante existe en el sistema.

#### **Relaciones entre componentes**

- Los **Command Services** interactúan con los repositorios para modificar el estado del sistema y con los servicios externos (ACL) para validar información de otros contextos.  
- Los **Query Services** interactúan únicamente con los repositorios para recuperar información del sistema.  
- Los **Event Handlers** reaccionan a eventos del dominio para ejecutar lógica adicional, como la generación de slots de disponibilidad.  
- Los **Outbound Services** (ACL) permiten la integración con otros contextos delimitados, como el Branching Bounded Context y el IAM Bounded Context.  

La **Application Layer** del Booking Bounded Context asegura que las operaciones relacionadas con la gestión de reservas y cubículos sean robustas, consistentes y fáciles de mantener. Al coordinar la lógica de negocio, manejar eventos y facilitar la integración con otros contextos, esta capa garantiza que las reglas del dominio se cumplan de manera eficiente y que el sistema sea escalable y extensible.

#### 4.2.4.4. Infrastructure Layer

La **Infrastructure Layer** del Booking Bounded Context proporciona las implementaciones técnicas necesarias para soportar las operaciones del sistema relacionadas con la gestión de reservas y cubículos. Esta capa incluye repositorios para la persistencia de datos y componentes que conectan la lógica de negocio con los recursos externos, como bases de datos. Su objetivo principal es garantizar que las operaciones de almacenamiento y recuperación de información sean eficientes, consistentes y seguras.

---

#### **Persistencia (JPA Repositories)**

1. **BookingRepository**
   - **Propósito**: Proporciona métodos para interactuar con la base de datos de reservas.
   - **Características**:
     - Extiende `JpaRepository`, lo que permite realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) sobre las entidades `Booking`.
     - Facilita la persistencia y recuperación de reservas, asegurando que las operaciones relacionadas con las reservas sean eficientes y confiables.

2. **CubicleRepository**
   - **Propósito**: Proporciona métodos para interactuar con la base de datos de cubículos y sus slots de disponibilidad.
   - **Métodos principales**:
     - `existsByHeadquarterIdAndCubicleDetails_CubicleNumber(HeadquarterId headquarterId, Integer cubicleDetails_cubicleNumber)`: Verifica si existe un cubículo con un número específico en una sede.
     - `findAvailabilitySlotsByCubicleIdAndDate(Long cubicleId, LocalDate date)`: Recupera los slots de disponibilidad de un cubículo para una fecha específica.
     - `findByIdWithSlotsForUpdate(Long id)`: Recupera un cubículo junto con sus slots de disponibilidad utilizando un bloqueo pesimista para evitar modificaciones concurrentes.
   - **Características**:
     - Extiende `JpaRepository`, lo que permite realizar operaciones CRUD sobre las entidades `Cubicle`.
     - Incluye consultas personalizadas para manejar la relación entre cubículos y sus slots de disponibilidad.
     - Utiliza un bloqueo pesimista (`PESSIMISTIC_WRITE`) para garantizar la consistencia de los datos durante las operaciones críticas, como la creación de reservas.

---

#### **Relaciones entre componentes**

- **Persistencia**: Los repositorios `BookingRepository` y `CubicleRepository` proporcionan acceso a los datos almacenados en la base de datos, permitiendo a las capas superiores (como la **Application Layer**) interactuar con las entidades del dominio.  
- **Validación**: Los métodos personalizados en `CubicleRepository` son utilizados para validar la existencia de cubículos y recuperar información específica, como los slots de disponibilidad, asegurando la consistencia de los datos durante las operaciones de negocio.  

La **Infrastructure Layer** del Booking Bounded Context asegura que las operaciones relacionadas con la persistencia de datos sean robustas y confiables. Al proporcionar repositorios especializados para las reservas y cubículos, esta capa facilita la integración con la base de datos y garantiza que las reglas de negocio, como la validación de slots de disponibilidad y la unicidad de cubículos, se cumplan de manera eficiente. Esta estructura modular y reutilizable permite que el sistema sea escalable y fácil de mantener.

#### 4.2.4.5. Bounded Context Software Architecture Component Level Diagrams

En esta sección se presenta el diagrama de componentes del **Booking Bounded Context**, el cual detalla los principales módulos y sus interacciones dentro del contexto delimitado. Este diagrama sigue el enfoque del C4 Model para representar los componentes clave, como servicios de aplicación, controladores, repositorios y servicios externos, junto con sus relaciones.

El propósito de este diagrama es proporcionar una visión clara y estructurada de cómo se organizan los componentes dentro del contexto, facilitando la comprensión de su arquitectura y permitiendo identificar puntos de integración y responsabilidades.

<img src="https://i.ibb.co/qYs1Jsgy/booking.png" alt="Booking BC Component Diagram" border="0">

El **Booking Bounded Context** está compuesto por los siguientes módulos principales:

1. **Application Layer**:
   - Coordina las operaciones de negocio relacionadas con la gestión de reservas y cubículos.
   - Incluye servicios de comandos y consultas que interactúan con la **Domain Layer** y la **Infrastructure Layer**.
   - Maneja eventos relacionados con la creación de reservas y la generación de slots de disponibilidad.

2. **Interface Layer**:
   - Expone los puntos de entrada al sistema a través de controladores REST.
   - Incluye recursos y transformadores que aseguran una representación adecuada de los datos y su conversión entre las capas de la aplicación.

3. **Domain Layer**:
   - Encapsula la lógica de negocio relacionada con la gestión de reservas y cubículos.
   - Define los agregados, entidades y objetos de valor que representan los conceptos clave del dominio.

4. **Infrastructure Layer**:
   - Proporciona las implementaciones técnicas necesarias para soportar las operaciones del sistema.
   - Incluye repositorios para la persistencia de datos y componentes que conectan la lógica de negocio con los recursos externos, como bases de datos.


#### 4.2.4.6. Bounded Context Software Architecture Code Level Diagrams

En este apartado se presentan los diagramas que ofrecen un mayor nivel de detalle sobre la implementación de los componentes del **Booking Bounded Context**. Estos diagramas están diseñados para ilustrar cómo se estructuran las clases, interfaces y relaciones dentro de las capas del contexto, proporcionando una visión técnica que facilita el desarrollo, mantenimiento y evolución del sistema.

##### 4.2.4.6.1. Bounded Context Domain Layer Class Diagrams

El diagrama de clases correspondiente a la **Domain Layer** del **Booking Bounded Context** incluye las clases principales, como agregados, entidades y objetos de valor, así como las interfaces y enumeraciones que definen el comportamiento del dominio. También se destacan las relaciones entre estos elementos, como asociaciones, composiciones y dependencias.

<img src="" alt="Booking BC Domain Layer Class Diagram"/><br>


**Elementos principales del diagrama:**

1. **Aggregates**:
   - `Booking`: Agregado principal que encapsula la lógica de negocio relacionada con las reservas. Incluye atributos como `userId`, `cubicleId`, `bookingDate` y `bookingSlots`.
   - `Cubicle`: Agregado que representa un cubículo en una sede específica, incluyendo su disponibilidad y detalles.

2. **Entities**:
   - `AvailabilitySlot`: Representa un intervalo de tiempo disponible para un cubículo en una fecha específica.
   - `BookingSlot`: Representa un intervalo de tiempo reservado por un estudiante.

3. **Value Objects**:
   - `UserId`: Representa el identificador único de un estudiante.
   - `HeadquarterId`: Representa el identificador único de una sede.
   - `CubicleDetails`: Representa los detalles de un cubículo, como su número y cantidad de asientos.
   - `TimeSlot`: Representa un intervalo de tiempo con una hora de inicio y una hora de fin.
   - `CubicleStatus`: Enumera los estados posibles de un cubículo (`AVAILABLE`, `RESERVED`, `OCCUPIED`, `MAINTENANCE`).
   - `ScheduleSlotStatus`: Enumera los estados posibles de un slot de disponibilidad (`AVAILABLE`, `RESERVED`).

**Relaciones destacadas:**
- El agregado `Booking` gestiona las relaciones con las entidades `BookingSlot` y `Cubicle`.
- El agregado `Cubicle` gestiona la generación y actualización de los slots de disponibilidad (`AvailabilitySlot`).
- Los objetos de valor encapsulan datos inmutables y validaciones específicas, asegurando consistencia en el dominio.


##### 4.2.4.6.2. Bounded Context Database Design Diagram.

El diseño de la base de datos para el **Booking Bounded Context** refleja la estructura del dominio, asegurando que las entidades y relaciones definidas en la **Domain Layer** se representen de manera eficiente en el modelo relacional.

[![IAM-DB.jpg](https://i.postimg.cc/nzsYT184/db1.png)](https://i.postimg.cc/nzsYT184/db1.png)

**Este diseño incluye las siguientes tablas principales:**

1. **Bookings**:
   - Representa las reservas realizadas por los estudiantes.
   - Atributos principales:
     - `id`: Identificador único de la reserva.
     - `user_id`: Identificador del estudiante que realizó la reserva.
     - `cubicle_id`: Identificador del cubículo reservado.
     - `booking_date`: Fecha de la reserva.

2. **Cubicles**:
   - Representa los cubículos disponibles en las sedes.
   - Atributos principales:
     - `id`: Identificador único del cubículo.
     - `headquarter_id`: Identificador de la sede a la que pertenece el cubículo.
     - `cubicle_number`: Número del cubículo.
     - `seats`: Cantidad de asientos.
     - `status`: Estado actual del cubículo.

3. **AvailabilitySlots**:
   - Representa los slots de disponibilidad de los cubículos.
   - Atributos principales:
     - `id`: Identificador único del slot.
     - `cubicle_id`: Identificador del cubículo asociado.
     - `date_of_slot`: Fecha del slot.
     - `start_time`: Hora de inicio del slot.
     - `end_time`: Hora de fin del slot.
     - `status`: Estado del slot (`AVAILABLE`, `RESERVED`).

4. **BookingSlots**:
   - Representa los slots reservados por los estudiantes.
   - Atributos principales:
     - `id`: Identificador único del slot reservado.
     - `booking_id`: Identificador de la reserva asociada.
     - `start_time`: Hora de inicio del slot reservado.
     - `end_time`: Hora de fin del slot reservado.
     

