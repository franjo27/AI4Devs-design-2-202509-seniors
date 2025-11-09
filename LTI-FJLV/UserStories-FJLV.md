# 📘 Épicos Principales del Sistema LTI ATS

Este documento resume los **épicos funcionales clave** del sistema **LTI ATS (Applicant Tracking System)**, identificados a partir del análisis del documento LTI-FJLV.md.  
Cada épico se describe brevemente con su **objetivo**, **alcance** y **casos de uso relacionados**.

---

## 🧩 1. Gestión de Vacantes
**Objetivo:**  
Permitir a los reclutadores crear, editar, publicar y cerrar vacantes dentro del sistema.  
**Descripción:**  
Incluye la definición de campos clave (puesto, requisitos, ubicación, tipo de contrato) y el control de estados (abierta, en revisión, cerrada).  
**Casos de uso relacionados:**  
- CU1: Crear y Publicar Vacante.

---

## 🧩 2. Gestión de Candidatos
**Objetivo:**  
Centralizar y mantener actualizada la información de los candidatos.  
**Descripción:**  
Permite el registro manual o la importación desde LinkedIn o formularios públicos. Incluye ficha detallada con datos personales, profesionales y documentos asociados.  
**Casos de uso relacionados:**  
- CU2: Registrar o Importar Candidato.

---

## 🧩 3. Pipeline Visual de Selección (Kanban)
**Objetivo:**  
Facilitar la gestión visual del flujo de candidatos en cada proceso de selección.  
**Descripción:**  
Representa el avance de los candidatos entre etapas (screening, entrevista, oferta) mediante una vista Kanban y permite moverlos con drag & drop.  
**Casos de uso relacionados:**  
- CU3: Mover Candidato entre Etapas.

---

## 🧩 4. Automatización de Notificaciones y Comunicaciones
**Objetivo:**  
Reducir tareas manuales y mantener informados a candidatos y reclutadores.  
**Descripción:**  
Configura y envía correos automáticos o mensajes internos según eventos (nueva candidatura, cambio de etapa, rechazo).  
**Casos de uso relacionados:**  
- Asociado a CU3 y eventos del sistema.

---

## 🧩 5. Cumplimiento y Gestión de Consentimientos (GDPR)
**Objetivo:**  
Garantizar la protección y tratamiento adecuado de los datos personales.  
**Descripción:**  
Gestiona el consentimiento, retención y eliminación automática de datos conforme al GDPR. Incluye anonimización y control de caducidad.  
**Casos de uso relacionados:**  
- Integrado en CU2 (solicitud y registro de consentimiento).

---

## 🧩 6. Integración con Plataformas Externas
**Objetivo:**  
Facilitar la publicación de ofertas y recepción de candidaturas desde portales externos.  
**Descripción:**  
Permite conexión con LinkedIn, Indeed y servicios de calendario o correo (Google/Microsoft 365).  
**Casos de uso relacionados:**  
- CU1 (publicación en LinkedIn).  
- CU2 (importación desde LinkedIn).

---

## 🧩 7. Roles, Permisos y Colaboración
**Objetivo:**  
Definir una estructura de acceso y colaboración entre distintos perfiles.  
**Descripción:**  
Incluye gestión de permisos para reclutadores, managers y directivos, comentarios internos y evaluaciones compartidas.  
**Casos de uso relacionados:**  
- Transversales a todos los módulos.

---

## 🧩 8. Analítica y Métricas del Proceso de Selección
**Objetivo:**  
Proporcionar indicadores que permitan optimizar el proceso de contratación.  
**Descripción:**  
Dashboard con KPIs como tiempo medio de contratación, conversión por etapa y fuente de talento.  
**Casos de uso relacionados:**  
- Derivados de CU1–CU3 y eventos automáticos.

---

## 🧩 9. Formularios Públicos de Candidatura
**Objetivo:**  
Simplificar la recepción de candidaturas externas.  
**Descripción:**  
Ofrece formularios configurables embebibles en la web corporativa con campos personalizados y subida de CV.  
**Casos de uso relacionados:**  
- Extiende CU2 (registro vía formulario).

---

## 🧩 10. Buscador y Reutilización de Talento
**Objetivo:**  
Permitir búsquedas rápidas y reutilización de perfiles previos.  
**Descripción:**  
Incluye buscador avanzado por nombre, habilidades o etiquetas, y reindexación automática en OpenSearch.  
**Casos de uso relacionados:**  
- Consultas sobre CU2 y CU3.

---

