---
sidebar_position: 2
id: projects-organization
title: Organización del trabajo con GitHub Projects
sidebar_label: GitHub Projects
---


La gestión del proyecto se realiza mediante **GitHub Projects** en formato **Kanban**, siguiendo una estructura ágil y simple para que el equipo pueda colaborar de forma organizada.

---

### 🧩 Tipos de tareas (issues)

Todas las tareas del proyecto se gestionan como **issues**. Estas pueden representar:

- **User stories**: funcionalidades desde la perspectiva del usuario (ej. *“Como alumno quiero ver mis resultados para saber cómo voy”*).
- **Bugs**: errores detectados que hay que solucionar.
- **Tareas técnicas**: mejoras internas, refactorizaciones, ajustes de entorno, etc.

---

### ✍️ Plantillas de issues

Para asegurar una descripción clara y uniforme de las tareas, se usan **plantillas predefinidas**. Al crear una nueva issue, elige la plantilla correspondiente:

- 🧑‍🎓 `user-story.md`
- 🐛 `bug.md`
- 🔧 `tech-task.md`

Cada plantilla incluye:

- Descripción clara de la tarea
- Criterios de aceptación (qué se considera “terminado”)
- Checklist si aplica

> 📌 Esto ayuda a que todo el equipo entienda rápidamente de qué va la tarea y cómo completarla.
> 

---

### 🏷️ Etiquetas (labels)

Las issues tendrán etiquetas para clasificar y priorizar el trabajo. Algunas etiquetas comunes:

- `frontend`, `backend`, `infra`
- `bug`, `enhancement`, `question`
- `high priority`, `blocked`, `in progress`

---

### 🗂️ Tablero Kanban

El tablero tendrá columnas como:

- **Backlog** – ideas o tareas por priorizar
- **To Do** – tareas del sprint actual que aún no se han empezado
- **In Progress** – tareas en desarrollo
- **In Review** – tareas con Pull Request en espera de revisión
- **Done** – tareas completadas y revisadas

---

### 🌀 Flujo de trabajo ágil

1. Al inicio de cada **sprint**, el equipo seleccionará y refinará las tareas prioritarias.
2. Las tareas grandes (epics o user stories) se dividirán en subtareas concretas.
3. Cada estudiante se asigna una o más subtareas claras.
4. Cada tarea se trabaja en una **rama individual**, vinculada con su issue.
5. Una vez completada y revisada, la issue se mueve a **Done**.

---

### 🧠 Buenas prácticas

- Si empiezas una tarea, **asígnatela en el tablero**.
- Asegúrate de que la descripción sea clara antes de comenzar.
- Si te bloqueas, **mueve la tarea a `Blocked`** y comunica el problema.
- Usa el historial de la issue para dejar comentarios, dudas o avances.