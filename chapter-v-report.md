# Capítulo V: Solution UI/UX Design

## 5.1. Style Guidelines

En este apartado se establecen los principios de interacción y visuales que regulan la experiencia completa en la plataforma Bib Flip, garantizando así una coherencia entre las distintas plataformas. Utilizando la tipografía, los colores, el espaciado, la iconografía y un tono de comunicación unificado, establecemos una identidad visual definida.

### 5.1.1. General Style Guidelines

#### Branding

Para representar nuestro producto Bibflip, se desarrolló un logo que fusiona elementos clave de nuestra propuesta de valor: un libro abierto que simboliza el conocimiento y los espacios académicos, junto con una estrella de cuatro puntas en su interior. Esta combinación visual transmite de forma inmediata la naturaleza del producto como una plataforma de gestión de reservas de cubículos estudiantiles con un enfoque innovador y accesible.

El libro, elemento universal asociado al estudio, la biblioteca y el aprendizaje, se convierte en un símbolo dinámico gracias a la estrella que lo corona. Esta estrella comunica la idea de excelencia, destacar y facilitar la experiencia del usuario. Juntos, estos elementos representan a Bibflip como la solución que ilumina el camino hacia espacios de estudio organizados y fácilmente reservables.

[![Group-1.png](https://i.postimg.cc/9fMHWTHY/Group-1.png)](https://postimg.cc/dhzx6h1h)

##### Variantes del Logo

- **Versión Light**: Fondo gris claro (#D3D3D3) con icono en negro, transmitiendo claridad y accesibilidad
- **Versión Primary**: Fondo en tonalidad naranja/marrón cálido (#D4844A), reflejando calidez académica y profesionalismo
- **Versión Dark**: Fondo oscuro (#2A2A2A) con icono en blanco cremoso (#F5F5DC), para contextos digitales premium

##### Aplicación

El logo de Bibflip representa la modernidad aplicada a la gestión educativa: simplificando la reserva de espacios de estudio y permitiendo que los estudiantes se enfoquen en lo que realmente importa: su aprendizaje.


#### Tipografía

- Fuente: Inter
- Tamaños: Seleccionar entre los tamaños disponibles para asegurar una legibilidad adecuada en diferentes dispositivos y tamaños de pantalla.
- Espaciado entre letras y líneas: Ajustar según sea necesario para mejorar la legibilidad, especialmente en textos largos.

[![tipografia.png](https://i.postimg.cc/T3g5Pqk3/tipografia.png)](https://postimg.cc/tsR4SPQK)

#### Paleta de colores

[![section-colors.png](https://i.postimg.cc/d359tM92/section-colors.png)](https://postimg.cc/vx6n3NkT)

#### Colores Principales

| Nombre | Código Hex | Uso | Opacidad |
|--------|-----------|-----|---------|
| Dark Charcoal | #2A2A2A | Textos principales, encabezados | 100% |
| Brown Primary | #634729 | Botones principales, elementos interactivos | 100% |
| Mauve | #755D60 | Acentos secundarios, bordes | 100% |
| Brown Secondary | #805E48 | Hover states, variaciones de botones | 100% |
| Warm Tan | #916749 | Estados activos, elementos destacados | 100% |
| Light Tan | #916953 | Fondos claros, backgrounds secundarios | 100% |

#### Colores Neutros

| Nombre | Código Hex | Uso | Opacidad |
|--------|-----------|-----|---------|
| Dark Gray | #96959B | Textos secundarios, placeholders | 100% |
| Blanco | #AABBB6 | Fondos alternativos, spaces | 100% |
| Light Gray | #ACABBB3 | Bordes, divisores | 100% |
| Very Light Gray | #ADAAB3 | Fondos muy claros | 100% |
| Off-White | #F7F9F4 | Fondos principales, espacios limpios | 100% |

### 5.1.2. Web, Mobile and IoT Style Guidelines

#### Estados y Componentes

**Botones y Acciones:**
- Color base: #634729 (Brown Primary)
- Hover: #805E48 (Brown Secondary)
- Activo: #916749 (Warm Tan)

**Tags/Badges (Disponible):**
- Background: #916953 (Light Tan)
- Texto: Blanco (#FFFFFF)

**Fondos y Containers:**
- Fondo principal: #F7F9F4 (Off-White)
- Cards/Containers: Blanco (#FFFFFF)
- Bordes: #96959B (Dark Gray)

#### Significado y Uso

La paleta de **tonos tierra y marrón** transmite calidez, confianza y profesionalismo, perfecta para la temática de biblioteca y espacios compartidos. Los tonos neutros proporcionan equilibrio visual y facilitan la legibilidad. Los acentos en colores tierra crean jerarquía visual sin ser intrusivos.

#### Ejemplo de Interfaz

**Bibflip - San Miguel Cubículos:**
- Navbarra: Blanco (#FFFFFF)
- Headers: Dark Charcoal (#2A2A2A)
- Botones "Reservar": #634729 (Brown Primary)
- Tags "Disponible": #916953 (Light Tan) con texto blanco
- Fondos de página: #F7F9F4 (Off-White)
- Cards de cubículos: Blanco (#FFFFFF) con bordes sutiles

[![Cubiculos-Estudiante.png](https://i.postimg.cc/fb3W8YFt/Cubiculos-Estudiante.png)](https://postimg.cc/JyLWnHRM)

[![Cubiculos.png](https://i.postimg.cc/GpZMD1G9/Cubiculos.png)](https://postimg.cc/FfVgt8PQ)

# 5.2. Information Architecture

## 5.2.1. Organization Systems

Para Bibflip, hemos implementado sistemas de organización que facilitan la navegación y acceso a la información tanto para estudiantes como para administradores. Estos sistemas están diseñados para proporcionar una experiencia de usuario intuitiva y eficiente.

### Sistema jerárquico

Organizamos la información en Bibflip siguiendo una estructura jerárquica clara:

**Para estudiantes:**

El proceso comienza en la Landing Page, donde los usuarios son redirigidos a la aplicación web o móvil según su preferencia. Una vez allí, los estudiantes pueden registrarse o iniciar sesión con sus credenciales, accediendo a un panel principal que les muestra información relevante como reservas activas, sedes disponibles y servicios de la biblioteca, incluyendo información sobre cubículos y salas grupales. Para realizar una reserva, los estudiantes seleccionan una sede, visualizan los cubículos disponibles en tiempo real y completan un formulario con los detalles de su reserva, como fecha, hora aproximada de estadía y cubículo específico. Además, pueden ubicar la sede en un mapa integrado para mayor comodidad.

**Para administradores:**

Por otro lado, los administradores acceden a un panel de gestión después de iniciar sesión. Desde allí, pueden administrar los cubículos de las sedes, agregando nuevos o eliminando los existentes mediante un formulario sencillo. También tienen acceso a información detallada de las sedes y pueden visualizar las reservas de diferentes maneras: por cubículo, por estudiante o en una lista completa. Esto les permite mantener un control eficiente sobre las operaciones del centro de estudio.

**Para superadministradores:**

Los superadministradores tienen acceso completo al sistema. Pueden registrar nuevos administradores asignándoles sedes específicas, crear nuevas sedes en el sistema, y visualizar toda la información consolidada de usuarios, sedes y reservas para realizar pruebas y monitoreo general del sistema.

### Sistema secuencial

También implementamos una organización secuencial para procesos específicos:

**Proceso de reserva:**
1. Selección de sede
2. Visualización de cubículos disponibles en tiempo real
3. Selección de cubículo
4. Selección de hora aproximada de estadía
5. Confirmación de reserva

**Proceso de gestión de cubículos:**
1. Visualización del inventario actual de cubículos
2. Selección de acción (agregar/eliminar)
3. Introducción de datos del cubículo (identificador, capacidad)
4. Confirmación de la operación

**Proceso de registro de administrador:**
1. Acceso del superadmin al módulo de administradores
2. Selección de "Agregar administrador"
3. Ingreso de credenciales del nuevo administrador
4. Asignación de sede específica
5. Confirmación del registro

## 5.2.2. Labeling Systems

Antes de implementar las etiquetas en nuestra plataforma, determinamos qué requisitos necesitamos cumplir. Las etiquetas nos permiten agregar información contextual a diferentes elementos de la plataforma Bibflip. A continuación, se detalla el sistema de etiquetado implementado:

### Etiquetas para cubículos

| Etiqueta | Descripción |
|----------|-------------|
| [DISPONIBLE] | Cubículo que puede ser reservado en este momento |
| [OCUPADO] | Cubículo actualmente en uso por estudiantes |
| [RESERVADO] | Cubículo con reserva activa pendiente de ocupación |

### Etiquetas para reservas

| Etiqueta | Descripción |
|----------|-------------|
| [ACTIVA] | Reserva en curso (dentro del rango horario seleccionado) |
| [EXPIRADA] | Reserva que ya ha finalizado su período de vigencia |
| [PENDIENTE] | Reserva programada para uso futuro |

### Etiquetas para servicios de biblioteca

| Etiqueta | Descripción |
|----------|-------------|
| [CUBÍCULOS] | Espacios individuales de estudio |
| [SALAS GRUPALES] | Espacios para trabajo colaborativo |
| [COMPUTADORAS] | Equipos de cómputo disponibles |

### Etiquetas para nivel de ocupación

| Etiqueta | Descripción |
|----------|-------------|
| [ALTA DISPONIBILIDAD] | Más del 50% de cubículos disponibles |
| [DISPONIBILIDAD MEDIA] | Entre 20% y 50% de cubículos disponibles |
| [BAJA DISPONIBILIDAD] | Menos del 20% de cubículos disponibles |
| [COMPLETO] | Sin cubículos disponibles |

### Etiquetas para notificaciones de sistema

| Etiqueta | Descripción |
|----------|-------------|
| [ÉXITO] | Confirmación de operación completada exitosamente |
| [ERROR] | Problema durante una operación |
| [ADVERTENCIA] | Mensaje de precaución o limitación del sistema |
| [ACTUALIZACIÓN] | Cambio en disponibilidad detectado por sensores |

Este sistema de etiquetas proporciona contexto visual inmediato y mejora la comprensión de la información presentada tanto para estudiantes como para administradores.


### 5.2.3. SEO Tags and Meta Tags

La implementación adecuada de etiquetas SEO es crucial para mejorar la visibilidad de Bibflip en los motores de búsqueda.
### Título
Indica el tema de la página, debe ser corto y descriptivo, manteniéndose entre 55-60 caracteres.
```html
<title>Bibflip - Sistema de Gestión de Cubículos para Bibliotecas Universitarias</title>
```
### Descripción
Breve descripción del propósito de la plataforma.<br>
```html
<meta name="description" content="Bibflip optimiza la gestión de espacios en bibliotecas universitarias con tecnología IoT, visualización en tiempo real de cubículos disponibles y reservas digitales. ¡Mejora la experiencia de estudio!"/>
```
### Robots
Indican a los motores de búsqueda qué hacer con la página.
```html
<meta name="robots" content="index, follow">
```
### Tipo de contenido
Útil para que los motores de búsqueda identifiquen el idioma de la página.
```html
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<meta http-equiv="Content-Language" content="es">
```
### Viewport Meta Tag
Crucial para asegurar que el contenido se vea bien en dispositivos móviles.
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
### Open Graph Tags
Para mejorar la apariencia cuando se comparte en redes sociales.
```html
<meta property="og:title" content="Bibflip - Gestión Inteligente para Bibliotecas Universitarias">
<meta property="og:description" content="Sistema IoT para optimizar la ocupación de cubículos en centros de estudio">
<meta property="og:image" content="https://bibflip.com/images/bibflip-preview.jpg">
<meta property="og:url" content="https://bibflip.com">
<meta property="og:type" content="website">
```
### Keywords
Aunque tienen menor importancia actualmente, aún pueden ser útiles.
```html
<meta name="keywords" content="reservas bibliotecas, cubículos disponibles, IoT bibliotecas, gestión centros estudio, sistema reservas tiempo real, ocupación cubículos, bibliotecas universitarias, espacios estudio">

```


### 5.2.4. Searching Systems
El sistema de búsqueda propuesto para Bibflip permitirá a los usuarios encontrar fácilmente información relevante según sus necesidades específicas.

### Sistema de búsqueda para estudiantes
 Nombre del filtro | Descripción |
|-------------------|-------------|
| Ubicación | El usuario podrá filtrar bibliotecas por distrito o zona de la ciudad |
| Disponibilidad inmediata | Muestra sólo las bibliotecas con cubículos disponibles en el momento actual |
| Capacidad | Permite filtrar por tipo de espacio (individual, grupal, con computadora) |
| Horario de atención | Filtra por bibliotecas abiertas en un rango horario específico |
| Distancia | Ordena los resultados desde la ubicación actual del usuario |
| Nivel de ocupación | Filtra sedes por porcentaje de disponibilidad (alta, media, baja) |

### Sistema de búsqueda para administradores

| Nombre del filtro | Descripción |
|-------------------|-------------|
| Búsqueda por número de cubículo | Permite encontrar rápidamente información de un cubículo específico |
| Búsqueda por nombre de estudiante | Localiza reservas realizadas por un estudiante específico |
| Filtro por fecha | Busca reservas en un rango de fechas específico |
| Estado de cubículo | Filtra por estado: disponible, ocupado, reservado |
| Historial de reservas | Busca en el histórico de reservas completadas |

### Sistema de búsqueda para superadministradores

| Nombre del filtro | Descripción |
|-------------------|-------------|
| Búsqueda de administradores | Localiza administradores por nombre o sede asignada |
| Búsqueda de sedes | Encuentra sedes específicas en el sistema |
| Visualización global | Accede a estadísticas consolidadas de todas las sedes |

### Características adicionales del sistema de búsqueda

- **Búsqueda en tiempo real**: Los resultados se actualizan automáticamente cada 5 segundos mediante datos de sensores IoT.
- **Historial de búsquedas**: Mantiene un registro de búsquedas recientes del usuario.
- **Sugerencias automáticas**: Ofrece resultados mientras el usuario escribe.
- **Filtros combinados**: Permite aplicar múltiples filtros simultáneamente.

Este sistema de búsqueda está diseñado para ser intuitivo y proporcionar resultados precisos, mejorando así la experiencia del usuario y la eficiencia operativa de la plataforma Bibflip.



### 5.2.5. Navigation Systems

El sistema de navegación de la plataforma Bibflip guiará a los usuarios a través de las distintas secciones y pantallas, proporcionándoles acceso intuitivo a todas las funcionalidades. A continuación, se detallan los elementos que facilitan la navegación de los usuarios:

### Navegación global

| Nombre | Descripción |
|--------|-------------|
| Inicio | Página principal que muestra un resumen de la información relevante según el tipo de usuario |
| Perfil | Permite al usuario gestionar su información personal y preferencias |
| Notificaciones | Alertas sobre reservas, actualizaciones de disponibilidad o mensajes del sistema |

### Navegación para estudiantes

| Nombre | Descripción |
|--------|-------------|
| Explorar sedes | Muestra todas las bibliotecas disponibles con información sobre ubicación y disponibilidad en tiempo real |
| Mi reserva | Permite al usuario ver su reserva activa con detalles de horario, sede y número de cubículo |
| Sedes | Visualización de todas las sedes del centro de estudio con opción de ver en mapa |
| Ver servicios | Acceso al reglamento y servicios del centro de estudio (cubículos, salas grupales, etc.) |
| Mapa | Visualización geográfica de las sedes en un mapa interactivo |

### Navegación para administradores

| Nombre | Descripción |
|--------|-------------|
| Dashboard | Panel principal con indicadores clave sobre la operación de la sede asignada |
| Gestión de cubículos | Interfaz para agregar, eliminar o modificar cubículos en la sede asignada |
| Visualizar reservas | Visualización y gestión de las reservas actuales y futuras con filtros por estudiante o cubículo |
| Mi sede | Información detallada de la sede asignada al administrador |

### Navegación para superadministradores

| Nombre | Descripción |
|--------|-------------|
| Panel completo | Acceso a todas las funcionalidades del sistema |
| Administradores | Módulo para registrar y gestionar administradores con asignación de sedes |
| Gestión de sedes | Crear, editar y visualizar todas las sedes del sistema |
| Usuarios | Visualización completa de estudiantes, administradores y sus actividades |

### Elementos de navegación

- **Menú principal**: Barra de navegación fija en la parte superior que contiene los enlaces principales según el rol del usuario.
- **Menú lateral desplegable**: Para acceso a funciones secundarias, configuraciones y cierre de sesión.
- **Botones de acción flotantes**: Para acciones principales como "Realizar reserva" o "Agregar cubículo".
- **Breadcrumbs**: Indicadores de ubicación dentro de la jerarquía de navegación.
- **Gestos táctiles**: En la versión móvil, se implementan gestos como deslizar para ver más opciones o pellizcar para ampliar el mapa.

### Patrones de navegación

- **Hub and spoke**: La pantalla principal actúa como centro desde donde se accede a las diferentes funcionalidades específicas del rol.
- **Navegación por pestañas**: Para alternar entre diferentes vistas de una misma categoría (ej: cubículos disponibles vs. ocupados).
- **Navegación jerárquica**: Para profundizar en detalles (sede → cubículos → reservas → detalles de estudiante).
- **Desplazamiento infinito**: En listados de sedes o cubículos para cargar más resultados al desplazarse.
- **Navegación contextual**: Botones y acciones que aparecen según el estado del sistema (ej: "Reservar" solo si hay disponibilidad).

### Características de accesibilidad

- **Indicadores visuales claros**: Uso de colores y etiquetas para mostrar estados de disponibilidad.
- **Actualización automática**: Los indicadores de disponibilidad se actualizan en menos de 5 segundos según datos de sensores.
- **Prevención de errores**: El sistema impide reservar si ya existe una reserva activa del estudiante.
- **Confirmaciones**: Mensajes de confirmación para acciones críticas como eliminar cubículos o cancelar reservas.

Este sistema de navegación está diseñado para ser consistente, intuitivo y adaptable a diferentes dispositivos, asegurando que los usuarios puedan encontrar rápidamente la información o funcionalidad que necesitan sin esfuerzo excesivo. La estructura se adapta dinámicamente según el rol del usuario (estudiante, administrador o superadministrador), mostrando únicamente las opciones relevantes para cada perfil.


## 5.3. Landing Page UI Design

### 5.3.1. Landing Page Wireframe

En esta sección se presenta el wireframe de la landing page de Bibflip, una representación estructural inicial que organiza los principales bloques de contenido del sitio sin incluir aún detalles gráficos. Su propósito es definir la jerarquía informativa y el flujo de navegación que guiará al usuario durante su experiencia en la página. Este esquema permite visualizar la distribución de secciones como el encabezado, la introducción al proyecto, las características principales, los beneficios y la sección de contacto. El diseño se centra en la claridad y coherencia de la información, garantizando que el visitante pueda comprender rápidamente el objetivo de Bibflip: ofrecer una plataforma que optimiza la reserva de cubículos mediante tecnología IoT dentro de la Universidad Peruana de Ciencias Aplicadas (UPC).

El wireframe fue elaborado en Figma y define la estructura inicial de la landing page.  

[Ver Wireframe en Figma](https://www.figma.com/design/MFD4yVEhDz2ChR78iE3x6B/Bibflip---Landing-page---Wirefame?node-id=0-1&t=3enJg2TmsN7kH5Jd-1)

### 5.3.2. Landing Page Mock-up

El mockup de la landing page de Bibflip muestra una versión visual refinada y cercana al diseño final. En esta etapa se aplico una tipografía legible y una composición equilibrada. Este diseño busca comunicar el propósito central del proyecto: mejorar la experiencia de los estudiantes en la gestión de espacios de estudio mediante una interfaz moderna, intuitiva y atractiva. Las secciones del mockup incluyen una presentación clara de la solución propuesta, los beneficios de Bibflip y un llamado a la acción enfocado en conocer más sobre la aplicación. Con ello se refleja una propuesta visual profesional y funcional, alineada con los valores de innovación y comunidad universitaria.

[![Captura-de-pantalla-2025-10-09-233857.png](https://i.postimg.cc/L8G7tfFc/Captura-de-pantalla-2025-10-09-233857.png)](https://postimg.cc/VJBD1J6g)

[![Captura-de-pantalla-2025-10-09-234009.png](https://i.postimg.cc/rp6n0k5v/Captura-de-pantalla-2025-10-09-234009.png)](https://postimg.cc/Wdn6CxWn)

[![Captura-de-pantalla-2025-10-09-234035.png](https://i.postimg.cc/rspQXFLt/Captura-de-pantalla-2025-10-09-234035.png)](https://postimg.cc/N9W1RtFg)

[![Captura-de-pantalla-2025-10-09-234108.png](https://i.postimg.cc/0ySZqBLv/Captura-de-pantalla-2025-10-09-234108.png)](https://postimg.cc/Js1jNPrY)

[![Captura-de-pantalla-2025-10-09-234149.png](https://i.postimg.cc/7YGngRPq/Captura-de-pantalla-2025-10-09-234149.png)](https://postimg.cc/TpxbxCWs)

[![Captura-de-pantalla-2025-10-09-234233.png](https://i.postimg.cc/G2gvDFZB/Captura-de-pantalla-2025-10-09-234233.png)](https://postimg.cc/BLD89KZs)

El mockup fue elaborado en Figma y presenta la propuesta visual final antes de la implementación. 

[Ver Mock-up en Figma](https://www.figma.com/design/lFAHFEcpJcJSknycAs0GBe/Bibflip---Landing-page---Mockup?node-id=0-1&t=GOQTIyM7Krw6Y7tg-1)



## 5.4. Applications UX/UI Design

En esta sección se documenta el diseño de la aplicación de Bib Flip, la cual cuenta con su versión web y móvil. La versión web contará con interfaces y páginas personalizadas para cada tipo de usuario (Administrador, Supervisor y Estudiante); sin embargo, la aplicación móvil solo contará con pantallas para los estudiantes. Además, la adición de esta versión de la aplicación para dispositivos móviles es necesaria porque permite cumplir con los objetivos del proyecto y con las historias de usuario de los sprints correspondientes.

### 5.4.1. Applications Wireframes
En esta sección se presentan los wireframes de la aplicación Bibflip, tanto para la versión web como para la versión móvil. Los wireframes son esquemas visuales de baja fidelidad que muestran la estructura básica de las pantallas, la disposición de los elementos y la jerarquía de la información, sin incluir detalles gráficos finales. Su objetivo es definir la organización de los contenidos y la navegación entre las diferentes secciones, permitiendo validar la lógica de interacción antes de avanzar a etapas de diseño visual más detalladas. 

#### Web Application Wireframes
Los wireframes de la aplicación web contemplan las vistas principales para cada tipo de usuario: Administrador, Supervisor y Estudiante. Incluyen pantallas como el panel principal (dashboard), gestión de cubículos, visualización de reservas, perfil de usuario y navegación entre sedes. Cada wireframe muestra la ubicación de menús, botones de acción, tablas de información y formularios, asegurando una experiencia de usuario clara y eficiente para cada rol sin entrar demasiado en detalle. Para poder visualizar el conjunto de wireframes se proporciona el siguiente enlace: [Enlace-Web-Application-Wireframes-Figma](https://www.figma.com/design/36XnbJB9ljpI3viqruRiML/Bib-Flip?node-id=0-1)

##### Pantallas Generales

[![Inicio-de-Sesi-n.png](https://i.postimg.cc/8ckzBxgm/Inicio-de-Sesi-n.png)](https://postimg.cc/FdqvhWRY)

Los 3 tipos de usuario podrán iniciar sesión ingresando su usuario y contraseña previamente registrados.<br>

[![Registro.png](https://i.postimg.cc/nrVhYNf1/Registro.png)](https://postimg.cc/R68mvsF3)

Al ser esta una pantalla totalmente pública y accedida por cualquier usuario de internet, los administradores y supervisores no podrán registrarse de esta manera por razones de seguridad. De esta manera se evita que cualquier agente externo pueda crearse una cuenta de administrador y sabotear el sistema. Por lo tanto, esta pantalla de registro tendrá la funcionalidad de registrar nuevos estudiantes.<br>

---

##### Pantallas para Administrador

[![Home-Administrador.png](https://i.postimg.cc/RFB79CwM/Home-Administrador.png)](https://postimg.cc/B8mLB0hy)

Este es el menú inicial del administrador que observa tras iniciar sesión.<br>

[![Dashboard-Sedes-Admin.png](https://i.postimg.cc/j5bHKqyx/Dashboard-Sedes-Admin.png)](https://postimg.cc/sBTQ4rnq)

Al presionar el botón "Gestionar Sedes", el administrador es dirigido a esta pantalla donde podrá agregar una sede nueva.<br>

[![Dashboard-Sedes-Admin-1.png](https://i.postimg.cc/0QsYx575/Dashboard-Sedes-Admin-1.png)](https://postimg.cc/WD5Fwv9x)

Al presionar el botón de supervisores, el administrador podrá crearle una cuenta al supervisor y asignarle una sede.<br>

[![Dashboard-Sedes-Admin-2.png](https://i.postimg.cc/FR4ymF0h/Dashboard-Sedes-Admin-2.png)](https://postimg.cc/FfTdV4P6)

En esta pantalla el administrador podrá ver al supervisor por sede asignado. <br>

---

##### Pantallas para Supervisor

[![Home-Supervisor.png](https://i.postimg.cc/ZRHdS8Tf/Home-Supervisor.png)](https://postimg.cc/G8B2PsTY)

Este el menú inicial que verá el supervisor tras iniciar sesión en la aplicación web.<br>

[![Gesti-n-de-Reservas-Supervisor.png](https://i.postimg.cc/C17qgGFm/Gesti-n-de-Reservas-Supervisor.png)](https://postimg.cc/KkKz7g3M)

En este apartado el supervisor podrá visualizar las reservas por estudiante.<br>

[![Gesti-n-de-Reservas-Supervisor-1.png](https://i.postimg.cc/fLC9Ncw8/Gesti-n-de-Reservas-Supervisor-1.png)](https://postimg.cc/KkKz7g3T)

En este apartado el supervisor podrá visualizar las reservas por cubículo.<br>

[![Gesti-n-de-Cub-culos-Supervisor.png](https://i.postimg.cc/JnxkLN1K/Gesti-n-de-Cub-culos-Supervisor.png)](https://postimg.cc/vg1B76x6)

En esta pantalla podrá gestionar los cubiculos, es decir agregarlos, editarlos o eliminarlos.<br>

---

##### Pantallas para estudiante

[![Home-Estudiante.png](https://i.postimg.cc/xdt6sbw1/Home-Estudiante.png)](https://postimg.cc/v1x7TD8J)

Este será el menú inicial que verá el estudiante tras iniciar sesión. En este apartado podrá ver sus reservas más recientes y cancelarlas. <br>

[![Formulario-para-ver-Detalles-de-Reserva-Estudiante.png](https://i.postimg.cc/XvQs2yTR/Formulario-para-ver-Detalles-de-Reserva-Estudiante.png)](https://postimg.cc/rdRGszyj)

Al seleccionar la opción de ver una reserva, el estudiante podrá ver estos detalles. <br>

[![Reservaci-n-Estudiante.png](https://i.postimg.cc/JhPpTBfr/Reservaci-n-Estudiante.png)](https://postimg.cc/674VqT6g)

Al seleccionar el botón del navbar que dice "Reservar", el estudiante verá este apartado. En esta página tendrá la opción de dirigirse a ver el mapa de la sede o continuar a la reserva de cubículos. <br>

[![Mapa-Estudiante.png](https://i.postimg.cc/d045WTbq/Mapa-Estudiante.png)](https://postimg.cc/v1x7TD8j)

Este apartado muestra el mapa de la sede para que nuevos estudiantes puedan ubicarse mejor. <br>

[![Cub-culos-Estudiante.png](https://i.postimg.cc/tg2BrVK9/Cub-culos-Estudiante.png)](https://postimg.cc/d7ZR3DQf)

Este apartado muestra los cubículos disponibles para reservar. <br>

[![Formulario-para-Reservar-Cub-culo-Estudiante.png](https://i.postimg.cc/tg2BrVKH/Formulario-para-Reservar-Cub-culo-Estudiante.png)](https://postimg.cc/v1x7TD8P)

Al querer reservar un cubículo, el estudiante podrá ver los horarios disponibles y efectuar la reserva. <br>

---

#### Mobile Application Wireframes

Los wireframes de la aplicación móvil están enfocados en la experiencia del estudiante. Incluyen pantallas como inicio de sesión, panel principal, exploración de sedes, visualización de cubículos disponibles, detalles de reserva, historial de reservas y perfil. El diseño prioriza la simplicidad y la facilidad de uso en dispositivos móviles, con menús accesibles, botones grandes y navegación intuitiva adaptada a pantallas táctiles. Para poder visualizar el conjunto de wireframes se proporciona el siguiente enlace: [Enlace-Mobile-Application-Wireframes-Figma](https://www.figma.com/design/36XnbJB9ljpI3viqruRiML/Bib-Flip?node-id=1-2)

[![Inicio-de-sesi-n.png](https://i.postimg.cc/GtWRHfKK/Inicio-de-sesi-n.png)](https://postimg.cc/ctB2zXVt)

En este apartado el inicio de sesión es exclusivo para estudiantes. <br>

[![Registro.png](https://i.postimg.cc/9062rkb1/Registro.png)](https://postimg.cc/SYf3PDwz)

Esta imagen expresa la pantalla de registro para la aplicación móvil con los mismos parámetros que la aplicación web. El registro por este medio seguirá siendo igualmente solo para estudiantes. <br>

[![Home.png](https://i.postimg.cc/7hF4fR9M/Home.png)](https://postimg.cc/JH5vFP9G)

Esta será la pantalla inicial que verá el estudiante tras iniciar sesión. En ella podrá darle click a la sede San Miguel para acceder a los cubículos. Además, podrá seleccionar la tarjeta de reservas activas para ver todas sus reservas.

[![Home-1.png](https://i.postimg.cc/br7Ps5g9/Home-1.png)](https://postimg.cc/rRN3HQvD)

Este será un apartado secundario para acceder a los cubículos de la sede San Miguel.

[![Ver-cubiculos.png](https://i.postimg.cc/J0f8GFxQ/Ver-cubiculos.png)](https://postimg.cc/sG4qLwtB)

Este apartado se utilizará para todos los cubículos disponibles en la sede San Miguel. <br>

[![Mapbox.png](https://i.postimg.cc/zvsNVQ7j/Mapbox.png)](https://postimg.cc/RJLyYXj6)

Esta pantalla se utilizará para visualizar el mapa de la sede San Miguel. <br>

[![Reservacion-de-cubiculos.png](https://i.postimg.cc/prhxVvf6/Reservacion-de-cubiculos.png)](https://postimg.cc/m1sKV06Y)

Esta pantalla se utilizará para reservar cubículos en un horario disponible. <br>


### 5.4.2. Applications Wireflow Diagrams
En esta sección se presentan los wireflows de la aplicación, que combinan wireframes con diagramas de flujo para ilustrar cómo los usuarios navegan entre las diferentes pantallas y funcionalidades. Los wireflows permiten visualizar los posibles caminos de interacción, las decisiones del usuario y las respuestas del sistema, facilitando la identificación de mejoras en la experiencia de usuario y la detección de posibles bloqueos o redundancias en la navegación.

<!-- En Proceso -->


### 5.4.3. Applications Mock-ups
Aquí se muestran los mockups de alta fidelidad de la aplicación Bibflip, tanto para la versión web como móvil. Los mockups representan el diseño visual final, incluyendo tipografía, colores, iconografía y disposición precisa de los elementos.

#### Web App Mock-ups

En el siguiente enlace se desarrollaron los mock-ups:
[Enlace-Vista-Web-App-Mockups](https://www.figma.com/design/36XnbJB9ljpI3viqruRiML/Bib-Flip?node-id=1-3)

##### Pantallas Generales

[![Inicio-de-sesi-n.png](https://i.postimg.cc/sxvHG9gQ/Inicio-de-sesi-n.png)](https://postimg.cc/hQR1Hmxc)

Los 3 tipos de usuario podrán iniciar sesión ingresando su usuario y contraseña previamente registrados.<br>

[![Registro.png](https://i.postimg.cc/Fz7CkgHY/Registro.png)](https://postimg.cc/fSQf6dXs)

Al ser esta una pantalla totalmente pública y accedida por cualquier usuario de internet, los administradores y supervisores no podrán registrarse de esta manera por razones de seguridad. De esta manera se evita que cualquier agente externo pueda crearse una cuenta de administrador y sabotear el sistema. Por lo tanto, esta pantalla de registro tendrá la funcionalidad de registrar nuevos estudiantes.<br>

---

##### Pantallas para Administrador

[![Home-Administrativo.png](https://i.postimg.cc/7PGp6wGc/Home-Administrativo.png)](https://postimg.cc/5jJPKcmq)

Este es el menú inicial del administrador que observa tras iniciar sesión.<br>

[![Dashboard-Sedes-Admin.png](https://i.postimg.cc/8kJq5NJY/Dashboard-Sedes-Admin.png)](https://postimg.cc/xqQsprPG)

Al presionar el botón de supervisores, el administrador podrá crearle una cuenta al supervisor y asignarle una sede.<br>

[![Asignaci-n-de-supervisor-a-una-sede.png](https://i.postimg.cc/kM6k4q6N/Asignaci-n-de-supervisor-a-una-sede.png)](https://postimg.cc/nMxdS81M)

En esta pantalla el administrador puede gestionar y visualizar al supervisor que fue asignado a una sede.

---

##### Pantallas para Supervisor

[![Home-Panel-de-Supervisor.png](https://i.postimg.cc/jj6SByK2/Home-Panel-de-Supervisor.png)](https://postimg.cc/94M27RDH)

Este el menú inicial que verá el supervisor tras iniciar sesión en la aplicación web.<br>

[![Reservas-de-la-sede-por-Estudiante.png](https://i.postimg.cc/tgd48Fys/Reservas-de-la-sede-por-Estudiante.png)](https://postimg.cc/mcD4HzP4)

En este apartado el supervisor podrá visualizar las reservas por estudiante.<br>

[![Reservas-de-la-sede-por-cub-culo.png](https://i.postimg.cc/1z03bDPf/Reservas-de-la-sede-por-cub-culo.png)](https://postimg.cc/KKzbMk12)

En este apartado el supervisor podrá visualizar las reservas por cubículo.<br>

[![Gesti-n-de-Cub-culos-1.png](https://i.postimg.cc/Lsk8GjRY/Gesti-n-de-Cub-culos-1.png)](https://postimg.cc/06QvwMzP)

[![Gesti-n-de-cubiculos-2.png](https://i.postimg.cc/8CdzxLDz/Gesti-n-de-cubiculos-2.png)](https://postimg.cc/4KdG97mD)

En esta pantalla el supervisor podrá gestionar los cubiculos, es decir agregarlos, editarlos o eliminarlos.<br>

---

##### Pantallas para estudiante

[![Home-Reservas-Estudiante.png](https://i.postimg.cc/y8jVPsTW/Home-Reservas-Estudiante.png)](https://postimg.cc/fV3nW4ph)

Este será el menú inicial que verá el estudiante tras iniciar sesión. En este apartado podrá ver sus reservas más recientes y cancelarlas. <br>

[![Detalles-de-la-Reserva-Estudiante.png](https://i.postimg.cc/RZ4SKNwt/Detalles-de-la-Reserva-Estudiante.png)](https://postimg.cc/fJqQhW2W)

Al seleccionar la opción de ver una reserva, el estudiante podrá ver estos detalles. <br>

[![Menu-antes-de-reservar-Estudiante.png](https://i.postimg.cc/zG8zKVTK/Menu-antes-de-reservar-Estudiante.png)](https://postimg.cc/TpNvX273)

Al seleccionar en la opción del navbar que dice "Reservar", el estudiante verá este apartado. En esta página podrá seleccionar la opción de ver el mapa de la sede o continuar a la reserva de cubículos. <br>

[![Mapa-de-la-sede-Estudiante.png](https://i.postimg.cc/XY4jdp9f/Mapa-de-la-sede-Estudiante.png)](https://postimg.cc/F7CXQFWz)

Este apartado muestra el mapa de la sede para que nuevos estudiantes puedan ubicarse mejor. <br>

[![Cubiculos-Ver-Estudiante.png](https://i.postimg.cc/Bn4SHX2D/Cubiculos-Ver-Estudiante.png)](https://postimg.cc/gntbPcSk)

Este apartado muestra los cubículos disponibles para reservar. <br>

[![Horarios-disponibles-Estudiante.png](https://i.postimg.cc/Qdh81Hc9/Horarios-disponibles-Estudiante.png)](https://postimg.cc/D8p3Kfjn)

Al querer reservar un cubículo, el estudiante podrá ver los horarios disponibles y efectuar la reserva. <br>

---

#### Mobile Application Mock-ups

En el siguiente enlace se desarrollaron los mock-ups:
[Enlace-Vista-Mobile-App-Mockups](https://www.figma.com/design/36XnbJB9ljpI3viqruRiML/Bib-Flip?node-id=1-4)

[![Inicio-de-sesi-n.png](https://i.postimg.cc/g2WVhqM2/Inicio-de-sesi-n.png)](https://postimg.cc/VdK0QMQx)

En este apartado el inicio de sesión es exclusivo para estudiantes. <br>

[![Registro.png](https://i.postimg.cc/Sxh697ZK/Registro.png)](https://postimg.cc/JGpHVJCw)

Esta imagen expresa la pantalla de registro para la aplicación móvil con los mismos parámetros que la aplicación web. El registro por este medio seguirá siendo igualmente solo para estudiantes. <br>

[![Home.png](https://i.postimg.cc/vZsrnLP8/Home.png)](https://postimg.cc/VdK0QMQ2)

Esta será la pantalla inicial que verá el estudiante tras iniciar sesión. En ella podrá darle click a la sede San Miguel para acceder a los cubículos. Además, podrá seleccionar la tarjeta de reservas activas para ver todas sus reservas.

[![Sedes.png](https://i.postimg.cc/jSbHfQ8s/Sedes.png)](https://postimg.cc/dL5ZPdPX)

Este será un apartado secundario para acceder a los cubículos de la sede San Miguel.

[![Cubiculos.png](https://i.postimg.cc/GpZMD1G9/Cubiculos.png)](https://postimg.cc/FfVgt8PQ)

Este apartado se utilizará para todos los cubículos disponibles en la sede San Miguel. <br>

[![Mapbox.png](https://i.postimg.cc/nhJ4mYdz/Mapbox.png)](https://postimg.cc/7fKJ87r8)

Esta pantalla se utilizará para visualizar el mapa de la sede San Miguel. <br>

[![Reservacion-de-cubiculos.png](https://i.postimg.cc/vZsrnLPb/Reservacion-de-cubiculos.png)](https://postimg.cc/1fvVh6hj)

Esta pantalla se utilizará para reservar cubículos en un horario disponible. <br>


### 5.4.4. Applications User Flow Diagrams
En esta sección se documentan los diagramas de flujo de usuario (user flows) para los principales procesos dentro de la aplicación, como la reserva de cubículos, la gestión de sedes y la administración de usuarios. Los user flows muestran los pasos que sigue un usuario desde el inicio hasta la finalización de una tarea específica, identificando puntos clave de decisión, validaciones y retroalimentación del sistema. Estos diagramas ayudan a optimizar la experiencia y asegurar que los procesos sean intuitivos y eficientes.



[![Captura-de-pantalla-2025-10-10-010357.png](https://i.postimg.cc/wjMmLfXj/Captura-de-pantalla-2025-10-10-010357.png)](https://postimg.cc/fV4yhvqG)

## 5.5. Applications Prototyping
En esta sección se describen los prototipos desarrollados para Bibflip. Estos permiten simular la navegación y las principales funcionalidades tanto en la versión web como móvil.

<!-- En Proceso -->
