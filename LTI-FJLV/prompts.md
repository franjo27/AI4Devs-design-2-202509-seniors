# Documentación del Flujo de Trabajo con GPT-5 para la Especificación de Requisitos de un Sistema ATS

**Alumno:** Participante del curso LID  
**Fecha:** 09/11/2025  
**Proyecto:** Sistema de Seguimiento de Candidatos (ATS)  
**Herramienta utilizada:** Modelo GPT-5

---

## 1. Objetivo del ejercicio

El objetivo de esta práctica fue utilizar un modelo de lenguaje avanzado (GPT-5) como copiloto para definir de forma iterativa y estructurada la especificación de requisitos de un sistema ATS. A lo largo del proceso, se abordaron distintas fases del análisis y diseño de producto, desde la identificación de épicos hasta la descomposición en tickets técnicos.

---

## 2. Flujo de trabajo seguido

### 🧩 Fase 1: Definición de Épicos

### Contexto
Eres un Product Manager y Business Analyst con amplia experiencia en el mercado de los sistemas de seguimiento de candidatos (ATS). Estás trabajando en la definición del PRD (Product Requirements Document) de un nuevo sistema ATS. Se te proporciona un documento que contiene las características, casos de uso y documentación actual del proyecto.

### Objetivo
Analizar el contenido del documento adjunto para identificar y extraer los **épicos principales** que debe cubrir el sistema. Estos épicos servirán como base para la futura definición de historias de usuario.

### Resultado esperado
Una lista en **texto plano** de los épicos clave del sistema ATS, cada uno con:
- **Nombre del épico**
- **Descripción breve**
- **Casos de uso relacionados (si se identifican claramente)**

Una vez validado el contenido, se generará un fichero en formato `.md` con esta información estructurada.

### Instrucciones
1. Lee y comprende el documento adjunto.
2. Extrae los épicos principales que se desprenden del contenido.
3. Presenta los resultados en texto plano, agrupando por áreas funcionales si es posible.
4. No generes historias de usuario aún, solo épicos.

---
### 🎯 Definición de Épicos - Resultado
- Se proporcionó al modelo el contexto del proyecto y un documento base con la información funcional.
- Se solicitó al modelo que identificara los **épicos principales** del sistema, entendidos como grandes bloques funcionales.
- El modelo devolvió una lista de épicos con nombre, descripción y casos de uso relacionados.

## 🧩 Fase 2: Generación de Historias de Usuario

### Instrucciones adicionales (Iteración 2)

Una vez que se hayan identificado y validado los épicos principales del sistema ATS, genera entre **2 y 5 historias de usuario por cada épico**, siguiendo las siguientes directrices:

### Estructura de cada historia de usuario

- **Título de la historia**
- **Narrativa en lenguaje natural**:
  _Como [rol del usuario], quiero [acción que desea realizar el usuario], para que [beneficio que espera obtener el usuario]._
- **Criterios de aceptación**:  
  Lista de al menos 3 criterios específicos que deben cumplirse para considerar la historia como completada.
- **Notas adicionales**:  
  Consideraciones técnicas, de negocio o de experiencia de usuario relevantes.
- **Historias relacionadas**:  
  Referencias a otras historias que estén conectadas funcional o lógicamente.
- **Prioridad**:  
  Alta / Media / Baja (según impacto y urgencia).
- **Estimación de esfuerzo**:  
  Pequeño / Medio / Grande (según complejidad y recursos necesarios).

### Perfiles de usuario disponibles

Utiliza los siguientes roles para contextualizar las historias:
- Reclutador
- Candidato
- Administrador del sistema

### Formato de salida

Presenta primero las historias en **texto plano**, agrupadas por épico. No generes el fichero `.md` hasta que se haya validado el contenido.

---

### 🎯 Generación de Historias de Usuario - Resultado

- Una vez validados los épicos, se pidió al modelo que generara entre **2 y 5 historias de usuario por épico**.
- Las historias seguían la estructura clásica:  
  _"Como [rol del usuario], quiero [acción], para que [beneficio]"_.
