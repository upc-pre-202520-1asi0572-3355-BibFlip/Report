## 4.2. Tactical-Level Domain-Driven Design

### 4.2.1. Bounded Context: IAM

El **IAM (Identity and Access Management) Bounded Context** es responsable de gestionar la autenticación y la creación de usuarios en el sistema. Este contexto asegura que los usuarios (principalmente Estudiantes, Administradores de Cubículos y Super Administradores) puedan registrarse, iniciar sesión y gestionar sus credenciales de manera segura, cumpliendo con los estándares de seguridad y privacidad.

#### 4.2.1.1. Domain Layer

La Domain Layer del IAM Bounded Context encapsula la lógica de negocio relacionada con la autenticación y la gestión de usuarios. En esta capa se definen los elementos principales del dominio: agregados, entidades y objetos de valor que representan los conceptos clave del sistema.

##### **Aggregates**
1. **User**
   - **Propósito**: El agregado principal es el usuario (`User`), que encapsula la lógica de negocio relacionada con la autenticación y la gestión de roles.
   - **Atributos**:
     - `username`: Identificador único del usuario, validado para cumplir con restricciones de longitud y unicidad.
     - `password`: Contraseña del usuario, almacenada de forma segura.
     - `roles`: Conjunto de roles asociados al usuario, representados como una relación `ManyToMany` con la entidad `Role`.
   - **Métodos**:
     - `addRole(Role role)`: Agrega un rol al usuario.
     - `addRoles(List<Role> roles)`: Agrega múltiples roles al usuario, validando que sean roles válidos.
   - **Características**:
     - Extiende `AuditableAbstractAggregateRoot`, lo que permite auditar cambios en los usuarios.
     - Gestiona la relación entre usuarios y roles, asegurando consistencia y validación.

##### **Entities**
1. **Role**
   - **Propósito**: La entidad `Role` representa los roles que pueden ser asignados a los usuarios.
   - **Atributos**:
     - `id`: Identificador único del rol.
     - `name`: Nombre del rol, representado como un valor enumerado (`Roles`).
   - **Métodos**:
     - `getDefaultRole()`: Devuelve el rol predeterminado (`ROLE_USER`).
     - `toRoleFromName(String name)`: Convierte un nombre de rol en una instancia de `Role`.
     - `validateRoleSet(List<Role> roles)`: Valida un conjunto de roles, asignando un rol predeterminado si el conjunto está vacío o es nulo.
   - **Características**:
     - Define una relación única entre los nombres de roles y sus representaciones en la base de datos.
     - Facilita la validación y asignación de roles a los usuarios.

##### **Value Objects**: 
1. **Roles**
   - **Propósito**: El objeto de valor `Roles` es una enumeración que define los roles disponibles en el sistema.
   - **Valores**:
     - `ROLE_ADMIN`: Rol de administrador.
     - `ROLE_SUPERVISOR`: Rol de supervisor.
     - `ROLE_USER`: Rol de usuario estándar.
   - **Características**:
     - Representa roles como valores inmutables, asegurando consistencia en su uso dentro del dominio.


En conjunto, estos elementos permiten modelar de manera robusta y segura la lógica de negocio relacionada con la autenticación y la gestión de usuarios, asegurando que las reglas del dominio se cumplan de manera consistente.

#### 4.2.1.2. Interface Layer

La **Interface Layer** del IAM Bounded Context expone los puntos de entrada al sistema a través de controladores REST. Estos controladores permiten la interacción con las entidades del dominio mediante solicitudes HTTP, facilitando la comunicación entre los clientes y el sistema. Además, esta capa incluye recursos y transformadores que aseguran una representación adecuada de los datos y su conversión entre las capas de la aplicación.

#### **Controllers**

Los controladores son responsables de manejar las solicitudes HTTP y delegar la lógica de negocio a los servicios correspondientes. A continuación, se describen los principales controladores:

