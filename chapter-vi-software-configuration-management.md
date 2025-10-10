# Capítulo VI: Product Implementation, Validation & Deployment

## 6.1. Software Configuration Management

En esta sección se establece el proceso de implementación, comprobación, despliegue y validación de la solución compuesta por los productos digitales de nuestro alcance. Este capítulo, alineado al enunciado y rúbrica del curso, cubre: configuración del entorno de desarrollo, control de código fuente, guías de estilo y la configuración de despliegue de **Landing Page**, **Web Applications**, **Web Services** y **Mobile Applications**.

<br/>

### 6.1.1. Software Development Environment Configuration

A continuación se especifica cada uno de los productos de software, que utilizamos para olaborar en el ciclo de vida y desarrollo de los productos para nuestra solución, considerando todas las herramientas utilizadas en la documentación, especificación de nuestra solución y desarrollo de software, respetando las restricciones indicadas sobre los productos de software y herramientas que debemos utilizar.

**Project Management**

| Producto de Software | Descripción | Ruta de referencia o de descarga |
|:--------------------:|:------------|:---------------------------------|
| Trello | Para el control del proyecto, asignación de tareas y actividades de cada integrante del equipo en base a nuestras User Stories. | https://www.trello.com/ |
| Google Meet | Plataforma virtual para realizar reuniones del grupo para coordinar y asignar actividades. | https://meet.google.com |
| Discord | Plataforma virtual para realizar reuniones del grupo para coordinar y asignar actividades. | https://discord.com/ |

<br>

**Requirements Management**

| Producto de Software | Descripción | Ruta de referencia o de descarga |
|:--------------------:|:------------|:---------------------------------|
| UXPressia | Elaboración de User Personas, Empathy Maps, Journey Maps e Impact Maps. | https://uxpressia.com/ |
| Miro | Elaboración de As-Is y To-Be Scenario Maps | https://miro.com/ |
| Microsoft Stream | Publicación del video que contiene todas las entrevistas realizadas | https://www.microsoft.com/es-es/microsoft-365/microsoft-stream |

<br>

**Product UX/UI Design**

| Producto de Software | Descripción | Ruta de referencia o de descarga |
|:--------------------:|:------------|:---------------------------------|
| Figma | Elaboración de Wireframes, Mock-ups y Prototypes. | https://www.figma.com |

<br>

**Software Development**

| Producto de Software | Descripción | Ruta de referencia o de descarga |
|:--------------------:|:------------|:---------------------------------|
| IntelliJ | Idea Entorno de Desarrollo Integrado (IDE) para codificación y desarrollo del lado Backend de nuestra solución. | https://www.jetbrains.com/idea/ |
| Visual Studio Code | Editor de código fuente para codificación y desarrollo de nuestra aplicación móvil. | https://code.visualstudio.com/ |
| GIT | Almacenamiento y control de versiones de código. | https://git-scm.com |
| GitHub | Gestionar GIT en un repositorio común. | https://github.com |

<br>

**Software Testing**

| Producto de Software | Descripción | Ruta de referencia o de descarga |
|:--------------------:|:------------|:---------------------------------|
| Gherkin | Lenguaje de especificación de pruebas utilizado para escribir nuestros Test en formato más legible. | https://cucumber.io/docs/gherkin/ |

<br>

**Software Deployment**

| Producto de Software | Descripción | Ruta de referencia o de descarga |
|:--------------------:|:------------|:---------------------------------|
| GitHub Pages | Despliegue de nuestra Landing Page. | https://pages.github.com/ |
| Firebase | Despliegue de nuestra aplicación web. | https://firebase.google.com/ |
| Microsoft Azure | Despliegue de servicios web. | https://azure.microsoft.com/ |

<br>

**Software Documentation**

| Producto de Software | Descripción | Ruta de referencia o de descarga |
|:--------------------:|:------------|:---------------------------------|
| Swagger | Documentación de Web Services usando OpenAPI Specification. | https://swagger.io |

<br>

### 6.1.2. Source Code Management

Para el seguimiento de modificaciones en el desarrollo de nuestra solución, utilizamos la plataforma GitHub para alojar tanto la documentación como el código de nuestros productos de software. Esta plataforma nos permite realizar seguimiento de las modificaciones en cada parte de los productos desarrollados y también la utilizaremos como sistema de control de versiones. Para asegurar que todo el equipo pueda acceder a la plataforma y que los repositorios que alojarán diferentes partes de nuestra solución sean accesibles por una misma ruta, por lo cual hemos creado una organización en GitHub con el nombre de nuestro producto.