## 🧩 11. Módulo de Inteligencia Artificial (AI Microservices)
**Objetivo:**  
Automatizar tareas de análisis, evaluación y predicción en procesos de selección.  
**Descripción:**  
Incluye servicios como Resume Parser, Candidate Ranking, Chatbot, Video Analyzer y Predictive Analytics Engine.  
**Casos de uso relacionados:**  
- CU2 (análisis de CVs).  
- CU3 (evaluación de candidatos).

---

## 🧩 12. Arquitectura y Observabilidad del Sistema
**Objetivo:**  
Garantizar la escalabilidad, seguridad y trazabilidad del sistema.  
**Descripción:**  
Infraestructura modular en AWS basada en microservicios y arquitectura orientada a eventos, con monitoreo centralizado y control de acceso seguro.  
**Casos de uso relacionados:**  
- Soporte transversal a todos los módulos.

---
# 📘 Historias de Usuario – Sistema LTI ATS

Este documento contiene las **historias de usuario** derivadas de los épicos principales del sistema **LTI ATS (Applicant Tracking System)**.  
Cada historia sigue la estructura: narrativa, criterios de aceptación, notas técnicas, relaciones y estimación.

---

## 🧩 Épico 1 – Gestión de Vacantes

### Historia 1.1 – Crear nueva vacante
**Narrativa:**  
Como **reclutador**, quiero crear una nueva vacante con todos los datos requeridos, para que el proceso de selección pueda iniciarse correctamente.  
**Criterios de aceptación:**  
- Debe incluir campos obligatorios: título, descripción, requisitos, ubicación y tipo de contrato.  
- El sistema valida los campos antes de guardar.  
- La vacante se crea con estado “Abierta”.  
**Notas adicionales:**  
El formulario debe ser responsive y permitir autocompletar desde plantillas previas.  
**Historias relacionadas:** 1.2, 6.1  
**Prioridad:** Alta  
**Esfuerzo:** Medio  

---

### Historia 1.2 – Publicar vacante en portales externos
**Narrativa:**  
Como **reclutador**, quiero publicar automáticamente una vacante en LinkedIn, para ahorrar tiempo y aumentar la visibilidad del proceso.  
**Criterios de aceptación:**  
- El sistema debe conectarse con la API de LinkedIn.  
- Los datos de la vacante se sincronizan automáticamente.  
- Debe mostrarse confirmación de publicación exitosa.  
**Notas adicionales:**  
Integración basada en tokens OAuth y eventos de publicación.  
**Historias relacionadas:** 1.1, 6.1  
**Prioridad:** Alta  
**Esfuerzo:** Grande  

---

### Historia 1.3 – Editar o cerrar vacante existente
**Narrativa:**  
Como **reclutador**, quiero editar la información de una vacante o cerrarla, para mantener actualizada su disponibilidad.  
**Criterios de aceptación:**  
- Solo vacantes en estado “Abierta” o “En revisión” pueden editarse.  
- El cierre actualiza su estado a “Cerrada”.  
- Se notifica automáticamente a los candidatos asociados.  
**Notas adicionales:**  
Debe registrarse trazabilidad del cambio.  
**Prioridad:** Media  
**Esfuerzo:** Medio  

---

## 🧩 Épico 2 – Gestión de Candidatos

### Historia 2.1 – Registrar candidato manualmente
**Narrativa:**  
Como **reclutador**, quiero registrar un nuevo candidato desde el panel interno, para incluir perfiles recibidos por otros medios.  
**Criterios de aceptación:**  
- Se deben validar los campos obligatorios (nombre, email, CV).  
- Se debe vincular el candidato a una vacante activa.  
- El sistema solicita consentimiento GDPR.  
**Notas adicionales:**  
El formulario debe aceptar carga de CV en PDF o DOCX.  
**Prioridad:** Alta  
**Esfuerzo:** Medio  

---

### Historia 2.2 – Importar candidato desde LinkedIn
**Narrativa:**  
Como **reclutador**, quiero importar la información de un candidato desde su perfil de LinkedIn, para reducir el tiempo de registro.  
**Criterios de aceptación:**  
- Se autentica al usuario en LinkedIn mediante OAuth.  
- Los datos importados deben mapearse correctamente a los campos internos.  
- El sistema registra el origen de la candidatura.  
**Notas adicionales:**  
Usa LinkedIn API v2 con permisos r_emailaddress y r_liteprofile.  
**Prioridad:** Alta  
**Esfuerzo:** Grande  

---

