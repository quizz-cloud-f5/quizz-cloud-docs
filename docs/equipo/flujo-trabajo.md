---
sidebar_position: 1
id: flujo-trabajo
title: Flujo-trabajo
sidebar_label: Flujo-trabajo
---


## 🎯 Git, Flujo de trabajo

Este proyecto utiliza una estrategia de trabajo basada en `Git Flow`, adaptada y simplificada. Cómo trabajar correctamente con ramas, issues y pull requests?

---

### 🧑‍💻 1. Trabajo individual con ramas

Cada miembro del equipo trabajará en su propia rama a partir de `develop`, siguiendo esta convención de nombres:

- Para nuevas funcionalidades: `feature/nombre-descriptivo`
- Para corregir errores: `fix/descripcion-error`

Por ejemplo:

```
feature/gestor-preguntas
fix/login-incorrecto
```

> ✅ El nombre debe reflejar qué estás haciendo. ¡Evita nombres genéricos como prueba1 o mi-rama!
> 

---

### 📋 2. Vincular la tarea a una *issue*

Antes de empezar, asegúrate de que tu tarea esté registrada en el tablero de GitHub Projects como una **issue**.

- Cada issue representa una historia de usuario, bug o tarea técnica.
- Asigna la issue a ti mismo/a y crea la rama a partir de ahí.
- Cuando hagas el PR, usa `Closes #número` para que se cierre automáticamente al hacer merge.

---

### 🔄 3. Mantén tu rama actualizada

Antes de abrir el pull request:

```bash
git fetch origin
git rebase origin/develop
```

Esto asegura que tu rama está al día con los últimos cambios y ayuda a **evitar conflictos** de fusión.

Si hay conflictos, **resuélvelos antes de hacer el PR**.

> 🧠 Rebase es obligatorio antes del PR para tener un historial limpio y evitar errores.
> 

---

### 🚦 4. Abrir un Pull Request (PR)

Cuando termines tu tarea:

1. Abre un **pull request (PR)** desde tu rama hacia `develop`.
2. En la descripción, **indica qué hiciste** y **usa `Closes #número` de la issue.**
3. Espera revisión por parte del equipo o del mentor.
4. El merge se hace con **squash**, para dejar un solo commit claro.

> 💡 Esto hace que el historial de develop sea fácil de leer y seguir.
> 

---

### ✅ 5. Qué debe pasar antes de aceptar un PR

Al crear el PR se ejecutará automáticamente:

- ✅ **CI (Integración continua):** se lanzan pruebas automáticas.
- ✅ **Coverage:** se comprueba qué porcentaje del código está cubierto por pruebas.
- ✅ **Análisis de calidad:** SonarQube revisa el código para detectar problemas y malas prácticas.

> ❌ Si alguna de estas comprobaciones falla, el PR no podrá ser aceptado hasta que se corrija.
> 

---

### 🔍 6. Revisión de código

Antes de hacer el merge, otro compañero/a o el mentor revisará:

- ¿El código hace lo que dice?
- ¿Es claro y legible?
- ¿Sigue las convenciones?
- ¿Tiene pruebas si aplica?

Esto es una oportunidad para **aprender de los demás y mejorar tu código**.

---

### 📚 Ejemplo de flujo completo

1. Me asigno la issue #42: “Como usuario quiero ver el listado de exámenes”.
2. Creo una rama: `feature/42-listado-examenes`.
3. Hago mis cambios y los testeo localmente.
4. Rebaso la rama `develop` y resuelvo conflictos si hay.
5. Abro un PR con el mensaje:
    
    `"feat: muestra listado de exámenes \n\Refers #42"`
    
6. Espero revisión y, si todo está correcto, se hace merge con squash.

---

### 🧠 Buenas prácticas

- Commits con estilo `Conventional Commits` (`feat:`, `fix:`, `docs:`, etc.).
- PRs pequeños y enfocados. Evita meter muchas cosas juntas.
- No te vayas de una tarea sin dejarla **limpia, probada y revisada.**