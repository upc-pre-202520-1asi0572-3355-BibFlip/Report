### 4.2.3. Bounded Context: Branching

El **Branching Bounded Context** es responsable de gestionar la información de las sedes (headquarters) del sistema. Este contexto asegura que las sedes puedan ser registradas, actualizadas y gestionadas de manera eficiente, incluyendo detalles como horarios de atención, ubicación geográfica, información de contacto y dirección. Este contexto es clave para garantizar que las operaciones relacionadas con las sedes sean consistentes y cumplan con los estándares de calidad y precisión requeridos.

#### 4.2.3.1. Domain Layer


La **Domain Layer** del Branching Bounded Context encapsula la lógica de negocio relacionada con la gestión de sedes. En esta capa, se definen los elementos principales del dominio, como agregados, entidades y objetos de valor, que representan los conceptos clave del sistema.

##### **Aggregates**
1. **Headquarter**
   - **Propósito**: El agregado principal es la sede (`Headquarter`), que encapsula la lógica de negocio relacionada con la gestión de información de las sedes.
   - **Atributos**:
     - `name`: Nombre de la sede, representado como un objeto de valor `NameHeadquarter`.
     - `contactNumbers`: Números de contacto de la sede, representados como un objeto de valor `ContactNumbers`.
     - `coordinates`: Coordenadas geográficas de la sede, representadas como un objeto de valor `Coordinates`.
     - `schedule`: Horarios de atención de la sede, representados como una entidad `Schedule`.
     - `address`: Dirección de la sede, representada como un objeto de valor `StreetAddress`.
   - **Métodos**:
     - `getOpeningTime()`: Devuelve la hora de apertura de la sede.
     - `getClosingTime()`: Devuelve la hora de cierre de la sede.
     - `getIntervalMinutes()`: Devuelve el intervalo de tiempo en minutos entre reservas.
   - **Características**:
     - Extiende `AuditableAbstractAggregateRoot`, lo que permite auditar cambios en las sedes.
     - Gestiona la relación entre los horarios, la dirección y los datos de contacto de la sede, asegurando consistencia y validación.

##### **Entities**
1. **Schedule**
   - **Propósito**: Representa los horarios de atención de una sede.
   - **Atributos**:
     - `businessHours`: Horarios de apertura y cierre, representados como un objeto de valor `BusinessHours`.
     - `intervalMinutes`: Intervalo de tiempo en minutos entre reservas.
   - **Características**:
     - Permite definir y validar los horarios de atención de la sede.
     - Incluye validaciones para garantizar que los horarios sean consistentes (por ejemplo, la hora de apertura no puede ser posterior a la hora de cierre).

##### **Value Objects**
1. **BusinessHours**
   - **Propósito**: Representa los horarios de apertura y cierre de una sede.
   - **Atributos**:
     - `openingTime`: Hora de apertura.
     - `closingTime`: Hora de cierre.
   - **Validaciones**:
     - La hora de apertura no puede ser nula.
     - La hora de cierre no puede ser nula.
     - La hora de apertura no puede ser posterior a la hora de cierre.

2. **ContactNumbers**
   - **Propósito**: Representa los números de contacto de una sede.
   - **Atributos**:
     - `landlinePhone`: Número de teléfono fijo.
     - `mobilePhone`: Número de teléfono móvil.
   - **Validaciones**:
     - Ambos números deben ser válidos y no nulos.

3. **Coordinates**
   - **Propósito**: Representa las coordenadas geográficas de una sede.
   - **Atributos**:
     - `latitude`: Latitud de la sede.
     - `longitude`: Longitud de la sede.
   - **Validaciones**:
     - La latitud y la longitud no pueden ser nulas.

4. **NameHeadquarter**
   - **Propósito**: Representa el nombre de una sede.
   - **Atributos**:
     - `name`: Nombre de la sede.
   - **Validaciones**:
     - El nombre no puede ser nulo ni vacío.
     - El nombre debe cumplir con un formato válido (solo letras y espacios).