### Historia 2.3 – Visualizar ficha completa del candidato
**Narrativa:**  
Como **reclutador**, quiero visualizar toda la información de un candidato, para evaluar su idoneidad.  
**Criterios de aceptación:**  
- Debe mostrar datos personales, experiencia, educación y documentos.  
- Se debe registrar fecha de última actualización.  
- Solo usuarios con permisos adecuados pueden acceder.  
**Notas adicionales:**  
Posible integración futura con IA para sugerir afinidad.  
**Prioridad:** Media  
**Esfuerzo:** Medio  

---

## 🧩 Épico 3 – Pipeline Visual de Selección

### Historia 3.1 – Ver pipeline de candidatos
**Narrativa:**  
Como **reclutador**, quiero visualizar el estado de todos los candidatos en un tablero Kanban, para tener una visión clara del proceso.  
**Criterios de aceptación:**  
- El tablero debe mostrar etapas configurables.  
- Se debe actualizar automáticamente al mover un candidato.  
- Los cambios deben registrarse en el historial.  
**Notas adicionales:**  
Implementar drag & drop con persistencia automática.  
**Prioridad:** Alta  
**Esfuerzo:** Medio  

---

### Historia 3.2 – Cambiar etapa del candidato
**Narrativa:**  
Como **reclutador**, quiero mover un candidato entre etapas, para reflejar su progreso.  
**Criterios de aceptación:**  
- El movimiento debe actualizar el estado en base de datos.  
- Se dispara una notificación al candidato.  
- Se actualiza el tiempo medio por etapa.  
**Notas adicionales:**  
Eventos gestionados vía EventBridge.  
**Prioridad:** Alta  
**Esfuerzo:** Pequeño  

---

## 🧩 Épico 4 – Automatización de Notificaciones

### Historia 4.1 – Configurar plantillas de notificación
**Narrativa:**  
Como **reclutador**, quiero definir plantillas de correo para cada etapa del proceso, para ahorrar tiempo y mantener consistencia.  
**Criterios de aceptación:**  
- Las plantillas deben soportar variables dinámicas (nombre, puesto).  
- Se pueden activar o desactivar por evento.  
- Las notificaciones se guardan en el historial del candidato.  
**Notas adicionales:**  
Integración con Amazon SES o SMTP propio.  
**Prioridad:** Media  
**Esfuerzo:** Medio  

---

### Historia 4.2 – Envío automático tras cambio de estado
**Narrativa:**  
Como **sistema**, quiero enviar correos automáticos cuando un candidato cambie de etapa, para mantenerlo informado.  
**Criterios de aceptación:**  
- Se deben respetar las plantillas configuradas.  
- Debe registrarse un log del envío.  
- Fallos de envío deben generar alertas.  
**Notas adicionales:**  
Desencadenado por eventos en AWS EventBridge.  
**Prioridad:** Alta  
**Esfuerzo:** Medio  

---

## 🧩 Épico 5 – Cumplimiento GDPR

### Historia 5.1 – Solicitar consentimiento GDPR
**Narrativa:**  
Como **candidato**, quiero aceptar el tratamiento de mis datos, para poder participar en procesos de selección.  
**Criterios de aceptación:**  
- El sistema muestra un aviso legal antes de enviar el formulario.  
- El consentimiento se registra con fecha y hora.  
- Sin consentimiento, el registro no se completa.  
**Notas adicionales:**  
Los textos deben ser configurables.  
**Prioridad:** Alta  
**Esfuerzo:** Pequeño  

---

### Historia 5.2 – Eliminar datos tras vencimiento
**Narrativa:**  
Como **administrador del sistema**, quiero que los datos de candidatos se eliminen automáticamente tras un periodo legal, para cumplir con la normativa.  
**Criterios de aceptación:**  
- El sistema calcula la fecha de vencimiento.  
- Se anonimiza o borra la información según configuración.  
- Se registra la acción en logs de auditoría.  
**Notas adicionales:**  
Proceso automatizado con AWS Lambda.  
**Prioridad:** Alta  
**Esfuerzo:** Medio  

---

## 🧩 Épico 6 – Integración con Plataformas Externas

### Historia 6.1 – Publicar en LinkedIn
**Narrativa:**  
Como **reclutador**, quiero que las vacantes creadas se publiquen automáticamente en LinkedIn, para llegar a más candidatos.  
**Criterios de aceptación:**  
- El sistema debe usar la API oficial de LinkedIn.  
- La publicación debe incluir título, descripción y enlace.  
- Debe mostrar estado de sincronización.  
**Notas adicionales:**  
Depende del épico 1.  
**Prioridad:** Alta  
**Esfuerzo:** Grande  

