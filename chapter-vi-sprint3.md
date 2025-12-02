### 6.2.3. Sprint 3

#### 6.2.3.1. Sprint Planning 3


**Introducción**  
Este sprint se enfocó en el **Trabajo Final (TF)**: cerrar la integración extremo a extremo del flujo **IoT Device → Edge API → Backend → Frontends (Web + Mobile)**, estabilizar el producto y dejar lista la evidencia para la demo final (video, validaciones y despliegues en la nube).

<!-- Sprint Planning Background (formato de la rúbrica) -->
<table>
  <thead>
    <tr><th colspan="2">Sprint #</th><th>Sprint 3</th></tr>
  </thead>
  <tbody>
    <tr><td colspan="2"><strong>Sprint Planning Background</strong></td><td></td></tr>
    <tr><td>Date</td><td>YYYY-MM-DD</td><td>2025-11-20</td></tr>
    <tr><td>Time</td><td>HH:MM</td><td>20:30</td></tr>
    <tr><td>Location</td><td>(física/virtual)</td><td>Virtual</td></tr>
    <tr>
      <td>Prepared By</td><td>(Responsable del acta)</td>
      <td>Aranda Vallejos, Oscar Gabriel</td>
    </tr>
    <tr>
      <td>Attendees (to planning meeting)</td>
      <td>(Equipo)</td>
      <td>
        Aranda Vallejos, Oscar Gabriel / Bernaola Pérez, André Arturo / Gutierrez Garcia, Jose Eduardo /
        Oliveira Paucar, Mauricio / Pedraza Maldonado, Joaquin / Soriano Medrano, Diego / Velarde Luyo, Piero Alberto
      </td>
    </tr>
    <tr>
      <td colspan="3"><strong>Sprint 3 – 3 Review Summary</strong><br/>
      <em>Al cierre del Sprint 3 se consolidó la integración entre el dispositivo IoT simulado en Wokwi, el Edge API desplegado en Azure, el Backend de reservas y los frontends Web/Mobile. Se estabilizaron los flujos de reserva y disponibilidad, se completaron los escenarios de prueba de extremo a extremo y se generaron las evidencias necesarias para el Trabajo Final (video, documentación y Student Outcomes).</em></td>
    </tr>
    <tr>
      <td colspan="3"><strong>Sprint 3 – 3 Retrospective Summary</strong><br/>
      <em>El equipo identificó que la mayor complejidad se concentró en la integración IoT–Backend, por lo que se incrementó el uso de pair programming y sesiones de depuración conjunta. También se mejoró la disciplina de ramas y pull requests para evitar conflictos en la etapa final. Como mejora futura se propone adelantar actividades de integración y validación en sprints anteriores, para reducir el riesgo acumulado en el último sprint.</em></td>
    </tr>
    <tr><td colspan="3"><strong>Sprint Goal &amp; User Stories / Technical Stories</strong></td></tr>
    <tr>
      <td>Sprint 3 Goal</td>
      <td>(SMART)</td>
      <td>
        En un período máximo de dos semanas, completar la integración en producción de la solución
        BibFlip, conectando los datos del dispositivo IoT (ocupación de cubículos) con el Edge API y el Backend,
        exponiendo dicha información en los frontends Web y Mobile y dejando un entorno estable para la demo
        del Trabajo Final, con pruebas automatizadas y documentación actualizada.
      </td>
    </tr>
    <tr><td>Sprint 3 Velocity</td><td>(Story Points)</td><td><strong>30 SP</strong></td></tr>
    <tr>
      <td>Sum of Story Points</td>
      <td>(stories incluidos)</td>
      <td><strong>30 SP</strong> (TS008=8, TS009=10, TS010=12)</td>
    </tr>
  </tbody>
</table>

#### 6.2.3.2. Aspect Leaders and Collaborators.

En este sprint se reforzó un **liderazgo distribuido** orientado a la integración y estabilización del producto.