1. **UsersController**
   - **Propósito**: Gestiona las operaciones relacionadas con los usuarios.
   - **Endpoints**:
     - `GET /api/v1/users`: Obtiene la lista de todos los usuarios.
     - `GET /api/v1/users/{userId}`: Obtiene los detalles de un usuario específico por su ID.
   - **Dependencias**:
     - `UserQueryService`: Servicio encargado de manejar las consultas relacionadas con los usuarios.

2. **RolesController**
   - **Propósito**: Gestiona las operaciones relacionadas con los roles.
   - **Endpoints**:
     - `GET /api/v1/roles`: Obtiene la lista de todos los roles disponibles.
   - **Dependencias**:
     - `RoleQueryService`: Servicio encargado de manejar las consultas relacionadas con los roles.

3. **AuthenticationController**
   - **Propósito**: Gestiona las operaciones de autenticación y registro de usuarios.
   - **Endpoints**:
     - `POST /api/v1/authentication/sign-up`: Registra un nuevo usuario en el sistema.
     - `POST /api/v1/authentication/sign-in`: Autentica a un usuario y genera un token de acceso.
   - **Dependencias**:
     - `UserCommandService`: Servicio encargado de manejar los comandos relacionados con los usuarios.

#### **Resources**

Los recursos representan los datos que se exponen a través de la API REST. Estos recursos son utilizados para estructurar las respuestas de los controladores y asegurar una representación clara y consistente de los datos. A continuación, se describen los principales recursos:

1. **UserResource**
   Representa un usuario en el sistema.
   - **Atributos**:
     - `id`: Identificador único del usuario.
     - `username`: Nombre de usuario.
     - `roles`: Lista de roles asociados al usuario.

1. **RoleResource**
   Representa un rol en el sistema.
   - **Atributos**:
     - `id`: Identificador único del rol.
     - `name`: Nombre del rol.

2. **AuthenticatedUserResource**
   Representa un usuario autenticado junto con su token de acceso.
   - **Atributos**:
     - `id`: Identificador único del usuario.
     - `username`: Nombre de usuario.
     - `token`: Token de acceso generado.

3. **SignUpResource**
   Representa los datos necesarios para registrar un nuevo usuario.
   - **Atributos**:
     - `username`: Nombre de usuario.
     - `password`: Contraseña.
     - `roles`: Lista de roles asignados al usuario.

4. **SignInResource**
   Representa los datos necesarios para autenticar a un usuario.
   - **Atributos**:
     - `username`: Nombre de usuario.
     - `password`: Contraseña.

#### **Transformers**

Los transformadores son responsables de convertir las entidades del dominio en recursos y viceversa. Esto asegura que los datos expuestos a través de la API REST sean consistentes y estén en el formato esperado. A continuación, se describen los principales transformadores:

1. **UserResourceFromEntityAssembler**
   Convierte una entidad `User` en un recurso `UserResource`.
   - **Método principal**:
     - `toResourceFromEntity(User entity)`: Transforma un usuario del dominio en un recurso.

1. **RoleResourceFromEntityAssembler**
   Convierte una entidad `Role` en un recurso `RoleResource`.
   - **Método principal**:
     - `toResourceFromEntity(Role entity)`: Transforma un rol del dominio en un recurso.

1. **AuthenticatedUserResourceFromEntityAssembler**
   Convierte una entidad `User` y un token en un recurso `AuthenticatedUserResource`.
   - **Método principal**:
     - `toResourceFromEntity(User entity, String token)`: Transforma un usuario autenticado en un recurso.

1. **SignUpCommandFromResourceAssembler**
   Convierte un recurso `SignUpResource` en un comando `SignUpCommand`.
   - **Método principal**:
     - `toCommandFromResource(SignUpResource resource)`: Transforma los datos de registro en un comando.

1. **SignInCommandFromResourceAssembler**
   Convierte un recurso `SignInResource` en un comando `SignInCommand`.
   - **Método principal**:
     - `toCommandFromResource(SignInResource resource)`: Transforma los datos de inicio de sesión en un comando.