---

### Historia 6.2 – Sincronizar candidaturas externas
**Narrativa:**  
Como **reclutador**, quiero que los candidatos que aplican desde LinkedIn se registren automáticamente en el ATS, para centralizar la información.  
**Criterios de aceptación:**  
- El sistema recibe los datos mediante webhook o polling.  
- Se crea la ficha del candidato con origen = “LinkedIn”.  
- Se asocia a la vacante correspondiente.  
**Notas adicionales:**  
Debe manejar duplicados y consentimientos.  
**Prioridad:** Alta  
**Esfuerzo:** Grande  

---

## 🧩 Épico 7 – Roles y Colaboración

### Historia 7.1 – Asignar roles a usuarios
**Narrativa:**  
Como **administrador del sistema**, quiero asignar diferentes roles y permisos, para controlar el acceso a funciones sensibles.  
**Criterios de aceptación:**  
- Roles disponibles: Reclutador, Manager, Dirección, Administrador.  
- Cada rol tiene permisos predefinidos.  
- Los cambios se reflejan en la sesión activa.  
**Notas adicionales:**  
Basado en AWS Cognito Roles.  
**Prioridad:** Alta  
**Esfuerzo:** Medio  

---

### Historia 7.2 – Colaboración en evaluaciones
**Narrativa:**  
Como **reclutador**, quiero que varios usuarios puedan dejar comentarios sobre un candidato, para mejorar la evaluación conjunta.  
**Criterios de aceptación:**  
- Cada comentario debe registrar autor y fecha.  
- Los comentarios no son visibles para el candidato.  
- Se pueden marcar como “revisión completada”.  
**Notas adicionales:**  
Relacionado con el módulo de pipeline.  
**Prioridad:** Media  
**Esfuerzo:** Medio  

---

## 🧩 Épico 8 – Analítica y Métricas

### Historia 8.1 – Visualizar KPIs del proceso
**Narrativa:**  
Como **manager**, quiero ver indicadores como tiempo medio de contratación y fuente de talento, para optimizar los procesos.  
**Criterios de aceptación:**  
- Los datos se actualizan diariamente.  
- Los indicadores son filtrables por vacante o reclutador.  
- El dashboard es accesible desde el panel principal.  
**Notas adicionales:**  
Visualización mediante gráficos en React.  
**Prioridad:** Media  
**Esfuerzo:** Medio  

---

### Historia 8.2 – Exportar reportes
**Narrativa:**  
Como **manager**, quiero exportar los KPIs a Excel o PDF, para compartir los resultados con la dirección.  
**Criterios de aceptación:**  
- Se pueden seleccionar fechas y filtros.  
- El archivo incluye logotipo y fecha de exportación.  
- El sistema registra el evento de descarga.  
**Notas adicionales:**  
Usar AWS Lambda + S3 para generación asíncrona.  
**Prioridad:** Baja  
**Esfuerzo:** Medio  

---

## 🧩 Épico 9 – Formularios Públicos de Candidatura

### Historia 9.1 – Crear formulario de aplicación
**Narrativa:**  
Como **reclutador**, quiero generar un formulario público para recibir candidaturas, para centralizar los datos.  
**Criterios de aceptación:**  
- El formulario debe incluir campos personalizados.  
- Debe integrarse mediante iframe o enlace directo.  
- Se almacena el origen de cada candidatura.  
**Notas adicionales:**  
Requiere validación CAPTCHA.  
**Prioridad:** Alta  
**Esfuerzo:** Medio  

---

### Historia 9.2 – Confirmar recepción de candidatura
**Narrativa:**  
Como **candidato**, quiero recibir una confirmación al enviar mi formulario, para saber que mi aplicación fue recibida.  
**Criterios de aceptación:**  
- Se muestra un mensaje de éxito.  
- Se envía un correo con resumen de la aplicación.  
- Se registra el evento de envío.  
**Notas adicionales:**  
Plantilla editable por el reclutador.  
**Prioridad:** Media  
**Esfuerzo:** Pequeño  

---

## 🧩 Épico 10 – Buscador y Reutilización de Talento

### Historia 10.1 – Buscar candidatos por nombre o habilidad
**Narrativa:**  
Como **reclutador**, quiero buscar candidatos por nombre, habilidades o etiquetas, para reutilizar perfiles previos.  
**Criterios de aceptación:**  
- La búsqueda debe ser instantánea.  
- Soporta filtros combinados.  
- Los resultados incluyen vínculo a la ficha del candidato.  
**Notas adicionales:**  
Implementar con Amazon OpenSearch.  
**Prioridad:** Alta  
**Esfuerzo:** Medio  