5. **StreetAddress**
   - **Propósito**: Representa la dirección de una sede.
   - **Atributos**:
     - `street`: Calle.
     - `number`: Número de la dirección.
     - `city`: Ciudad.
     - `postalCode`: Código postal.
     - `country`: País.
   - **Validaciones**:
     - Los campos `street`, `city`, `postalCode` y `country` no pueden ser nulos ni vacíos.
     - La calle debe cumplir con un formato válido (solo letras, espacios y puntos).

#### **Relaciones entre componentes**
- El agregado `Headquarter` actúa como el núcleo del dominio, gestionando las relaciones con los objetos de valor (`NameHeadquarter`, `ContactNumbers`, `Coordinates`, `StreetAddress`) y la entidad `Schedule`.
- Los objetos de valor encapsulan datos inmutables y validaciones específicas, asegurando consistencia en el dominio.
- La entidad `Schedule` permite modelar horarios complejos, incluyendo intervalos de tiempo entre reservas.

#### 4.2.3.2. Interface Layer

La **Interface Layer** del Branching Bounded Context expone los puntos de entrada al sistema a través de controladores REST y una ACL (Access Control Layer). Esta capa permite la interacción con las entidades del dominio mediante solicitudes HTTP, facilitando la comunicación entre los clientes y el sistema. Además, incluye recursos y transformadores que aseguran una representación adecuada de los datos y su conversión entre las capas de la aplicación.

#### **Access Control Layer (ACL)**

1. **HeadquarterContextFacade**
   - **Propósito**: Proporciona una interfaz simplificada para interactuar con el dominio del Branching Bounded Context desde otros contextos. Permite consultar información clave de las sedes, como horarios de apertura y cierre, intervalos de servicio y existencia de una sede.
   - **Métodos principales**:
     - `getOpeningTime(Long headquarterId)`: Devuelve la hora de apertura de una sede.
     - `getClosingTime(Long headquarterId)`: Devuelve la hora de cierre de una sede.
     - `getIntervalMinutes(Long headquarterId)`: Devuelve el intervalo de servicio en minutos de una sede.
     - `existsHeadquarter(Long headquarterId)`: Verifica si una sede existe en el sistema.
   - **Dependencias**:
     - `HeadquarterQueryService`: Servicio encargado de manejar las consultas relacionadas con las sedes.

#### **Controllers**

1. **HeadquarterController**
   - **Propósito**: Gestiona las operaciones relacionadas con las sedes.
   - **Endpoints**:
     - `POST /api/v1/headquarters`: Crea una nueva sede.
     - `GET /api/v1/headquarters/{headquarterId}`: Obtiene los detalles de una sede específica por su ID.
     - `GET /api/v1/headquarters`: Obtiene la lista de todas las sedes.
   - **Dependencias**:
     - `HeadquarterCommandService`: Servicio encargado de manejar los comandos relacionados con las sedes.
     - `HeadquarterQueryService`: Servicio encargado de manejar las consultas relacionadas con las sedes.

#### **Resources**

1. **CreateHeadquarterResource**
   - **Atributos**:
     - `name`, `landlinePhone`, `mobilePhone`, `latitude`, `longitude`, `street`, `number`, `city`, `postalCode`, `country`, `openingTime`, `closingTime`, `intervalMinutes`.

2. **HeadquarterResource**
   - **Atributos**:
     - `id`, `name`, `landlinePhone`, `mobilePhone`, `latitude`, `longitude`, `streetAddress`, `openingTime`, `closingTime`, `intervalMinutes`.

#### **Transformers**

1. **CreateHeadquarterCommandFromResourceAssembler**
   - Convierte `CreateHeadquarterResource` en `CreateHeadquarterCommand`.

2. **HeadquarterResourceFromEntityAssembler**
   - Convierte `Headquarter` en `HeadquarterResource`.

#### 4.2.3.3. Application Layer

<!-- Contenido del Application Layer para Branching -->

#### 4.2.3.4. Infrastructure Layer

