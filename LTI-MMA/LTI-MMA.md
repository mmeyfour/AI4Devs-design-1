
# LTI ATS - Diseño del Sistema

### 1. Descripción del Software

LTI es una startup enfocada en revolucionar los sistemas de seguimiento de candidatos (ATS - Applicant Tracking System). Su objetivo es optimizar la gestión del talento para departamentos de recursos humanos mediante automatización, colaboración en tiempo real y asistencia con inteligencia artificial.

### Valor Añadido y Ventajas Competitivas
	* 	**Automatización Inteligente**: Reducción de tareas manuales mediante IA.
	* 	**Colaboración en Tiempo Real**: Permite a reclutadores y managers interactuar eficientemente.
	* 	**Análisis Predictivo**: IA analiza datos históricos para mejorar la toma de decisiones.
	* 	**Integraciones Flexibles**: Conexión con plataformas de empleo, CRMs y ERPs.
	* 	**Experiencia Candidato Mejorada**: Comunicación fluida y automatizada con los postulantes.

### 2. Funcionalidades Principales
	* 	**Gestión de Procesos de Selección**: Creación de vacantes, seguimiento de etapas y feedback estructurado.
	* 	**Automatización de Selección**: Filtrado inteligente de candidatos mediante IA.
	* 	**Colaboración Multiequipo**: Espacios de trabajo compartidos con anotaciones y evaluaciones.
	* 	**Entrevistas Automatizadas**: Programación asistida y entrevistas pregrabadas con análisis de IA.
	* 	**Análisis y Reportes**: Panel de métricas sobre efectividad de contrataciones.

### 3. Lean Canvas

**Sección**	**Detalles**
**Problema**	Procesos de selección manuales y lentos, mala comunicación interna y experiencia deficiente para candidatos.
**Solución**	Automatización del reclutamiento, colaboración eficiente, IA para análisis predictivo.
**Métricas Clave**	Tiempo de contratación, tasa de aceptación de ofertas, satisfacción de candidatos.
**Propuesta de Valor**	ATS inteligente con IA, automatización y herramientas colaborativas.
**Ventaja Competitiva**	Integraciones API, colaboración avanzada y análisis de datos en tiempo real.
**Segmento de Clientes**	Empresas de RRHH, startups tecnológicas, consultoras de selección.
**Canales**	Web, API, partnerships con plataformas de empleo.
**Estructura de Costos**	Desarrollo de software, servidores, marketing, soporte.
**Flujo de Ingresos**	Suscripciones SaaS por usuario, personalizaciones premium.

### 4. Casos de Uso Principales

### Caso 1: Publicación de una Nueva Vacante

**Descripción**: Un reclutador crea una nueva oferta de trabajo en la plataforma y la publica en múltiples sitios de empleo.

**Diagrama de Flujo**:

graph TD*;*
    A[Reclutador inicia sesión] --> B[Accede a "Nueva Vacante"]
    B --> C[Completa detalles del puesto]
    C --> D[Selecciona canales de publicación]
    D --> E[Publica la vacante]

### Caso 2: Revisión de Candidatos y Feedback Colaborativo

**Descripción**: Un manager revisa candidatos y deja comentarios para otros miembros del equipo.

**Diagrama de Flujo**:

graph TD*;*
    A[Manager accede a la lista de candidatos] --> B[Filtra candidatos por criterios]
    B --> C[Revisa perfil y experiencia]
    C --> D[Deja comentarios y calificaciones]
    D --> E[Comparte evaluación con el equipo]

### Caso 3: Programación Automática de Entrevistas

**Descripción**: El sistema agenda entrevistas basándose en la disponibilidad de los participantes.

**Diagrama de Flujo**:

graph TD*;*
    A[Candidato seleccionado] --> B[IA analiza disponibilidad]
    B --> C[Propuesta de horarios generada]
    C --> D[Notificación enviada a candidato]
    D --> E[Candidato confirma horario]
    E --> F[Entrevista agendada automáticamente]

### 5. Modelo de Datos

### Entidades Principales
	* 	**Usuario** (id, nombre, email, rol)
	* 	**Empresa** (id, nombre, industria, ubicación)
	* 	**Vacante** (id, titulo, descripcion, empresa_id, estado)
	* 	**Candidato** (id, nombre, email, telefono, estado)
	* 	**Entrevista** (id, vacante_id, candidato_id, fecha, estado)

### Relaciones
	* 	Un **Usuario** pertenece a una **Empresa**.
	* 	Una **Vacante** pertenece a una **Empresa**.
	* 	Un **Candidato** puede postularse a múltiples **Vacantes**.
	* 	Una **Entrevista** está relacionada con una **Vacante** y un **Candidato**.

### 6. Diseño del Sistema a Alto Nivel

El sistema se estructura en tres capas:
	1.	**Capa de Presentación**: Aplicación web y API REST.
	2.	**Capa de Aplicación**: Servicios de autenticación, gestión de vacantes, IA de selección.
	3.	**Capa de Datos**: PostgreSQL para almacenamiento de datos estructurados.

### Diagrama de Arquitectura

```
graph TD*;*
    A[Frontend Web] -->|REST API| B[Backend]
    B -->|Autenticación| C[Servicio de Usuarios]
    B -->|Gestión de Vacantes| D[Servicio de Vacantes]
    B -->|IA de Selección| E[Módulo de IA]
    B -->|Almacenamiento| F[Base de Datos]
```

### 7. Diagrama C4

### Nivel 1: Contexto

```
graph TD*;*
    A[Usuario] -->|Usa| B[Sistema LTI ATS]
    B -->|Conecta con| C[Plataformas de Empleo]
    B -->|Accede a| D[Base de Datos]
    B -->|Integra con| E[Servicios de IA]
```

### Nivel 2: Contenedores

```
graph TD*;*
    A[Web App] -->|REST API| B[Backend (Django)]
    B -->|Almacena datos en| C[PostgreSQL]
    B -->|Procesa IA con| D[Servicio de IA]
    B -->|Enlaza con| E[Plataformas de Empleo]
```

⸻

Este documento proporciona una visión integral del diseño del sistema LTI ATS en su primera versión. Servirá como base para la planificación técnica y el desarrollo del producto.