| Aspecto                                   | Líder                                      | Colaboradores                                                                 |
|-------------------------------------------|--------------------------------------------|-------------------------------------------------------------------------------|
| Planificación y coordinación del Sprint   | Aranda Vallejos, Oscar Gabriel             | Todo el equipo                                                                |
| Integración IoT (Wokwi + Firmware)        | Velarde Luyo, Piero Alberto                | Gutierrez Garcia, Jose Eduardo / Soriano Medrano, Diego                       |
| Edge API & Routing de datos               | Soriano Medrano, Diego                     | Bernaola Pérez, André Arturo / Pedraza Maldonado, Joaquin                     |
| Backend de reservas & cubículos           | Bernaola Pérez, André Arturo               | Pedraza Maldonado, Joaquin / Oliveira Paucar, Mauricio                        |
| Frontend Web (estado en tiempo real)      | Pedraza Maldonado, Joaquin                 | Aranda Vallejos, Oscar Gabriel / Velarde Luyo, Piero Alberto                  |
| App Mobile (visualización de reserva)     | Gutierrez Garcia, Jose Eduardo             | Pedraza Maldonado, Joaquin                                                    |

#### 6.2.3.3. Sprint Backlog 3.


#### 6.2.3.3. Sprint Backlog 3

Durante este sprint se priorizaron **historias técnicas** relacionadas con la integración IoT, la observabilidad del sistema y el cierre de la experiencia de usuario para el demo final del TF.

**URL público de Trello:** <https://trello.com/b/htxHDgrX/bibflip>

<table>
  <thead>
    <tr>
      <th>Sprint #</th>
      <th colspan="7">Sprint 3</th>
    </tr>
    <tr>
      <th colspan="2">Technical Story</th>
      <th colspan="6">Work-Item / Task</th>
    </tr>
    <tr>
      <th>Id</th>
      <th>Title</th>
      <th>Id</th>
      <th>Title</th>
      <th>Description</th>
      <th>Estimation (Hours)</th>
      <th>Assigned To</th>
      <th>Status</th>
    </tr>
  </thead>
  <tbody>
    <!-- TS008 -->
    <tr>
      <td>TS008</td>
      <td>Integrar dispositivo IoT con Edge API y Backend</td>
      <td>TA1</td>
      <td>Ajustar lectura de sensores y payload</td>
      <td>Refinar la lógica de lectura de peso/ocupación y el formato del JSON enviado al Edge API.</td>
      <td>04</td>
      <td>Piero Velarde, Diego Soriano</td>
      <td>Done</td>
    </tr>
    <tr>
      <td></td><td></td>
      <td>TA2</td>
      <td>Conectar Edge API con servicios de cubículos</td>
      <td>Mapear las lecturas IoT a las entidades de cubículo y actualizar su estado en el Backend.</td>
      <td>04</td>
      <td>Diego Soriano, André Bernaola</td>
      <td>Done</td>
    </tr>
    <tr>
      <td></td><td></td>
      <td>TA3</td>
      <td>Validar flujo end-to-end</td>
      <td>Verificar que los cambios de ocupación se reflejen en Web y Mobile en tiempo casi real.</td>
      <td>02</td>
      <td>Jose Gutierrez, Joaquin Pedraza</td>
      <td>To Review</td>
    </tr>
    <!-- TS009 -->
    <tr>
      <td>TS009</td>
      <td>Implementar monitoreo, health-checks y logging</td>
      <td>TA1</td>
      <td>Extender endpoints de salud</td>
      <td>Agregar métricas y estados de salud para Edge API y Backend (latencia, conectividad, errores).</td>
      <td>03</td>
      <td>André Bernaola</td>
      <td>Done</td>
    </tr>
    <tr>
      <td></td><td></td>
      <td>TA2</td>
      <td>Configurar logs de integración IoT</td>
      <td>Registrar eventos clave de recepción y procesamiento de lecturas IoT.</td>
      <td>03</td>
      <td>Diego Soriano</td>
      <td>Done</td>
    </tr>
    <tr>
      <td></td><td></td>
      <td>TA3</td>
      <td>Panel básico de monitoreo</td>
      <td>Preparar consultas y visualizaciones simples (logs, estados) para revisión en la demo.</td>
      <td>02</td>
      <td>Oscar Aranda</td>
      <td>In Process</td>
    </tr>
    <!-- TS010 -->
    <tr>
      <td>TS010</td>
      <td>Cierre de experiencia de usuario y demo TF</td>
      <td>TA1</td>
      <td>Ajustar vistas de disponibilidad</td>
      <td>Refinar UI Web/Mobile para mostrar claramente cubículos libres/ocupados y reservas activas.</td>
      <td>04</td>
      <td>Joaquin Pedraza, Jose Gutierrez</td>
      <td>Done</td>
    </tr>
    <tr>
      <td></td><td></td>
      <td>TA2</td>
      <td>Grabar video About-the-Product</td>
      <td>Preparar guion y grabar el flujo principal del sistema para el video del TF.</td>
      <td>03</td>
      <td>Piero Velarde, Mauricio Oliveira</td>
      <td>Done</td>
    </tr>
    <tr>
      <td></td><td></td>
      <td>TA3</td>
      <td>Actualizar documentación y Student Outcome</td>
      <td>Incorporar evidencias finales en el informe, Student Outcome y anexos.</td>
      <td>03</td>
      <td>Mauricio Oliveira, Oscar Aranda</td>
      <td>Done</td>
    </tr>
  </tbody>