---

### Historia 10.2 – Guardar búsquedas frecuentes
**Narrativa:**  
Como **reclutador**, quiero guardar mis búsquedas frecuentes, para reutilizarlas fácilmente.  
**Criterios de aceptación:**  
- El sistema permite nombrar las búsquedas.  
- Pueden editarse o eliminarse.  
- Son privadas por usuario.  
**Notas adicionales:**  
Persistencia en base de datos RDS.  
**Prioridad:** Baja  
**Esfuerzo:** Pequeño  


# 🧭 Metodología de Desarrollo y Backlog Inicial – Sistema LTI ATS

## 📌 Metodología recomendada: Scrumban (Scrum + Kanban)

### Justificación de la elección
El sistema **LTI ATS** es una plataforma SaaS modular y compleja, con distintos flujos (vacantes, candidatos, automatización, IA y GDPR).  
Se recomienda un enfoque **Scrumban** que combine la estructura iterativa de Scrum con la flexibilidad de Kanban.

### ✅ Ventajas
1. **Entregas iterativas controladas:** Scrum permite construir módulos funcionales completos por sprint.  
2. **Alta trazabilidad:** Ideal para entornos con cumplimiento normativo (GDPR).  
3. **Priorización clara:** Enfocado en valor de negocio frente al esfuerzo técnico.  
4. **Flexibilidad operativa:** Kanban permite gestionar incidencias y mejoras sin interrumpir el sprint.  
5. **Adaptabilidad:** Perfecto para un producto SaaS en evolución continua.

### ⚠️ Desventajas
1. Requiere roles definidos (PO, Scrum Master, Dev Team).  
2. Planificación inicial más exigente.  
3. Integraciones complejas pueden exceder el marco temporal de un sprint.  
4. Mayor carga de ceremonias si el equipo es pequeño.

### 💡 Conclusión
> La metodología **Scrumban** es la más adecuada para el desarrollo del LTI ATS, permitiendo equilibrio entre planificación (Scrum) y flujo continuo (Kanban).  
> Se propone trabajar con **sprints de 3 semanas** y una **capacidad estimada de 20 puntos por sprint**.

---

# 🗂️ Backlog de Desarrollo Inicial

## 🧮 Escala de esfuerzo
- Pequeño = 2 puntos  
- Medio = 5 puntos  
- Grande = 8 puntos  
**Capacidad estimada:** 20 puntos por sprint

---

## 🏁 Sprint 1 – Módulo Base y Configuración Inicial (19 pts)
**Objetivo:** Entregar el núcleo funcional del ATS con gestión de vacantes, candidatos y GDPR básico.

| Historia | Descripción | Pri | Esfuerzo | Pts |
|-----------|--------------|-----|-----------|-----|
| 1.1 | Crear nueva vacante | Alta | Medio | 5 |
| 2.1 | Registrar candidato manualmente | Alta | Medio | 5 |
| 3.1 | Ver pipeline de candidatos | Alta | Medio | 5 |
| 5.1 | Solicitar consentimiento GDPR | Alta | Pequeño | 2 |
| 9.2 | Confirmar recepción de candidatura | Media | Pequeño | 2 |

**Justificación:**  
Base funcional mínima (MVP) para operar el ATS, cubriendo flujos de vacantes y candidatos con cumplimiento legal básico.

---

## 🚀 Sprint 2 – Automatización y Colaboración (22 pts)
**Objetivo:** Implementar automatización de comunicaciones y colaboración entre usuarios.

| Historia | Descripción | Pri | Esfuerzo | Pts |
|-----------|--------------|-----|-----------|-----|
| 3.2 | Cambiar etapa del candidato | Alta | Pequeño | 2 |
| 4.1 | Configurar plantillas de notificación | Media | Medio | 5 |
| 4.2 | Envío automático tras cambio de estado | Alta | Medio | 5 |
| 7.1 | Asignar roles a usuarios | Alta | Medio | 5 |
| 7.2 | Colaboración en evaluaciones | Media | Medio | 5 |

**Justificación:**  
Enfocado en flujos automáticos y permisos de usuario. Algunas historias dependen del pipeline del Sprint 1.

---

## 🌐 Sprint 3 – Integraciones Externas y Publicación (24 pts)
**Objetivo:** Conectar el ATS con LinkedIn y automatizar publicación y recepción de candidaturas externas.

