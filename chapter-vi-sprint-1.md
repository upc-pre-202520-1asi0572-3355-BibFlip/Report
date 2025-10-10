## 6.2. Landing Page, Services & Applications Implementation

### 6.2.1. Sprint 1

#### 6.2.1.1. Sprint Planning 1

**Introducción**  
Este sprint se orientó a entregar la primera versión navegable de la **Landing Page (HTML/CSS/JS)**, el **Frontend Web (Vue 3 + PrimeVue)** y la **App Mobile (Flutter/Dart)**, cumpliendo con los entregables solicitados para TP1.

<!-- Sprint Planning Background (formato de la rúbrica) -->
<table>
  <thead>
    <tr><th colspan="2">Sprint #</th><th>Sprint 1</th></tr>
  </thead>
  <tbody>
    <tr><td colspan="2"><strong>Sprint Planning Background</strong></td><td></td></tr>
    <tr><td>Date</td><td>YYYY-MM-DD</td><td>2025-10-05</td></tr>
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
      <td colspan="3"><strong>Sprint 1 – 1 Review Summary</strong><br/><em>No aplica (proyecto inicia en Sprint 1).</em></td>
    </tr>
    <tr>
      <td colspan="3"><strong>Sprint 1 – 1 Retrospective Summary</strong><br/><em>No aplica (proyecto inicia en Sprint 1).</em></td>
    </tr>
    <tr><td colspan="3"><strong>Sprint Goal &amp; User Stories</strong></td></tr>
    <tr>
      <td>Sprint 1 Goal</td>
      <td>(SMART)</td>
      <td>
        Entregar la <strong>v1 navegable</strong> de: 
        (1) Landing Page (GitHub Pages), 
        (2) Frontend Web (Vue 3 + PrimeVue) en Firebase Hosting, 
        (3) App Mobile (Flutter) con navegación base y pantallas Home/Reservas; 
        evidenciar navegación y despliegues.
      </td>
    </tr>
    <tr><td>Sprint 1 Velocity</td><td>(Story Points)</td><td><strong>30 SP</strong></td></tr>
    <tr>
      <td>Sum of Story Points</td>
      <td>(stories incluidos)</td>
      <td><strong>30 SP</strong> (US001=2, US002=2, US003=2, US004=3, US005=3, US006=5, US007=8, US009=5)</td>
    </tr>
  </tbody>
</table>


#### 6.2.1.2. Aspect Leaders and Collaborators


| Miembro                                      | GitHub Username     | Landing | Frontend Web (Vue + PrimeVue) | Mobile (Flutter/Dart) |
|---------------------------------------------|------------|:------:|:-----------------------------:|:---------------------:|
| **Aranda Vallejos, Oscar Gabriel**          | OscarGAV | **L**  | C                             | C                     |
| **Bernaola Pérez, André Arturo**            | Andorla0 | C      | **L**                         | C                     |
| **Gutierrez Garcia, Jose Eduardo**          | Elcrackje | C      | C                             | **L**                 |
| **Oliveira Paucar, Mauricio**               | Mauricio-nn | C      | C                             | C                     |
| **Pedraza Maldonado, Joaquin**              | JoaquinPedraza1 | C      | C                             | C                     |
| **Soriano Medrano, Diego**                  | diego5m | C      | **L**                         | C                     |
| **Velarde Luyo, Piero Alberto**             | P1er0VL | C      | C                             | C                     |


#### 6.2.1.3. Sprint Backlog 1

<table>
  <thead>
    <tr>
      <th>ID</th><th>Título</th><th>Epic</th><th>Tipo</th><th>SP</th><th>Estado</th><th>Notas</th>
    </tr>
  </thead>
  <tbody>
    <!-- Landing -->
    <tr><td>US001</td><td>Ver sección “¿Qué es Bibflip?”</td><td>EPIC-LANDING-001</td><td>Feature</td><td><em>—</em></td><td>Hecho</td><td>Landing</td></tr>
    <tr><td>US002</td><td>Ver “Características clave”</td><td>EPIC-LANDING-001</td><td>Feature</td><td><em>—</em></td><td>Hecho</td><td>Landing</td></tr>
    <tr><td>US003</td><td>Ver galería virtual</td><td>EPIC-LANDING-001</td><td>Feature</td><td><em>—</em></td><td>Hecho</td><td>Landing</td></tr>
    <tr><td>US004</td><td>Formulario de contacto</td><td>EPIC-LANDING-001</td><td>Feature</td><td><em>—</em></td><td>Hecho</td><td>Validaciones básicas</td></tr>
    <!-- Frontend Web -->
    <tr><td>US007</td><td>Disponibilidad de cubículos en tiempo real</td><td>EPIC-CLIENT-002</td><td>Feature</td><td><em>—</em></td><td>UI (mock)</td><td>PrimeVue; sin backend</td></tr>
    <tr><td>US009</td><td>Ver sedes en un mapa</td><td>EPIC-CLIENT-002</td><td>Feature</td><td><em>—</em></td><td>UI (mock)</td><td>Pop-up / placeholder</td></tr>
    <tr><td>US005</td><td>Ver servicios de una sede</td><td>EPIC-CLIENT-002</td><td>Feature</td><td><em>—</em></td><td>UI (mock)</td><td>Listado y filtros</td></tr>
    <!-- Mobile -->
    <tr><td>US006</td><td>Visualizar reserva activa</td><td>EPIC-CLIENT-002</td><td>Feature</td><td><em>—</em></td><td>UI (mock)</td><td>Home muestra estado</td></tr>
    <tr><td>US008</td><td>Reservar un cubículo</td><td>EPIC-CLIENT-002</td><td>Feature</td><td><em>—</em></td><td>UI (mock)</td><td>Flujo base sin backend</td></tr>
  </tbody>
