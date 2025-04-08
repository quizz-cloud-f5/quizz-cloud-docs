# 📘 Documentación técnica y funcional – QuizF5

Este repositorio contiene toda la documentación del proyecto **QuizF5**, construida con **[Docusaurus](https://docusaurus.io/)**.  
Está pensada para facilitar el trabajo colaborativo, la trazabilidad y la comprensión del sistema.

---

## 🚀 ¿Cómo funciona esta documentación?

La documentación está escrita en formato **Markdown (`.md`)**, organizada por secciones y desplegada automáticamente en GitHub Pages.

Cada vez que se hace un **push a la rama `main`**, se ejecuta un **GitHub Action** que:

- Compila el sitio de documentación con Docusaurus.
- Lo despliega automáticamente a GitHub Pages.

Puedes acceder a la versión pública en:

🔗 https://quizz-cloud-f5.github.io/quizz-cloud-docs

---

## ✍️ ¿Cómo editar la documentación?

Puedes editar cualquier archivo `.md` desde varias herramientas, según tu preferencia:

### ✅ Opción 1: Visual Studio Code (recomendado)

1. Clona el repositorio o ábrelo localmente en VSCode.
2. Navega a la carpeta `docs/` y edita los archivos Markdown.
3. Guarda, haz commit y push:

```bash
git add .
git commit -m "✏️ Actualizar documentación de login"
git push origin main
```

> Esto actualizará la web de documentación automáticamente.

---

### ✅ Opción 2: Obsidian (modo wiki)

1. Abre este repositorio como un **vault** de Obsidian.
2. Usa Obsidian para navegar y editar como si fuera un conjunto de notas.
3. Guarda y haz push como cualquier proyecto Git.

---

### ✅ Opción 3: Editar desde GitHub

1. Ve a `docs/` en GitHub.
2. Abre un archivo `.md` y pulsa el lápiz ✏️ para editarlo online.
3. Al guardar, selecciona “commit directamente a `main`”.

> Esta acción también lanzará el despliegue automático.

---

## 🧱 Estructura principal

- `docs/funcionalidades/` → Documentación por funcionalidad (login, dashboard, etc.)
- `docs/equipo/` → Normas de trabajo, flujo Git, estilo
- `docs/entidades/` → Entidades del sistema (User, Quiz, etc.)
- `docs/despliegue/` → Guías de CI/CD, infraestructura, dominio

---

## 🛠️ ¿Cómo levantar Docusaurus en local?

Si necesitas probar cambios antes de hacer push:

```bash
npm install
npm run start
```

Esto abrirá la documentación en `http://localhost:3000`.

---

## ✅ CI/CD activo

Este repositorio utiliza:

- `actions/checkout@v4`
- `actions/setup-node@v4`
- `actions/upload-pages-artifact@v3`
- `actions/deploy-pages@v4`

Puedes ver el estado de despliegue en la pestaña **Actions**.

---