| Historia | Descripción | Pri | Esfuerzo | Pts |
|-----------|--------------|-----|-----------|-----|
| 1.2 | Publicar vacante en portales externos | Alta | Grande | 8 |
| 2.2 | Importar candidato desde LinkedIn | Alta | Grande | 8 |
| 6.2 | Sincronizar candidaturas externas | Alta | Grande | 8 |

**Justificación:**  
Integraciones API de alta complejidad. Depende del módulo de vacantes y candidatos del Sprint 1.

---

## 📊 Sprint 4 – Analítica y Optimización (22 pts)
**Objetivo:** Incorporar métricas, formularios y herramientas de búsqueda para mejorar la eficiencia del reclutador.

| Historia | Descripción | Pri | Esfuerzo | Pts |
|-----------|--------------|-----|-----------|-----|
| 8.1 | Visualizar KPIs del proceso | Media | Medio | 5 |
| 8.2 | Exportar reportes | Baja | Medio | 5 |
| 10.1 | Buscar candidatos por nombre o habilidad | Alta | Medio | 5 |
| 10.2 | Guardar búsquedas frecuentes | Baja | Pequeño | 2 |
| 9.1 | Crear formulario de aplicación | Alta | Medio | 5 |

**Justificación:**  
Sprint orientado a la mejora de usabilidad, analítica y capacidad de gestión avanzada.

---

## 🤖 Sprint 5 – Inteligencia Artificial y Cumplimiento Avanzado (21 pts)
**Objetivo:** Implementar servicios inteligentes (IA) y funciones avanzadas de cumplimiento GDPR.

| Historia | Descripción | Pri | Esfuerzo | Pts |
|-----------|--------------|-----|-----------|-----|
| 11.1 | Resume Parser (IA para CVs) | Alta | Grande | 8 |
| 11.2 | Candidate Ranking (afinidad IA) | Alta | Grande | 8 |
| 5.2 | Eliminar datos tras vencimiento (GDPR) | Alta | Medio | 5 |

**Justificación:**  
Sprint centrado en IA y automatización avanzada. Requiere datos históricos de candidatos y vacantes para operar.

---

## 🚧 Historias Bloqueadas o Dependientes

| Historia | Bloqueada por | Motivo |
|-----------|----------------|--------|
| 1.2 (Publicar vacante) | 1.1 | Requiere vacantes creadas previamente |
| 2.2 (Importar LinkedIn) | 1.2 | Depende de la autenticación API |
| 4.2 (Notificaciones automáticas) | 3.2 | Necesita eventos definidos de cambio de etapa |
| 5.2 (Eliminar datos) | 2.1 / 5.1 | Requiere registro y consentimiento previos |

---

## 📅 Resumen de planificación

| Sprint | Objetivo principal | Total Pts | Estado |
|--------|--------------------|------------|--------|
| 1 | Núcleo del ATS + GDPR básico | 19 | 🟢 Prioritario |
| 2 | Automatización y roles | 22 | 🟢 Confirmado |
| 3 | Integraciones externas | 24 | 🟡 Complejidad alta |
| 4 | Analítica y formularios | 22 | 🟢 Planificado |
| 5 | IA y GDPR avanzado | 21 | 🟡 Fase de madurez |

# 🧩 Sprint 1 – Núcleo del Sistema ATS

## 🎯 Objetivo del sprint
Desarrollar el **MVP funcional** del sistema, permitiendo gestionar vacantes y candidatos, visualizar el pipeline y cumplir con el GDPR básico.

**Arquitectura de referencia:**
- **Frontend:** React + Next.js + TailwindCSS  
- **Backend:** Node.js (Express) o .NET Core (ECS Fargate)  
- **Base de datos:** PostgreSQL (AWS RDS)  
- **Almacenamiento:** Amazon S3  
- **Autenticación:** JWT (AWS Cognito)  
- **Infraestructura:** Docker, AWS ECS, API Gateway  

---

## 🔹 Historia 1.1 – Crear nueva vacante

### 🧾 Ticket 1.1.1 – Crear modelo y migraciones para “JobPosting”
- **Descripción:** Crear la tabla `job_postings` en PostgreSQL con los campos requeridos. Incluir índices y validaciones de integridad.  
- **Tipo:** Tarea Técnica  
- **Criterios de aceptación:**  
  - Migración validada en entornos dev/test.  
  - Relación con `Recruiter` establecida.  