</table>

<blockquote>
<strong>Nota:</strong> SP (Story Points) y Velocity del Sprint pendientes de estimación formal del equipo.
</blockquote>

#### 6.2.1.4. Development Evidence for Sprint Review

Orgnaizacion del github: [`https://github.com/upc-pre-202520-1asi0572-3355-BibFlip`]()
<table>
  <thead>
    <tr>
      <th>Repository</th><th>Branch</th><th>Commit Id</th><th>Commit Message</th><th>Commit Message Body</th><th>Committed on (Date)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>LandingPage</td><td>main</td><td><em>e65b846</em></td>
      <td>edit: footer(style)</td>
      <td>-</td>
      <td><em>8/10/25</em></td>
    </tr>
    <tr>
      <td>Web-Frontend</td><td>production</td><td><em>af43059</em></td>
      <td>hotfix: update .env production</td>
      <td>-</td>
      <td><em>6/10/25</em></td>
    </tr>
    <tr>
      <td>Mobile-Frontend</td><td>production</td><td><em>
        8f3b6f6</em></td>
      <td>feat: update google maps integration</td>
      <td>-</td>
      <td><em>8/10/25</em></td>
    </tr>
  </tbody>
</table>


#### 6.2.1.5. Testing Suite Evidence for Sprint Review

<p><em>Para Sprint 1 no se incluyen Web Services; se planifica test unitario/UI para front y widget tests en Flutter en el Sprint 2.</em></p>

<table>
  <thead>
    <tr>
      <th>Repo (Testing)</th><th>Tipo</th><th>Relación con historias</th><th>Estado</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>org/web-bibflip</td><td>UI/Component tests</td><td>US005, US007, US009</td><td>Planificado</td></tr>
    <tr><td>org/mobile-bibflip</td><td>Flutter widget tests</td><td>US006, US008</td><td>Planificado</td></tr>
  </tbody>
</table>


#### 6.2.1.6. Execution Evidence for Sprint Review

**Screenshots (avances reales):**

- **Web (Frontend):**  
  ![web-1](https://i.postimg.cc/hGhngYkJ/Captura-de-pantalla-2025-10-10-015726.png)  
  ![web-2](https://i.postimg.cc/yxyt0XqY/Captura-de-pantalla-2025-10-10-015821.png)  
  ![web-3](https://i.postimg.cc/FFVBWZqH/Captura-de-pantalla-2025-10-10-015917.png)

- **Landing:**  
  ![landing-1](https://i.postimg.cc/KzF5tXmT/Captura-de-pantalla-2025-10-10-020020.png)  
  ![landing-2](https://i.postimg.cc/VkC9Ts6D/Captura-de-pantalla-2025-10-10-020056.png)

- **Mobile (Flutter):**  
  ![mobile-1](https://i.postimg.cc/jdWkxb2b/Captura-de-pantalla-2025-10-10-020731.png)  
  ![mobile-2](https://i.postimg.cc/cLBzjc6J/Captura-de-pantalla-2025-10-10-020835.png)

#### 6.2.1.7. Services Documentation Evidence for Sprint Review

<p><em>Sin Web Services en Sprint 1. Se documentarán endpoints con OpenAPI a partir de Sprint 2 (TS001–TS003).</em></p>

<table>
  <thead>
    <tr><th>Servicio</th><th>Endpoint</th><th>Método</th><th>Descripción</th><th>OpenAPI URL</th><th>Estado</th></tr>
  </thead>
  <tbody>
    <tr><td colspan="6" style="text-align:center;">— No aplica en Sprint 1 —</td></tr>
  </tbody>
</table>

#### 6.2.1.8. Software Deployment Evidence for Sprint Review

- **Landing**: GitHub Pages — URL: [`https://upc-pre-202520-1asi0572-3355-bibflip.github.io/LandingPage/`](https://upc-pre-202520-1asi0572-3355-bibflip.github.io/LandingPage/)
- **Frontend Web**: Firebase Hosting — URL: [`https://bib-flip-web-app-2025-02.web.app/`](https://bib-flip-web-app-2025-02.web.app/)
- **Mobile**: Build APK de pruebas internas.

<p><em>Adjuntar capturas de consola y/o logs de despliegue (GitHub Actions / Firebase CLI).</em></p>


#### 6.2.1.9. Team Collaboration Insights during Sprint

- **Gestión en Trello**: tablero con columnas backlog → to-do → in-process → review → done.  
  - URL del Board: <em>[`https://trello.com/b/htxHDgrX/bibflip`](https://trello.com/b/htxHDgrX/bibflip)</em>.
- **Git/Colaboración**: GitFlow (feature → develop → release → main); PRs con revisión cruzada; Conventional Commits y SemVer.
- **Observaciones**:  
  - Picos de actividad: 08–10 oct (Landing/Web), 08–09 oct (Mobile).  
  - Próximo Sprint: integrar API (TS001–TS003, TS006) y pruebas e2e con datos reales.