| Organización | URL |
|:------------:|:----|
| upc-pre-202520-1asi0572-3355-BibFlip | https://github.com/upc-pre-202520-1asi0572-3355-BibFlip |

Dentro de nuestra organización en GitHub, se encuentran los repositorios correspondientes a cada uno de los productos a desarrollar.

| Producto | URL del Repositorio |
|:--------:|:--------------------|
| Landing Page | https://github.com/upc-pre-202520-1asi0572-3355-BibFlip/LandingPage |
| Web Service | https://github.com/upc-pre-202520-1asi0572-3355-BibFlip/Backend |
| Web Application | https://github.com/upc-pre-202520-1asi0572-3355-BibFlip/Web-Frontend |
| Mobile Application | https://github.com/upc-pre-202520-1asi0572-3355-BibFlip/Mobile-Frontend |

**Implementación de GitFlow**

Para el desarrollo de nuestro proyecto, implementaremos GitFlow propuesto por Vincent Driessen en "A successful Git branching model". Utilizaremos este flujo de trabajo en todos los repositorios que integran nuestra solución.

Para implementar GitFlow crearemos las siguientes ramas de trabajo en cada repositorio:

| Rama | Descripción |
|:----:|:------------|
| main | La rama principal del repositorio contiene el código inicial y estable, y solo se actualizará con versiones estables del software. Cada cambio en esta rama deberá ser revisado por todos los integrantes del equipo. |
| develop | Esta rama contendrá el código más reciente desarrollado y servirá como base para futuras versiones. Se fusionará con ramas de características "feature" y principal "main" cuando sea necesario. Los miembros del equipo podrán realizar fusiones a esta rama si lo consideran conveniente. |
| feature | Ramas que pueden crear los integrantes del equipo para el desarrollo de nuevas funciones o características. Estas ramas existen mientras la funcionalidad esté en desarrollo, pero eventualmente se deben fusionar con la rama "develop" para añadir definitivamente la nueva funcionalidad a próximas versiones. La convención de nomenclatura para esta rama puede ser cualquier nombre excepto master, develop, release o hotfix. |
| release | Esta rama se utilizará para preparar el código que incluye varias características nuevas para una nueva versión. Podrá fusionarse con las ramas "develop" y "main" después de una revisión parcial por parte del equipo. La convención de nomenclatura para esta rama debe ser release-<número>, donde <número> debe ser una secuencia de dígitos y puntos. |
| hotfixes | Esta rama nos permitirá corregir errores en el código de la rama "main". Una vez realizadas las correcciones, éstas se fusionarán tanto en la rama "main" como en la rama "develop". La convención de nomenclatura para esta rama debe ser hotfix-<número>, donde <número> debe ser una secuencia de dígitos y puntos. |

<br>

<p align="center">
    <img src="https://miro.medium.com/v2/resize:fit:1400/1*X8WN29vxbiyc3XFFfWanTA.png" width="60%" alt="Ejemplo flujo de Gitflow"/>
</p>

<br>

**Implementación de Conventional Commits**

Conventional Commits es una convención basada en los mensajes de commit en git. En nuestro contexto nos proporciona un conjunto de reglas para crear un historial de commits, ya que describe las características, correcciones y cambios importantes realizados en los mensajes de commit.

Aplicaremos Conventional Commits para los textos de mensajes de cada commit en todas las ramas de nuestros repositorio.

Los mensajes de commit deben tener la siguiente estructura:

```
<Tipo>[ámbito opcional]: <Descripción>
[Cuerpo opcional]
[pie de página opcional]
```

Durante el desarrollo de los productos asociados a nuestra solución establecemos que cada commit debe contener los siguientes elementos.

`fix`: Indica una corrección en el código base.<br>
`feat`: Introduce una nueva característica en el código base.<br>
Otros tipos basados en la convención Angular como `build:` , `chore:` , `ci:` , `docs:` , `style:` , `refactor:`, `perf:` , `test:` y otros.

Establecemos estas convenciones con el propósito de comunicar de manera clara y precisa la intención de todo lo realizado durante el desarrollo de nuestra solución, tanto a los consumidores de los repositorios como a los miembros del equipo.

<br>


### 6.1.3. Source Code Style Guide & Conventions

Para el desarrollo de nuestra propuesta de solución, el equipo utilizará las convenciones estándar para cada lenguaje durante todo el ciclo de vida del proyecto y en todos los repositorios de trabajo. A continuación, se presentan las referencias para la nomenclatura de los elementos en cada lenguaje, procurando utilizar nomenclatura en inglés y seguir buenas prácticas de programación.