La **Infrastructure Layer** del Branching Bounded Context proporciona las implementaciones técnicas necesarias para soportar las operaciones del sistema relacionadas con la gestión de sedes. Esta capa incluye repositorios para la persistencia de datos y componentes que conectan la lógica de negocio con los recursos externos, como bases de datos. Su objetivo principal es garantizar que las operaciones de almacenamiento y recuperación de información sean eficientes, consistentes y seguras.

#### **Persistencia (JPA Repositories)**

1. **HeadquarterRepository**
   - **Propósito**: Proporciona métodos para interactuar con la base de datos de sedes.
   - **Métodos principales**:
     - `existsByName(NameHeadquarter name)`: Verifica si existe una sede con un nombre específico.
     - `existsByCoordinates(Coordinates coordinates)`: Verifica si existe una sede en una ubicación geográfica específica.
   - **Características**:
     - Extiende `JpaRepository`, lo que permite realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) sobre las entidades `Headquarter`.
     - Facilita la validación de unicidad para nombres y coordenadas de sedes, asegurando que no haya duplicados en el sistema.


#### **Relaciones entre componentes**

- **Persistencia**: El repositorio `HeadquarterRepository` proporciona acceso a los datos almacenados en la base de datos, permitiendo a las capas superiores (como la **Application Layer**) interactuar con las entidades del dominio.
- **Validación**: Los métodos `existsByName` y `existsByCoordinates` son utilizados para validar la unicidad de las sedes durante las operaciones de creación o actualización, asegurando la consistencia de los datos.


La **Infrastructure Layer** del Branching Bounded Context asegura que las operaciones relacionadas con la persistencia de datos sean robustas y confiables. Al proporcionar un repositorio especializado para las sedes, esta capa facilita la integración con la base de datos y garantiza que las reglas de negocio, como la unicidad de nombres y ubicaciones, se cumplan de manera eficiente. Esta estructura modular y reutilizable permite que el sistema sea escalable y fácil de mantener.

#### 4.2.3.5. Bounded Context Software Architecture Component Level Diagrams

En esta sección se presenta el diagrama de componentes del **Branching Bounded Context**, el cual detalla los principales módulos y sus interacciones dentro del contexto delimitado. Este diagrama sigue el enfoque del C4 Model para representar los componentes clave, como servicios de aplicación, controladores, repositorios y servicios externos, junto con sus relaciones.

El propósito de este diagrama es proporcionar una visión clara y estructurada de cómo se organizan los componentes dentro del contexto, facilitando la comprensión de su arquitectura y permitiendo identificar puntos de integración y responsabilidades. 

<img src="" alt="Branching BC Component Diagram"/><br>

El **Branching Bounded Context** está compuesto por los siguientes módulos principales:

1. **Application Layer**:
   - Coordina las operaciones de negocio relacionadas con la gestión de sedes.
   - Incluye servicios de comandos y consultas que interactúan con la **Domain Layer** y la **Infrastructure Layer**.
   - Maneja eventos relacionados con la creación y actualización de sedes.

2. **Interface Layer**:
   - Expone los puntos de entrada al sistema a través de controladores REST.
   - Incluye recursos y transformadores que aseguran una representación adecuada de los datos y su conversión entre las capas de la aplicación.

3. **Domain Layer**:
   - Encapsula la lógica de negocio relacionada con la gestión de sedes.
   - Define los agregados, entidades y objetos de valor que representan los conceptos clave del dominio.

4. **Infrastructure Layer**:
   - Proporciona las implementaciones técnicas necesarias para soportar las operaciones del sistema.
   - Incluye repositorios para la persistencia de datos y componentes que conectan la lógica de negocio con los recursos externos, como bases de datos.


#### 4.2.3.6. Bounded Context Software Architecture Code Level Diagrams

En este apartado se presentan los diagramas que ofrecen un mayor nivel de detalle sobre la implementación de los componentes del **Branching Bounded Context**. Estos diagramas están diseñados para ilustrar cómo se estructuran las clases, interfaces y relaciones dentro de las capas del contexto, proporcionando una visión técnica que facilita el desarrollo, mantenimiento y evolución del sistema.