- **Prioridad:** Alta  
- **Estimación:** M  
- **Asignado a:** Backend Dev  
- **Etiquetas:** `backend`, `database`, `postgres`, `sprint1`, `vacantes`  
- **Comentarios:** Script SQL versionado en `/migrations`.  
- **Historial:** Creado → Revisado por QA.

---

### 🧾 Ticket 1.1.2 – API REST para CRUD de vacantes
- **Descripción:** Implementar endpoints REST `/api/vacantes` con validaciones y autenticación JWT.  
- **Tipo:** Feature  
- **Criterios de aceptación:**  
  - CRUD completo funcional y autenticado.  
  - Documentación OpenAPI 3 disponible.  
- **Prioridad:** Alta  
- **Estimación:** L  
- **Asignado a:** Backend Dev  
- **Etiquetas:** `backend`, `api`, `sprint1`, `vacantes`, `.net`  
- **Comentarios:** Desplegar en ECS y conectar a AWS RDS.  
- **Historial:** Pendiente de revisión de seguridad JWT.

---

### 🧾 Ticket 1.1.3 – UI de creación de vacantes
- **Descripción:** Crear formulario en Next.js para alta de vacantes con validación en frontend.  
- **Tipo:** Feature  
- **Criterios de aceptación:**  
  - Validaciones de campos obligatorios.  
  - Mensaje de confirmación visible.  
- **Prioridad:** Alta  
- **Estimación:** M  
- **Asignado a:** Frontend Dev  
- **Etiquetas:** `frontend`, `react`, `vacantes`, `sprint1`  
- **Historial:** UI completada → Integración backend pendiente.

---

### 🧾 Ticket 1.1.4 – Spike: Integración futura con LinkedIn Job API
- **Descripción:** Investigar autenticación y publicación automática de vacantes en LinkedIn API v2.  
- **Tipo:** Investigación (Spike)  
- **Criterios de aceptación:** Documento técnico con endpoints y scopes definidos.  
- **Prioridad:** Media  
- **Estimación:** S  
- **Asignado a:** Arquitecto Backend  
- **Etiquetas:** `spike`, `integración`, `linkedin`, `sprint1`  
- **Historial:** Pendiente de análisis Sprint 2.

---

## 🔹 Historia 2.1 – Registrar candidato manualmente

### 🧾 Ticket 2.1.1 – Modelo y migración para “Candidate”
- **Descripción:** Crear entidad `candidates` con campos (nombre, correo, fuente, consentimiento, fecha).  
- **Tipo:** Tarea Técnica  
- **Criterios de aceptación:** Validación de email único y relación 1:N con `Applications`.  
- **Prioridad:** Alta  
- **Estimación:** M  
- **Asignado a:** Backend Dev  
- **Etiquetas:** `backend`, `database`, `candidatos`, `sprint1`  
- **Historial:** En desarrollo.

---

### 🧾 Ticket 2.1.2 – API REST para registro de candidatos
- **Descripción:** Endpoint `POST /api/candidatos` para registro manual con validación GDPR.  
- **Tipo:** Feature  
- **Criterios de aceptación:** Crea registro y devuelve ID del candidato.  
- **Prioridad:** Alta  
- **Estimación:** M  
- **Asignado a:** Backend Dev  
- **Etiquetas:** `api`, `backend`, `gdpr`, `sprint1`  
- **Historial:** En test QA.

---

### 🧾 Ticket 2.1.3 – UI de registro manual de candidatos
- **Descripción:** Implementar formulario Next.js con subida de CV a S3 y checkbox GDPR.  
- **Tipo:** Feature  
- **Criterios de aceptación:** Validación de campos, subida correcta a S3.  
- **Prioridad:** Alta  
- **Estimación:** M  
- **Asignado a:** Frontend Dev  
- **Etiquetas:** `frontend`, `next`, `upload`, `sprint1`  
- **Historial:** Pendiente de prueba QA.

---

### 🧾 Ticket 2.1.4 – Validación GDPR en backend
- **Descripción:** Registrar fecha y estado del consentimiento GDPR del candidato.  
- **Tipo:** Técnica  
- **Criterios de aceptación:** Campo `consent_given=true` con timestamp.  
- **Prioridad:** Alta  
- **Estimación:** S  
- **Asignado a:** Backend Dev  
- **Etiquetas:** `gdpr`, `security`, `sprint1`  
- **Historial:** Test unitario completado.

---

## 🔹 Historia 3.1 – Ver pipeline de candidatos

