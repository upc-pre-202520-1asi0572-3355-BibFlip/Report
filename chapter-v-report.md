# Capítulo V: Solution UI/UX Design

## 5.1. Style Guidelines

### 5.1.1. General Style Guidelines

### 5.1.2. Web, Mobile and IoT Style Guidelines

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

### 5.2.5. Navigation Systems

## 5.3. Landing Page UI Design

### 5.3.1. Landing Page Wireframe

### 5.3.2. Landing Page Mock-up

## 5.4. Applications UX/UI Design

### 5.4.1. Applications Wireframes

### 5.4.2. Applications Wireflow Diagrams

### 5.4.2. Applications Mock-ups

### 5.4.3. Applications User Flow Diagrams

## 5.5. Applications Prototyping