- Se incluyeron criterios de aceptación, notas adicionales, prioridad, esfuerzo estimado y relaciones entre historias.
- Los perfiles de usuario definidos fueron: **reclutador**, **candidato** y **administrador del sistema**.

---

## 🧩 Fase 3: Análisis de Metodología Ágil y Planificación del Backlog

### Contexto
Ya se han definido los épicos y las historias de usuario del sistema ATS. Cada historia incluye: narrativa centrada en el usuario, criterios de aceptación, notas adicionales, prioridad (Alta, Media, Baja) y estimación de esfuerzo (Pequeño, Medio, Grande).

El proyecto se encuentra en fase de planificación del desarrollo. Se busca construir un backlog inicial que permita organizar el trabajo en sprints, pero antes de ello es necesario validar qué metodología de desarrollo encaja mejor con el contexto del producto.

### Objetivo
1. Analizar las metodologías ágiles disponibles (Scrum, Kanban, XP, etc.) y determinar cuál se adapta mejor al desarrollo del sistema ATS.
2. Justificar la elección con una explicación clara de **ventajas y desventajas** en relación al contexto del proyecto.
3. Una vez seleccionada la metodología, generar el **backlog de desarrollo inicial**, agrupando y ordenando las historias de usuario por prioridad y esfuerzo estimado.

### Resultado esperado
Una respuesta en **texto plano** que incluya:

#### Parte 1: Análisis de metodología
- Metodología recomendada
- Justificación de la elección
- Pros y contras en relación al proyecto ATS

#### Parte 2: Backlog de desarrollo
- **Sprint sugerido** (Sprint 1, Sprint 2, etc.)
- **Historias de usuario asignadas a cada sprint**
- **Justificación de la asignación** (por prioridad, esfuerzo y dependencia funcional)
- **Capacidad estimada por sprint** (puede ser ficticia si no se especifica)
- **Historias bloqueadas o dependientes** (si aplica)

### Instrucciones
1. Analiza el contexto del proyecto y las historias de usuario disponibles.
2. Evalúa qué metodología de desarrollo encaja mejor.
3. Explica tu elección con pros y contras.
4. Genera el backlog agrupado por sprints, priorizando las historias de mayor valor y menor esfuerzo.
5. Presenta todo en texto plano para revisión antes de generar el fichero `.md`.

### Consideraciones
- Se asume una capacidad de equipo media por sprint (puedes estimar 20 puntos por sprint como referencia).
- Las historias con prioridad Alta y esfuerzo Pequeño o Medio deben ir primero.
- Las historias con dependencias deben ir en sprints posteriores si no se pueden resolver antes.

---

### 🎯 Análisis de Metodología Ágil y Planificación del Backlog - Resultado

- Antes de planificar el backlog, se solicitó al modelo que analizara qué metodología ágil encajaba mejor con el contexto del proyecto.
- El modelo comparó **Scrum**, **Kanban** y otras metodologías, recomendando **Scrum** como la más adecuada por su enfoque iterativo, planificación por sprints y claridad de roles.
- Se pidió al modelo que organizara las historias de usuario en **sprints**, priorizando por valor de negocio y esfuerzo.
- El modelo generó una propuesta de backlog con asignación de historias a sprints, justificación de la planificación y dependencias funcionales.


## 🧩 Fase 4: Descomposición en Tickets

### Contexto
Ya se han definido los épicos y las historias de usuario del sistema ATS, y se ha planificado el Sprint 1. El siguiente paso es descomponer esas historias en tickets detallados que puedan ser asignados al equipo de desarrollo.

Un ticket representa una unidad de trabajo concreta y debe incluir toda la información necesaria para su ejecución. Los tipos de tickets que se pueden generar son:

