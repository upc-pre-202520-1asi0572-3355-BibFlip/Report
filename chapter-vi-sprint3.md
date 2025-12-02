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
#### 6.2.3.6. Execution Evidence for Sprint Review.
#### 6.2.3.7. Services Documentation Evidence for Sprint Review.
#### 6.2.3.8. Software Deployment Evidence for Sprint Review.
#### 6.2.3.9. Team Collaboration Insights during Sprint.