##### 4.2.3.6.1. Bounded Context Domain Layer Class Diagrams

El diagrama de clases correspondiente a la **Domain Layer** del **Branching Bounded Context** incluye las clases principales, como agregados, entidades y objetos de valor, así como las interfaces y enumeraciones que definen el comportamiento del dominio. También se destacan las relaciones entre estos elementos, como asociaciones, composiciones y dependencias.

El objetivo de este diagrama es proporcionar una representación detallada de la lógica de negocio encapsulada en la capa del dominio, asegurando que las reglas del negocio estén claramente definidas y alineadas con los requisitos del sistema.

<img src="" alt="Branching BC Domain Layer Class Diagram"/><br>

**Elementos principales del diagrama:**

1. **Aggregates**:
   - `Headquarter`: Agregado principal que encapsula la lógica de negocio relacionada con la gestión de sedes. Incluye atributos como `name`, `contactNumbers`, `coordinates`, `schedule` y `address`.

2. **Entities**:
   - `Schedule`: Representa los horarios de atención de una sede, incluyendo atributos como `businessHours` e `intervalMinutes`.

3. **Value Objects**:
   - `NameHeadquarter`: Representa el nombre de una sede.
   - `ContactNumbers`: Representa los números de contacto de una sede.
   - `Coordinates`: Representa las coordenadas geográficas de una sede.
   - `StreetAddress`: Representa la dirección de una sede.
   - `BusinessHours`: Representa los horarios de apertura y cierre de una sede.

**Relaciones destacadas:**
- El agregado `Headquarter` actúa como el núcleo del dominio, gestionando las relaciones con los objetos de valor (`NameHeadquarter`, `ContactNumbers`, `Coordinates`, `StreetAddress`) y la entidad `Schedule`.
- Los objetos de valor encapsulan datos inmutables y validaciones específicas, asegurando consistencia en el dominio.
- La entidad `Schedule` permite modelar horarios complejos, incluyendo intervalos de tiempo entre reservas.


##### 4.2.3.6.2. Bounded Context Database Design Diagram.

##### 4.2.3.6.2. Bounded Context Database Design Diagram

El diseño de la base de datos para el **Branching Bounded Context** refleja la estructura del dominio, asegurando que las entidades y relaciones definidas en la **Domain Layer** se representen de manera eficiente en el modelo relacional. 

[![BRANCHING-DB.jpg](https://i.postimg.cc/QC1gZxdV/db2.png)](https://i.postimg.cc/QC1gZxdV/db2.png)

**Este diseño incluye las siguientes tablas principales:**


1. **Headquarters**
   - **Propósito**: Representa las sedes registradas en el sistema.
   - **Atributos principales**:
     - `id`: Identificador único de la sede.
     - `name`: Nombre de la sede.
     - `landline_phone`: Número de teléfono fijo de la sede.
     - `mobile_phone`: Número de teléfono móvil de la sede.
     - `latitude`: Latitud de la ubicación de la sede.
     - `longitude`: Longitud de la ubicación de la sede.
     - `address_street`: Calle de la dirección de la sede.
     - `address_number`: Número de la dirección.
     - `address_city`: Ciudad donde se encuentra la sede.
     - `address_postal_code`: Código postal de la sede.
     - `address_country`: País donde se encuentra la sede.
     - `schedule_id`: Relación con la tabla `Schedules`.

2. **Schedules**
   - **Propósito**: Representa los horarios de atención de las sedes.
   - **Atributos principales**:
     - `id`: Identificador único del horario.
     - `opening_time`: Hora de apertura de la sede.
     - `closing_time`: Hora de cierre de la sede.
     - `interval_minutes`: Intervalo de tiempo en minutos entre reservas.

Este diseño asegura que las operaciones relacionadas con la gestión de sedes sean eficientes y consistentes, facilitando la integración con la lógica de negocio definida en la **Domain Layer**.