#### **Relaciones entre componentes**

- Los controladores utilizan los servicios de consulta (`UserQueryService`, `RoleQueryService`) y de comandos (`UserCommandService`) para delegar la lógica de negocio.
- Los transformadores convierten las entidades del dominio en recursos para las respuestas HTTP y viceversa para las solicitudes entrantes.
- Los recursos estructuran los datos expuestos a los clientes, asegurando una representación clara y consistente.

Esta estructura asegura que la **Interface Layer** sea modular, reutilizable y fácil de mantener, facilitando la interacción entre los clientes y el sistema.

#### 4.2.1.3 Application Layer

La **Application Layer** del IAM Bounded Context actúa como un intermediario entre la **Domain Layer** y las capas externas, como la **Interface Layer** y la **Infrastructure Layer**. Su propósito principal es coordinar las operaciones de negocio, manejar comandos y consultas, y orquestar la lógica de aplicación sin exponer directamente los detalles del dominio.

#### **Command Services**
Los servicios de comandos son responsables de ejecutar operaciones que modifican el estado del sistema. A continuación, se describen los principales servicios de comandos:

1. **RoleCommandServiceImpl**
   - **Propósito**: Gestiona las operaciones relacionadas con los roles, como la creación inicial de roles en el sistema.
   - **Métodos principales**:
     - `handle(SeedRolesCommand command)`: Verifica si los roles predefinidos existen en el sistema y los crea si no están presentes.
   - **Dependencias**:
     - `RoleRepository`: Interactúa con la base de datos para verificar y guardar roles.

2. **UserCommandServiceImpl**
   - **Propósito**: Gestiona las operaciones relacionadas con los usuarios, como el registro y la autenticación.
   - **Métodos principales**:
     - `handle(SignUpCommand command)`: Registra un nuevo usuario en el sistema, asignándole roles y almacenando su contraseña de forma segura.
     - `handle(SignInCommand command)`: Autentica a un usuario verificando sus credenciales y generando un token de acceso.
   - **Dependencias**:
     - `UserRepository`: Interactúa con la base de datos para guardar y recuperar usuarios.
     - `HashingService`: Codifica y verifica contraseñas.
     - `TokenService`: Genera y valida tokens de acceso.
     - `RoleRepository`: Recupera roles asignados a los usuarios.

#### **Query Services**
Los servicios de consultas son responsables de recuperar información del sistema sin modificar su estado. A continuación, se describen los principales servicios de consultas:

1. **RoleQueryServiceImpl**
   - **Propósito**: Gestiona las consultas relacionadas con los roles.
   - **Métodos principales**:
     - `handle(GetAllRolesQuery query)`: Recupera todos los roles disponibles en el sistema.
     - `handle(GetRoleByNameQuery query)`: Recupera un rol específico por su nombre.
   - **Dependencias**:
     - `RoleRepository`: Interactúa con la base de datos para recuperar roles.

2. **UserQueryServiceImpl**
   - **Propósito**: Gestiona las consultas relacionadas con los usuarios.
   - **Métodos principales**:
     - `handle(GetAllUsersQuery query)`: Recupera todos los usuarios registrados en el sistema.
     - `handle(GetUserByIdQuery query)`: Recupera un usuario específico por su ID.
     - `handle(GetUserByUsernameQuery query)`: Recupera un usuario específico por su nombre de usuario.
   - **Dependencias**:
     - `UserRepository`: Interactúa con la base de datos para recuperar usuarios.

#### **Relaciones entre componentes**
- Los **Command Services** interactúan con los repositorios para modificar el estado del sistema y con los servicios externos para operaciones auxiliares, como el hashing de contraseñas y la generación de tokens.
- Los **Query Services** interactúan únicamente con los repositorios para recuperar información del sistema.

Esta estructura asegura que la **Application Layer** sea modular, reutilizable y fácil de mantener, permitiendo una separación clara de responsabilidades y facilitando la evolución del sistema.

