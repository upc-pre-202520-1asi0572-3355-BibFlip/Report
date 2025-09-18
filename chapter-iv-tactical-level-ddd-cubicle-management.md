### 4.2.2. Bounded Context: Cubicle Management

El **Cubicle Management Bounded Context** es responsable de gestionar la información y el estado de los cubículos en las sedes de la universidad. Este contexto se encarga de registrar, actualizar y consultar el estado de los cubículos, así como su capacidad, ubicación dentro de la sede y otros atributos relevantes. Es el núcleo central que permite la visualización en tiempo real del estado de ocupación de los cubículos para los usuarios.

#### 4.2.2.1. Domain Layer

La **Domain Layer** del Cubicle Management Bounded Context encapsula la lógica de negocio relacionada con la gestión de cubículos. En esta capa, se definen los elementos principales del dominio, como agregados, entidades y objetos de valor, que representan los conceptos clave del sistema.

##### **Aggregates**
1. **Cubicle**
   - **Propósito**: El agregado principal es el cubículo (`Cubicle`), que encapsula la lógica de negocio relacionada con la gestión del cubículo y su estado de ocupación.
   - **Atributos**:
     - `cubicleNumber`: Número identificativo del cubículo, representado como un objeto de valor `CubicleNumber`.
     - `headquarterId`: Identificador de la sede a la que pertenece el cubículo, representado como un objeto de valor `HeadquarterId`.
     - `capacity`: Capacidad del cubículo (máx. 4 o 5 estudiantes), representada como un objeto de valor `Capacity`.
     - `status`: Estado actual del cubículo, representado como un objeto de valor `CubicleStatus`.
     - `location`: Ubicación física del cubículo dentro de la sede, representada como un objeto de valor `Location`.
   - **Métodos**:
     - `updateStatus(CubicleStatus status)`: Actualiza el estado del cubículo.
     - `assignToHeadquarter(HeadquarterId headquarterId)`: Asigna el cubículo a una sede específica.
     - `changeCapacity(Capacity capacity)`: Modifica la capacidad del cubículo.
     - `relocate(Location location)`: Actualiza la ubicación del cubículo dentro de la sede.
   - **Características**:
     - Extiende `AuditableAbstractAggregateRoot`, lo que permite auditar cambios en los cubículos.
     - Gestiona la validación de estados y cambios según reglas de negocio.

##### **Entities**
1. **Seat**
   - **Propósito**: La entidad `Seat` representa cada asiento asociado a un cubículo, con su estado de ocupación.
   - **Atributos**:
     - `id`: Identificador único del asiento.
     - `seatNumber`: Número identificativo del asiento dentro del cubículo.
     - `status`: Estado actual del asiento (ocupado o libre), representado como un objeto de valor `SeatStatus`.
   - **Métodos**:
     - `updateStatus(SeatStatus status)`: Actualiza el estado del asiento.
     - `isOccupied()`: Verifica si el asiento está ocupado.

##### **Value Objects**
1. **CubicleNumber**
   - Representa el número identificativo de un cubículo.
   - Validaciones: debe ser positivo y único dentro de una sede.

2. **HeadquarterId**
   - Representa el identificador único de una sede.
   - Validaciones: no puede ser nulo ni negativo.

3. **Capacity**
   - Representa la capacidad de un cubículo en términos de estudiantes.
   - Validaciones:
     - La capacidad debe ser un número positivo.
     - El rango permitido es entre 4 y 5 estudiantes.

4. **CubicleStatus**
   - Enumera los estados posibles de un cubículo.
   - Valores:
     - `AVAILABLE`: El cubículo está disponible para reservar.
     - `OCCUPIED`: El cubículo está actualmente ocupado.
     - `RESERVED`: El cubículo está reservado.
     - `MAINTENANCE`: El cubículo está fuera de servicio temporalmente.

5. **SeatStatus**
   - Enumera los estados posibles de un asiento.
   - Valores:
     - `OCCUPIED`: El asiento está ocupado por un estudiante.
     - `FREE`: El asiento está libre.

6. **Location**
   - Representa la ubicación física de un cubículo dentro de la sede.
   - Atributos:
     - `zone`: Zona de la universidad (piso, bloque, biblioteca, etc.).
     - `coordinates`: Coordenadas relativas dentro del plano de la sede.

#### **Commands**
1. **CreateCubicleCommand**
   - Crea un nuevo cubículo en una sede específica.
   - Atributos: `cubicleNumber`, `headquarterId`, `capacity`, `location`.

2. **UpdateCubicleStatusCommand**
   - Actualiza el estado de un cubículo existente.
   - Atributos: `cubicleId`, `status`.

3. **DeleteCubicleCommand**
   - Elimina un cubículo existente.
   - Atributos: `cubicleId`, `headquarterId`.

#### **Queries**
1. **GetCubicleByIdQuery**
   - Recupera un cubículo específico por su ID.
   - Atributos: `cubicleId`.

2. **GetCubiclesByHeadquarterQuery**
   - Recupera todos los cubículos asociados a una sede.
   - Atributos: `headquarterId`.

3. **GetCubiclesByStatusQuery**
   - Recupera todos los cubículos con un estado específico.
   - Atributos: `status`, `headquarterId`.

#### **Events**
1. **CubicleCreatedEvent**
   - Evento que se dispara cuando se crea un nuevo cubículo.
   - Atributos: `cubicleId`, `headquarterId`.