- **Características (Features)**: Funcionalidades vinculadas directamente a historias de usuario.
- **Tareas Técnicas**: Refactorización, configuración de infraestructura, integración, etc.
- **Bugs/Errores**: Problemas detectados que deben resolverse.
- **Mejoras**: Sugerencias basadas en feedback o experiencia de usuario.
- **Investigación (Spikes)**: Tareas orientadas a explorar soluciones o validar enfoques técnicos antes de implementar una funcionalidad.

### Objetivo
Descomponer las historias de usuario del Sprint 1 en un conjunto de tickets bien definidos, clasificados por tipo, priorizados y estimados según la metodología de tallas de camiseta.

### Consideración técnica adicional
Es **imprescindible tener en cuenta la estructura de componentes y la infraestructura tecnológica definida para el proyecto**. Esto incluye:

- Arquitectura del sistema (microservicios, monolito, etc.)
- Componentes técnicos (frontend, backend, base de datos, APIs, servicios externos, etc.)
- Tecnologías utilizadas (por ejemplo: React, Node.js, PostgreSQL, Docker, etc.)

Los tickets deben estar alineados con esta estructura para facilitar su implementación y asignación al equipo adecuado.

### Metodología de estimación
Utiliza la **metodología de tallas de camiseta** para estimar el esfuerzo de cada ticket. Esta técnica clasifica las tareas en:

- **XS (Extra pequeña)**: tareas muy simples, rápidas de ejecutar.
- **S (Pequeña)**: tareas simples que requieren poco tiempo.
- **M (Mediana)**: tareas con complejidad moderada.
- **L (Grande)**: tareas complejas que requieren coordinación.
- **XL (Extra grande)**: tareas muy complejas o que implican múltiples componentes.

Esta metodología permite una estimación rápida y visual del esfuerzo, facilitando la planificación y asignación de tareas.

### Resultado esperado
Una lista en **texto plano** de tickets derivados de las historias de usuario del Sprint 1, cada uno con:

- **Título del ticket**
- **Descripción detallada**
- **Tipo de ticket** (Feature, Técnica, Bug, Mejora, Spike)
- **Criterios de aceptación**
- **Prioridad** (Alta, Media, Baja)
- **Estimación** (XS, S, M, L, XL)
- **Asignado a** (si se puede inferir)
- **Etiquetas** (tecnología, módulo, sprint, etc.)
- **Comentarios adicionales**
- **Enlaces relevantes** (si aplica)
- **Historial de cambios** (simulado si no se especifica)

### Instrucciones
1. Analiza las historias de usuario del Sprint 1.
2. Descompón cada historia en los tickets necesarios para su desarrollo.
3. Clasifica cada ticket por tipo.
4. Prioriza y estima el esfuerzo usando tallas de camiseta.
5. Asegúrate de que cada ticket esté alineado con la arquitectura y tecnologías del proyecto.
6. Presenta los tickets en texto plano para revisión antes de generar el fichero `.md`.

---

### 🎯 Descomposición en Tickets - Resultado

- Finalmente, se solicitó al modelo que descompusiera las historias del **Sprint 1** en **tickets detallados**.
- Los tickets se clasificaron en:
  - Características (Features)
  - Tareas Técnicas
  - Bugs
  - Mejoras
  - Investigación (Spikes)
- Cada ticket incluía título, descripción, tipo, criterios de aceptación, prioridad, estimación (usando **tallas de camiseta**: XS, S, M, L, XL), asignación, etiquetas, comentarios y enlaces relevantes.
- Se indicó al modelo que tuviera en cuenta la **estructura de componentes e infraestructura tecnológica** del proyecto para alinear los tickets con el stack real.

---

## 3. Conclusión

Este ejercicio ha demostrado cómo un modelo de lenguaje como GPT-5 puede ser un aliado estratégico en la definición de producto, permitiendo:

- Acelerar la redacción de requisitos.
- Estructurar el pensamiento de forma iterativa.
- Generar entregables reutilizables como épicos, historias de usuario y tickets.
- Facilitar la planificación ágil y la colaboración con equipos técnicos.

El resultado final es una especificación de producto completa, coherente y alineada con las mejores prácticas de desarrollo ágil.