| Lenguaje | Referencias y Convenciones |
|:--------:|:---------------------------|
| HTML | - Utilizar la estructura de documento propia de HTML, especificando el "DOCTYPE html". <br> - Cerrar siempre las etiquetas de autocierre con />. <br> - Utilizar minúsculas "lowercase" para los nombres de las etiquetas y atributos. <br> - Incluir atributos ALT en las imágenes para describir su contenido. <br> - Mantener una indentación consistente en el código. |
| CSS | - Utilizar unidades relativas para definir el tamaño de las imágenes. <br> - Separar las palabras con guiones en lugar de espacios o subrayados. <br> - Preferir el uso de propiedades abreviadas cuando sea posible. <br> - Emplear nombres descriptivos para las clases y los identificadores. |
| JavaScript | - Documentar el código de manera descriptiva. <br> - Utilizar nombres descriptivos para variables y funciones. <br> - Organizar el código en módulos y componentes. |
| Java | - Las clases e interfaces deben nombrarse con sustantivos en CamelCase. <br> - Organizar el código en módulos y componentes. <br> - Limitar la longitud de los métodos para que realicen una única función clara. <br> - Manejar adecuadamente las excepciones con mensajes o acciones concretas. |
| Dart | - Los nombres de variables, métodos y funciones deben comenzar con una letra minúscula y seguir la convención lowerCamelCase. <br> - Los nombres de clases, enumeraciones y tipos deben usar UpperCamelCase. <br> - Evitar crear objetos o instancias innecesarias; preferir constantes `const` cuando sea posible. <br> - Usar `late` o inicialización diferida solo cuando sea realmente necesario para optimizar recursos. <br> - Los nombres de archivos, bibliotecas y paquetes deben escribirse en minúsculas, usando guiones bajos `snake_case` para separar palabras. |
| Gherkin | Se usará la estructura "Given","When","Then","And" para escribir casos de prueba. <br> - Uso de archivos .feature para cada caso de prueba. <br> - Utilizar un Feature por funcionalidad del sistema. <br> - Describir escenarios de un uso único, lo más independiente posible de otras funcionalidades. |

<br>

### 6.1.4. Software Deployment Configuration

Se especifican pasos reproducibles para desplegar cada producto desde los repositorios. Se incluye además un **Deployment Diagram (C4)** como evidencia (captura/imagen en `docs/diagrams/deployment.png`).

**Entornos**
<table>
  <thead><tr><th>Producto</th><th>Entorno</th><th>Dominio/URL</th><th>Notas</th></tr></thead>
  <tbody>
    <tr><td>Landing</td><td>Prod</td><td><em>https://usuario.github.io/bibflip</em></td><td>GitHub Pages</td></tr>
    <tr><td>Web (Vue)</td><td>Prod</td><td><em>https://bibflip-web.web.app</em></td><td>Firebase Hosting</td></tr>
    <tr><td>Mobile</td><td>QA/Interno</td><td><em>Firebase App Distribution</em></td><td>APK/AAB para testers</td></tr>
    <tr><td>Web Services</td><td>QA/Prod</td><td><em>Azure App Service</em></td><td>Pendiente primer release</td></tr>
  </tbody>
</table>

**Variables y secretos (estándar)**
- `VITE_API_BASE_URL` (web), `API_BASE_URL` (mobile).
- Claves/IDs de Firebase (hosting/app distribution).
- Nunca en el repo: se configuran en **GitHub Secrets** / **Firebase CLI**.

**1) Landing Page (GitHub Pages)**
```bash
# Requisitos
npm i
# Build (si aplica) o commit directo para sitio estático
git checkout main
git add .
git commit -m "feat(landing): v1 sections & assets"
git push origin main

# GitHub → Settings → Pages → Deploy from branch: main / root
# Verificar URL pública
```

**2) Frontend Web (Firebase Hosting)**
```bash
# Requisitos
npm i -g firebase-tools
firebase login
firebase init hosting  # seleccionar proyecto; setea build dir: dist

# Build y Deploy
npm ci
npm run build
firebase deploy

```

**3) Mobile (Flutter/Dart)**
```bash
flutter clean
flutter pub get
flutter build apk --release
# Distribuir con Firebase App Distribution
firebase appdistribution:distribute build/app/outputs/flutter-apk/app-release.apk --app <APP_ID> --groups testers

```

**4) Web Services (Azure) — plan de despliegue**

Contenedor / App Service con pipeline de GitHub Actions.

Branch main → deploy prod; develop → slot staging.

Documentación OpenAPI expuesta en /swagger.