### 🧾 Ticket 3.1.1 – Endpoint API para listar candidatos por etapa
- **Descripción:** Crear endpoint `GET /api/pipeline/{vacanteId}` agrupando candidatos por fase.  
- **Tipo:** Feature  
- **Criterios de aceptación:** JSON agrupado por etapa, incluye fecha de actualización.  
- **Prioridad:** Alta  
- **Estimación:** M  
- **Asignado a:** Backend Dev  
- **Etiquetas:** `api`, `pipeline`, `sprint1`  
- **Historial:** QA interno aprobado.

---

### 🧾 Ticket 3.1.2 – Componente frontend “Pipeline Kanban”
- **Descripción:** Implementar vista Kanban React con `react-beautiful-dnd`.  
- **Tipo:** Feature  
- **Criterios de aceptación:** Drag & drop funcional, refresco dinámico.  
- **Prioridad:** Alta  
- **Estimación:** L  
- **Asignado a:** Frontend Dev  
- **Etiquetas:** `frontend`, `kanban`, `react`, `sprint1`  
- **Historial:** UI → Implementación.

---

### 🧾 Ticket 3.1.3 – Actualización de estado de candidato
- **Descripción:** Endpoint `PATCH /api/candidatos/{id}/estado` para actualizar etapa del proceso.  
- **Tipo:** Feature  
- **Criterios de aceptación:** Registro auditado y evento en EventBridge.  
- **Prioridad:** Alta  
- **Estimación:** M  
- **Asignado a:** Backend Dev  
- **Etiquetas:** `api`, `pipeline`, `eventbridge`, `sprint1`  
- **Historial:** Dependiente del 3.1.1.

---

## 🔹 Historia 5.1 – Solicitar consentimiento GDPR

### 🧾 Ticket 5.1.1 – Modal de consentimiento GDPR
- **Descripción:** Crear modal en frontend con texto legal configurable y checkbox obligatorio.  
- **Tipo:** Feature  
- **Criterios de aceptación:** Se muestra antes del envío, no permite continuar sin aceptar.  
- **Prioridad:** Alta  
- **Estimación:** S  
- **Asignado a:** Frontend Dev  
- **Etiquetas:** `frontend`, `gdpr`, `sprint1`  
- **Historial:** Revisión UI pendiente.

---

### 🧾 Ticket 5.1.2 – Endpoint de registro de consentimiento
- **Descripción:** Crear servicio REST `/api/consentimientos` para guardar los consentimientos.  
- **Tipo:** Técnica  
- **Criterios de aceptación:** Guarda `user_id`, `fecha`, `versión de política`.  
- **Prioridad:** Alta  
- **Estimación:** S  
- **Asignado a:** Backend Dev  
- **Etiquetas:** `backend`, `gdpr`, `api`, `sprint1`  
- **Historial:** Pendiente de revisión.

---

## 🔹 Historia 9.2 – Confirmar recepción de candidatura

### 🧾 Ticket 9.2.1 – Envío de correo de confirmación (backend)
- **Descripción:** Configurar AWS SES para enviar correo tras registro de candidato.  
- **Tipo:** Feature  
- **Criterios de aceptación:** Envío exitoso con log registrado.  
- **Prioridad:** Media  
- **Estimación:** M  
- **Asignado a:** Backend Dev  
- **Etiquetas:** `email`, `aws-ses`, `backend`, `sprint1`  
- **Historial:** En QA.

---

### 🧾 Ticket 9.2.2 – UI de confirmación visual
- **Descripción:** Mostrar mensaje de éxito tras envío del formulario de candidato.  
- **Tipo:** Feature  
- **Criterios de aceptación:** Mensaje visible y opción de ver resumen.  
- **Prioridad:** Media  
- **Estimación:** S  
- **Asignado a:** Frontend Dev  
- **Etiquetas:** `frontend`, `ux`, `sprint1`  
- **Historial:** QA visual pendiente.

---

# 🧾 Resumen general del Sprint 1

| Historia | Total Tickets | Pri Alta | Pri Media | Estimación promedio | Tipo predominante |
|-----------|----------------|-----------|-----------|---------------------|-------------------|
| 1.1 | 4 | 2 | 2 | M–L | Feature / Técnica |
| 2.1 | 4 | 3 | 1 | S–M | Feature / Técnica |
| 3.1 | 3 | 3 | 0 | M–L | Feature |
| 5.1 | 2 | 2 | 0 | S | Feature / Técnica |
| 9.2 | 2 | 0 | 2 | S–M | Feature |

**Total:** 15 tickets → ~20 puntos de capacidad  
**Cobertura tecnológica:** Frontend (6), Backend (7), DB (2), AWS Services (2)

---