2. **CubicleStatusChangedEvent**
   - Evento que se dispara cuando cambia el estado de un cubículo.
   - Atributos: `cubicleId`, `previousStatus`, `newStatus`, `timestamp`.

#### 4.2.2.2. Interface Layer

La **Interface Layer** del Cubicle Management Bounded Context expone los puntos de entrada al sistema a través de controladores REST. Esta capa permite la interacción con las entidades del dominio mediante solicitudes HTTP.

#### **Access Control Layer (ACL)**
1. **CubicleManagementContextFacade**
   - **Propósito**: Proporciona una interfaz simplificada para interactuar con el dominio desde otros contextos.
   - **Métodos principales**:
     - `getCubicleStatus(Long cubicleId)`
     - `getCubiclesByStatus(Long headquarterId, String status)`
     - `existsCubicle(Long cubicleId)`
   - **Dependencias**: `CubicleQueryService`

#### **Controllers**
1. **CubicleController**
   - **Endpoints**:
     - `POST /api/v1/cubicles`
     - `GET /api/v1/cubicles/{cubicleId}`
     - `GET /api/v1/cubicles`
     - `GET /api/v1/headquarters/{headquarterId}/cubicles`
     - `PUT /api/v1/cubicles/{cubicleId}/status`
     - `DELETE /api/v1/cubicles/{cubicleId}`

#### **Resources**
1. **CreateCubicleResource**
   - Atributos: `cubicleNumber`, `headquarterId`, `capacity`, `zone`, `xPosition`, `yPosition`

2. **CubicleResource**
   - Atributos: `id`, `cubicleNumber`, `headquarterId`, `capacity`, `status`, `zone`, `position`

3. **UpdateCubicleStatusResource**
   - Atributos: `status`

#### **Transformers**
1. **CreateCubicleCommandFromResourceAssembler**
2. **CubicleResourceFromEntityAssembler**
3. **UpdateCubicleStatusCommandFromResourceAssembler**

#### 4.2.2.3. Application Layer

La **Application Layer** actúa como intermediaria entre la **Domain Layer** y capas externas.

##### **Command Services**
- **CubicleCommandServiceImpl**
  - Métodos: `handle(CreateCubicleCommand)`, `handle(UpdateCubicleStatusCommand)`, `handle(DeleteCubicleCommand)`
  - Validaciones:
    - Capacidad entre 4 y 5 estudiantes.
    - Verificación de sede con `ExternalHeadquarterService`.
    - Evitar duplicados en la misma sede.
  - Dependencias: `CubicleRepository`, `ExternalHeadquarterService`

##### **Query Services**
- **CubicleQueryServiceImpl**
  - Métodos: `handle(GetCubicleByIdQuery)`, `handle(GetCubiclesByHeadquarterQuery)`, `handle(GetCubiclesByStatusQuery)`
  - Dependencias: `CubicleRepository`

##### **Event Handlers**
- **CubicleStatusChangedEventHandler**
  - Maneja `CubicleStatusChangedEvent`
  - Dependencias: `NotificationService`, `StatisticsService`

##### **Outbound Services (ACL)**
- **ExternalHeadquarterService**
  - `existsHeadquarter(Long headquarterId)`
  
#### 4.2.2.4. Infrastructure Layer

La **Infrastructure Layer** del Cubicle Management Bounded Context proporciona implementaciones técnicas y repositorios.

##### **Persistencia (JPA Repositories)**
1. **CubicleRepository**
   - `findByHeadquarterId(Long headquarterId)`
   - `findByHeadquarterIdAndStatus(Long headquarterId, CubicleStatus status)`
   - `existsByHeadquarterIdAndCubicleNumber(Long headquarterId, Integer cubicleNumber)`

#### 4.2.2.5. Bounded Context Software Architecture Component Level Diagrams

<img src="" alt="Cubicle Management BC Component Diagram"/><br>

#### 4.2.2.6. Bounded Context Software Architecture Code Level Diagrams

##### 4.2.2.6.1. Bounded Context Domain Layer Class Diagrams

<img src="" alt="Cubicle Management BC Domain Layer Class Diagram"/><br>

##### 4.2.2.6.2. Bounded Context Database Design Diagram


El diseño de la base de datos para el **Cubicle Management Bounded Context** refleja la estructura del dominio, asegurando que las entidades y relaciones definidas en la **Domain Layer** se representen de manera eficiente en el modelo relacional.

<img src="" alt="Cubicle Management BC Data Base Diagram"/><br>

**Este diseño incluye las siguientes tablas principales:**

1. **Cubicles**:
   - Representa los cubículos en el sistema.
   - **Atributos principales**:
     - `id`: Identificador único del cubículo.
     - `cubicle_number`: Número del cubículo dentro de la sede.
     - `headquarter_id`: Identificador de la sede a la que pertenece el cubículo.
     - `capacity`: Capacidad del cubículo en términos de estudiantes.
     - `status`: Estado actual del cubículo (AVAILABLE, OCCUPIED, RESERVED, MAINTENANCE).
     - `zone`: Zona de la sede donde está ubicado el cubículo.
     - `x_position`: Coordenada X del cubículo en el plano.
     - `y_position`: Coordenada Y del cubículo en el plano.

2. **Seats**:
   - Representa los asientos asociados a los cubículos.
   - **Atributos principales**:
     - `id`: Identificador único del asiento.
     - `cubicle_id`: Identificador del cubículo al que pertenece el asiento.
     - `seat_number`: Número del asiento dentro del cubículo.
     - `status`: Estado actual del asiento (OCCUPIED, FREE).