#### 4.2.1.4. Infrastructure Layer 
La **Infrastructure Layer** del IAM Bounded Context proporciona las implementaciones técnicas necesarias para soportar las operaciones del sistema. Esta capa incluye configuraciones de seguridad, servicios de hashing, manejo de tokens, repositorios para la persistencia de datos y componentes relacionados con la autorización y autenticación. Su objetivo principal es conectar la lógica de negocio con los recursos externos, como bases de datos, servicios de seguridad y APIs externas.

#### **Persistencia (JPA Repositories)**

1. **RoleRepository**
   - **Propósito**: Proporciona métodos para interactuar con la base de datos de roles.
   - **Métodos principales**:
     - `findByName`: Busca un rol por su nombre.
     - `existsByName`: Verifica si un rol existe en la base de datos.

2. **UserRepository**
   - **Propósito**: Proporciona métodos para interactuar con la base de datos de usuarios.
   - **Métodos principales**:
     - `findByUsername`: Busca un usuario por su nombre de usuario.
     - `existsByUsername`: Verifica si un usuario existe en la base de datos.

#### **Relaciones entre componentes**
   - **Persistencia**: Los repositorios (`RoleRepository`, `UserRepository`) proporcionan acceso a los datos almacenados en la base de datos, permitiendo a las capas superiores interactuar con las entidades del dominio.

Esta estructura asegura que la **Infrastructure Layer** sea modular, reutilizable y fácil de mantener, facilitando la integración con otros sistemas y servicios externos.

#### 4.2.1.5. Bounded Context Software Architecture Component Level Diagrams

En esta sección se presenta el diagrama de componentes del **IAM Bounded Context**, el cual detalla los principales módulos y sus interacciones dentro del contexto delimitado. Este diagrama sigue el enfoque del C4 Model para representar los componentes clave, como servicios de aplicación, controladores, repositorios y servicios externos, junto con sus relaciones.

El propósito de este diagrama es proporcionar una visión clara y estructurada de cómo se organizan los componentes dentro del contexto, facilitando la comprensión de su arquitectura y permitiendo identificar puntos de integración y responsabilidades.

El **IAM Bounded Context** está compuesto por los siguientes módulos principales:

1. **Application Layer**:
   - Coordina las operaciones de negocio relacionadas con la autenticación y la gestión de usuarios.
   - Incluye servicios de comandos y consultas que interactúan con la **Domain Layer** y la **Infrastructure Layer**.
   - Maneja eventos relacionados con el registro de usuarios, la asignación de roles y la autenticación.

2. **Interface Layer**:
   - Expone los puntos de entrada al sistema a través de controladores REST.
   - Incluye recursos y transformadores que aseguran una representación adecuada de los datos y su conversión entre las capas de la aplicación.
   - Proporciona endpoints para operaciones como el registro de usuarios, la autenticación y la consulta de roles.

3. **Domain Layer**:
   - Encapsula la lógica de negocio relacionada con la autenticación y la gestión de usuarios.
   - Define los agregados, entidades y objetos de valor que representan los conceptos clave del dominio, como usuarios, roles y permisos.
   - Asegura que las reglas de negocio, como la validación de contraseñas y la asignación de roles, se cumplan de manera consistente.

4. **Infrastructure Layer**:
   - Proporciona las implementaciones técnicas necesarias para soportar las operaciones del sistema.
   - Incluye repositorios para la persistencia de datos y componentes que conectan la lógica de negocio con los recursos externos, como bases de datos y servicios de seguridad.
   - Implementa servicios auxiliares como el hashing de contraseñas y la generación de tokens de autenticación.

<img src="" alt="IAM BC Component Diagram"/><br>


#### 4.2.1.6. Bounded Context Software Architecture Code Level Diagrams

En este apartado se presentan los diagramas que ofrecen un mayor nivel de detalle sobre la implementación de los componentes del **IAM Bounded Context**. Estos diagramas están diseñados para ilustrar cómo se estructuran las clases, interfaces y relaciones dentro de las capas del contexto, proporcionando una visión técnica que facilita el desarrollo, mantenimiento y evolución del sistema.