</table>

<br>

#### 6.2.3.4. Development Evidence for Sprint Review.

Orgnaizacion del github: [`https://github.com/upc-pre-202520-1asi0572-3355-BibFlip`]()

<table>
  <thead>
    <tr>
      <th>Repository</th><th>Branch</th><th>Commit Id</th><th>Commit Message</th><th>Commit Message Body</th><th>Committed on (Date)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>LandingPage</td><td>main</td>
      <td><em>82d64e</em></td>
      <td>feat: update features section</td>
      <td>-</td>
      <td><em>02/12/25</em></td>
    </tr>
    <tr>
      <td>Web-Frontend</td>
      <td>develop</td>
      <td><em>7d4676f</em></td>
      <td>feat: update sign in request</td>
      <td>-</td>
      <td><em>6/11/25</em></td>
    </tr>
    <tr>
      <td>Mobile-Frontend</td>
      <td>develop</td>
      <td><em>420d355</em></td>
      <td>feat: update cubicle bookings hours</td>
      <td>-</td>
      <td><em>8/10/25</em></td>
    </tr>
    <tr>
      <td>Edge-Api-Platform</td>
      <td>main</td>
      <td><em>e881e0d</em></td>
      <td>Feat: Implement connection with backend and persistence to database</td>
      <td>-</td>
      <td><em>15/11/25</em></td>
    </tr>
    <tr>
      <td>ESP32-BibFlip-Embedded-System</td>
      <td>main</td>
      <td><em>a11c3d0</em></td>
      <td>Feat: Update project from wokwi</td>
      <td>-</td>
      <td><em>15/11/25</em></td>
    </tr>
    <tr>
      <td>Backend</td>
      <td>production</td>
      <td><em>95baaea</em></td>
      <td>Feat: Put time zone config commented</td>
      <td>-</td>
      <td><em>15/11/25</em></td>
    </tr>
    <tr>
      <td>Backend</td>
      <td>production</td>
      <td><em>e63579</em></td>
      <td>Feat: Reupdate the time zone for better sincronization with edge api</td>
      <td>-</td>
      <td><em>15/11/25</em></td>
    </tr>
  </tbody>
</table>