##### 4.2.1.6.1. Bounded Context Domain Layer Class Diagrams

El diagrama de clases correspondiente a la **Domain Layer** del **IAM Bounded Context** incluye las clases principales, como agregados, entidades y objetos de valor, así como las interfaces y enumeraciones que definen el comportamiento del dominio. También se destacan las relaciones entre estos elementos, como asociaciones, composiciones y dependencias.

<img src="" alt="IAM BC Domain Layer Class Diagram"/><br>

**Elementos principales del diagrama:**

1. **Aggregates**:
   - `User`: Agregado principal que encapsula la lógica de negocio relacionada con la autenticación y la gestión de usuarios. Incluye atributos como `username`, `password` y `roles`.
     - **Atributos**:
       - `username`: Identificador único del usuario.
       - `password`: Contraseña almacenada de forma segura.
       - `roles`: Lista de roles asignados al usuario.
     - **Métodos**:
       - `addRole(Role role)`: Agrega un rol al usuario.
       - `addRoles(List<Role> roles)`: Agrega múltiples roles al usuario, validando que sean válidos.

2. **Entities**:
   - `Role`: Representa los roles que pueden ser asignados a los usuarios.
     - **Atributos**:
       - `id`: Identificador único del rol.
       - `name`: Nombre del rol.
     - **Métodos**:
       - `getDefaultRole()`: Devuelve el rol predeterminado (`ROLE_USER`).
       - `validateRoleSet(List<Role> roles)`: Valida un conjunto de roles asignados.

3. **Value Objects**:
   - `Roles`: Enumeración que define los roles disponibles en el sistema (`ROLE_ADMIN`, `ROLE_SUPERVISOR`, `ROLE_USER`).
   - `Password`: Representa la contraseña del usuario, asegurando que cumpla con las políticas de seguridad.
   - `Token`: Representa un token de autenticación generado para un usuario.

**Relaciones destacadas:**
- El agregado `User` gestiona las relaciones con la entidad `Role`, asegurando que los usuarios tengan roles válidos asignados.
- Los objetos de valor encapsulan datos inmutables y validaciones específicas, como la seguridad de contraseñas y la unicidad de roles.
- La entidad `Role` define los permisos y responsabilidades que pueden ser asignados a los usuarios.

##### 4.2.1.6.2. Bounded Context Database Design Diagram.

El diseño de la base de datos para el **IAM Bounded Context** refleja la estructura del dominio, asegurando que las entidades y relaciones definidas en la **Domain Layer** se representen de manera eficiente en el modelo relacional. 

[![IAM-DB.jpg](https://i.postimg.cc/CMqsqJsY/db4.png)](https://i.postimg.cc/CMqsqJsY/db4.png)

**Este diseño incluye las siguientes tablas principales:**

1. **Users**:
   - Representa los usuarios registrados en el sistema.
   - **Atributos principales**:
     - `id`: Identificador único del usuario.
     - `username`: Nombre de usuario único.
     - `password`: Contraseña almacenada de forma segura.
     - `created_at`: Fecha de creación del usuario.

2. **Roles**:
   - Representa los roles disponibles en el sistema.
   - **Atributos principales**:
     - `id`: Identificador único del rol.
     - `name`: Nombre del rol.

3. **UserRoles**:
   - Representa la relación entre usuarios y roles.
   - **Atributos principales**:
     - `user_id`: Identificador del usuario.
     - `role_id`: Identificador del rol.

Este diseño asegura que las operaciones relacionadas con la autenticación y la gestión de usuarios sean eficientes y consistentes, facilitando la integración con la lógica de negocio definida en la **Domain Layer**.
Voy a completar el análisis táctico de Domain-Driven Design para los bounded contexts faltantes: Cubicle Management y IoT Monitoring. Desarrollaré cada sección siguiendo la estructura que ya tiene tu informe.