#### 6.2.3.5. Testing Suite Evidence for Sprint Review.
US17- Registro de cuenta de administrador
[![f45dea48-c4e2-469e-8c2d-02a741f6c54c.jpg](https://i.postimg.cc/pdMX6cs9/f45dea48-c4e2-469e-8c2d-02a741f6c54c.jpg)](https://postimg.cc/BjN08p9s)

#### 6.2.3.6. Execution Evidence for Sprint Review.

- **Landing Page:**

  ![landing-1](https://i.postimg.cc/KzF5tXmT/Captura-de-pantalla-2025-10-10-020020.png)  
  ![landing-2](https://i.postimg.cc/VkC9Ts6D/Captura-de-pantalla-2025-10-10-020056.png)

- **Web Application:**
 
  [![image.png](https://i.postimg.cc/SNKCZH67/image.png)](https://postimg.cc/14L8XCYf)
  [![image.png](https://i.postimg.cc/CKJmBbSs/image.png)](https://postimg.cc/CZBj9BZR)
  [![image.png](https://i.postimg.cc/R0nZqLcT/image.png)](https://postimg.cc/R34BDfp3)
  [![image.png](https://i.postimg.cc/RhPBgW7M/image.png)](https://postimg.cc/kRtz4XYZ)
  [![image.png](https://i.postimg.cc/5N6dxN5p/image.png)](https://postimg.cc/SJFtd4vz)
  [![image.png](https://i.postimg.cc/wv0ZpS7P/image.png)](https://postimg.cc/1nVJ070c)
  [![image.png](https://i.postimg.cc/mgCnDcPp/image.png)](https://postimg.cc/G43KgmJv)

- **Web Services:**

  [![image.png](https://i.postimg.cc/BQQDbRtC/image.png)](https://postimg.cc/DmHmYjrW)

- **Mobile (Flutter):**

  ![mobile-1](https://i.postimg.cc/jdWkxb2b/Captura-de-pantalla-2025-10-10-020731.png)  
  ![mobile-2](https://i.postimg.cc/cLBzjc6J/Captura-de-pantalla-2025-10-10-020835.png)

- **Link video de visualización y navegación logrado en este Sprint:**  
  <https://upcedupe-my.sharepoint.com/:v:/g/personal/u202114793_upc_edu_pe/IQBQVqiIknnEQJsNC2lEwg3qAc-pBdSmVQ8qelqnrxa_ty0?e=HGXPdd&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D>

<br>

#### 6.2.3.7. Services Documentation Evidence for Sprint Review.

En esta sección se presenta los principales endpoints de la API del sistema, desarrollados para este Sprint, organizados por bounded context como autenticación, recuperación de contraseña, reservas, cubículos, sedes, usuarios y la gestión de supervisores. Su documentación busca ofrecer una referencia clara para comprender las acciones disponibles, los parámetros requeridos y las respuestas esperadas en cada operación, facilitando así el desarrollo, la integración y el mantenimiento de nuestra solución.

**Sedes y Supervisores**

| Acción |	Verbo	| Endpoint |	Parámetros |	Ejemplo	| Response |
|:-------|--------|----------|:------------|:---------|:---------|
| Asignar supervisor | POST | /api/v1/headquarters/{headquarterId}/supervisors/{supervisorId} | Path: headquarterId, supervisorId | POST /api/v1/headquarters/1/supervisors/5 | Mensaje de éxito |
| Remover supervisor | DELETE | /api/v1/headquarters/{headquarterId}/supervisors/{supervisorId} | Path: headquarterId, supervisorId | DELETE /api/v1/headquarters/1/supervisors/5 | Mensaje de éxito |
| Obtener supervisores | GET | /api/v1/headquarters/{headquarterId}/supervisors | Path: headquarterId | GET /api/v1/headquarters/1/supervisors | Lista de supervisores |
| Obtener sede por supervisor | GET | /api/v1/headquarters/supervisors/{supervisorId} | Path: supervisorId | GET /api/v1/headquarters/supervisors/5 | Datos de la sede asignada |

**Autenticación**

| Acción |	Verbo	| Endpoint |	Parámetros |	Ejemplo	| Response |
|:-------|--------|----------|:------------|:---------|:---------|
| Registro | POST | /api/v1/authentication/sign-up | Body: { name, email, password } | POST /api/v1/authentication/sign-up con JSON en el cuerpo | Usuario creado con token de autenticación |
| Inicio de sesión | POST | /api/v1/authentication/sign-in | Body: { email, password } | POST /api/v1/authentication/sign-in | Devuelve token y datos del usuario |

**Recuperación de Contraseña**

| Acción |	Verbo	| Endpoint |	Parámetros |	Ejemplo	| Response |
|:-------|--------|----------|:------------|:---------|:---------|
| Solicitar recuperación | POST | /api/v1/password-recovery/request | Body: { email } | POST /api/v1/password-recovery/request | Mensaje de confirmación de envío de correo |
| Confirmar recuperación | POST | /api/v1/password-recovery/confirm | Body: { token, newPassword } | POST /api/v1/password-recovery/confirm | Mensaje de éxito o error |

**Reservas**

| Acción |	Verbo	| Endpoint |	Parámetros |	Ejemplo	| Response |
|:-------|--------|----------|:------------|:---------|:---------|
| Listar reservas | GET | /api/v1/bookings | Ninguno | GET /api/v1/bookings | Lista de reservas |
| Crear reserva | POST | /api/v1/bookings | Body: { clientId, cubicleId, date, time } | POST /api/v1/bookings | Reserva creada |
| Obtener reserva | GET | /api/v1/bookings/{id} | Path: id | GET /api/v1/bookings/10 | Detalles de la reserva |
| Eliminar reserva | DELETE | /api/v1/bookings/{id} | Path: id | DELETE /api/v1/bookings/10 | Mensaje de éxito |
| Reservas por cliente | GET | /api/v1/bookings/client/{clientId} | Path: clientId | GET /api/v1/bookings/client/3 | Lista de reservas del cliente |

**Cubículos**

| Acción |	Verbo	| Endpoint |	Parámetros |	Ejemplo	| Response |
|:-------|--------|----------|:------------|:---------|:---------|
| Listar cubículos | GET |	/api/v1/cubicles | Ninguno	| GET /api/v1/cubicles |	Lista de cubículos |
| Crear cubículo	| POST	| /api/v1/cubicles	| Body: { name, headquarterId, availability }	| POST /api/v1/cubicles	| Cubículo creado |
| Actualizar estado |	PATCH |	/api/v1/cubicles/{cubicleId}/status	| Body: { status } | PATCH /api/v1/cubicles/4/status | Estado actualizado |
| Actualizar disponibilidad |	PATCH |	/api/v1/cubicles/{cubicleId}/availability-slot/status	| Body: { slotId, status } | PATCH /api/v1/cubicles/4/availability-slot/status | Slot actualizado |
| Obtener cubículo	| GET	| /api/v1/cubicles/{cubicleId} |	Path: cubicleId	| GET /api/v1/cubicles/4 | Detalles del cubículo |
| Eliminar cubículo |	DELETE |	/api/v1/cubicles/{cubicleId} |	Path: cubicleId	| DELETE /api/v1/cubicles/4 |	Mensaje de éxito |
| Horario del cubículo |	GET |	/api/v1/cubicles/{cubicleId}/schedule |	Path: cubicleId	| GET /api/v1/cubicles/4/schedule |	Lista de horarios |
| Cubículos por sede |	GET |	/api/v1/cubicles/headquarter/{headquarterId} | Path: headquarterId |	GET /api/v1/cubicles/headquarter/1 |	Lista de cubículos en la sede |

**Sedes**

| Acción |	Verbo	| Endpoint |	Parámetros |	Ejemplo	| Response |
|:-------|--------|----------|:------------|:---------|:---------|
| Listar sedes |	GET |	/api/v1/headquarters	| Ninguno	| GET /api/v1/headquarters |	Lista de sedes |
| Crear sede |	POST |	/api/v1/headquarters |	Body: { name, address, openingTime, closingTime } |	POST /api/v1/headquarters |	Sede creada |
| Obtener sede |	GET |	/api/v1/headquarters/{headquarterId} |	Path: headquarterId	| GET /api/v1/headquarters/1 | Detalles de la sede |

**Roles y Usuarios**

| Acción |	Verbo	| Endpoint |	Parámetros |	Ejemplo	| Response |
|:-------|--------|----------|:------------|:---------|:---------|
| Listar roles |	GET |	/api/v1/roles |	Ninguno	| GET /api/v1/roles |	Lista de roles |
| Listar usuarios |	GET |	/api/v1/users |	Ninguno	| GET /api/v1/users |	Lista de usuarios |
| Obtener usuario |	GET |	/api/v1/users/{userId} |	Path: userId |	GET /api/v1/users/7 |	Detalles del usuario |

**IoT Edge**

| Acción | Verbo HTTP | Endpoint | Parámetros | Ejemplo | Response |
|--------|------------|----------|------------|---------|----------|
| Registrar dispositivo | POST | /api/v1/devices/register | Body: { "device_id": "string", "location": "string", "type": "string" } | POST /api/v1/devices/register Body: { "device_id": "chair-001", "location": "Sala A", "type": "sensor" } | Device registered successfully |
| Actualizar lectura | POST | /api/v1/devices/{device_id}/readings | Path: device_id Body: { "temperature": number, "humidity": number, "occupied": boolean } | POST /api/v1/devices/chair-001/readings Body: { "temperature": 22.5, "humidity": 45, "occupied": true } | Reading updated |
| Obtener dispositivos disponibles | GET | /api/v1/devices/status/available | Ninguno | GET /api/v1/devices/status/available | Available |
| Obtener dispositivos ocupados | GET | /api/v1/devices/status/occupied | Ninguno | GET /api/v1/devices/status/occupied | Sala C, Occupied |
| Verificar salud del backend | GET | /api/v1/devices/health/backend | Ninguno | GET /api/v1/devices/health/backend | Status: ok, Timestamp: 2025-11-14T18:00:00Z |
| Verificar dispositivos offline | POST | /api/v1/devices/maintenance/check-offline | Ninguno | POST /api/v1/devices/maintenance/check-offline | Status: "offline" |
| Obtener dispositivo por ID | GET | /api/v1/devices/{device_id} | Path: device_id | GET /api/v1/devices/chair-001 | device_id: "chair-001" |
| Eliminar dispositivo | DELETE | /api/v1/devices/{device_id} | Path: device_id | DELETE /api/v1/devices/chair-001 | Device deleted |
| Obtener todos los dispositivos | GET | /api/v1/devices/ | Ninguno | GET /api/v1/devices/ | device_id: "chair-001", ... |
| Verificar salud general | GET | /health | Ninguno | GET /health | status: "ok" |

<br>

**Imagen de documentación con OpenAPI:**  
[![image.png](https://i.postimg.cc/BQQDbRtC/image.png)](https://postimg.cc/DmHmYjrW)
[![image.png](https://i.postimg.cc/XvnNVBVH/image.png)](https://postimg.cc/zyPY7BHK)

**URL de documentación desplegada de Web Services:**  
  <https://bibflip-api-platform.azurewebsites.net/swagger-ui/index.html>

**URL de documentación desplegada de IoT Edge:**  
  <https://bibflip-edge-api-platform.azurewebsites.net/api/docs>

**URL del repositorio de Web Services:**  
  <https://github.com/upc-pre-202520-1asi0572-3355-BibFlip/Backend>

**URL del repositorio de IoT Edge:**  
  <https://github.com/upc-pre-202520-1asi0572-3355-BibFlip/Edge-Api-Platform>

<br>

#### 6.2.3.8. Software Deployment Evidence for Sprint Review.

- **Landing Page:**

  GitHub Pages — URL: [`https://upc-pre-202520-1asi0572-3355-bibflip.github.io/LandingPage/`](https://upc-pre-202520-1asi0572-3355-bibflip.github.io/LandingPage/)

  ![landing-2](https://i.postimg.cc/VkC9Ts6D/Captura-de-pantalla-2025-10-10-020056.png)

- **Web Application:**

  Firebase Hosting — URL: [`https://bib-flip-web-app-2025-02.web.app/`](https://bib-flip-web-app-2025-02.web.app/)
  
  [![image.png](https://i.postimg.cc/mknq5JD4/image.png)](https://postimg.cc/CnjmZvkr)
  
  1. Construir aplicación Vue  
    Genera la carpeta dist lista para producción:
    ```bash
    npm run build
    ```
  2. Inicializar Firebase en el proyecto  
    Dentro de la carpeta del proyecto ejecuta:
    ```bash
    firebase init
    ```
  3. Desplegar la aplicación
    ```bash
    Desplegar la aplicación
    ```
  
  [![image.png](https://i.postimg.cc/CKJmBbSs/image.png)](https://postimg.cc/CZBj9BZR)

- **Mobile Application:**

  Build APK de pruebas internas.

  ![mobile-1](https://i.postimg.cc/jdWkxb2b/Captura-de-pantalla-2025-10-10-020731.png)  
  ![mobile-2](https://i.postimg.cc/cLBzjc6J/Captura-de-pantalla-2025-10-10-020835.png)

- **Web Services y IoT Edge:**

  Web Services — URL: [`https://bibflip-api-platform.azurewebsites.net/swagger-ui/index.html`](https://bibflip-api-platform.azurewebsites.net/swagger-ui/index.html)

  IoT Edge — URL: [`https://bibflip-edge-api-platform.azurewebsites.net/api/docs`](https://bibflip-edge-api-platform.azurewebsites.net/api/docs)

  [![azure.jpg](https://i.postimg.cc/NFQf0y7Y/azure.jpg)](https://postimg.cc/xJFSx14F)
  [![image.png](https://i.postimg.cc/CLmdz4Q2/image.png)](https://postimg.cc/HV8TNbH0)
  [![image.png](https://i.postimg.cc/XvnNVBVH/image.png)](https://postimg.cc/zyPY7BHK)

<br>

#### 6.2.3.9. Team Collaboration Insights during Sprint.
