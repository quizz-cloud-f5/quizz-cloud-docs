---
sidebar_position: 1
id: deploy-strategy
title: Estrategia de Despliegue
sidebar_label: Estrategia de Despliegue
---


## 🚀 Estrategia de despliegue

El despliegue a producción está automatizado para que, una vez finalizada una entrega, todo el sistema esté listo para ejecutarse en la nube con el menor esfuerzo manual posible.

---

### 🔁 Proceso general de despliegue

1. **Merge de `develop` a `main`**
    - Cuando todas las funcionalidades previstas para una entrega están listas y probadas, se hace merge de `develop` a `main`.
2. **Creación de un tag de versión**
    - Se crea un tag semántico (por ejemplo: `v1.0.0`).
    - Este tag es lo que **dispara automáticamente** el proceso de despliegue.
3. **Generación de artefactos**
    - GitHub Actions crea imágenes Docker para el **frontend** y el **backend**.
    - Estas imágenes quedan listas para ser desplegadas (empaquetadas con sus dependencias).

---

### 🐳 Repositorio de despliegue

Se ha creado un **repositorio exclusivo para el despliegue** de la aplicación, que contiene:

- Un archivo `docker-compose.yml` que:
    - Lanza el frontend y el backend desde las imágenes generadas.
    - Gestiona las variables de entorno necesarias para producción (claves, URLs, etc).
- Scripts de automatización para conectarse a una **instancia EC2 en AWS** y ejecutar el despliegue.
- Soporte para futuras mejoras, como balanceo de carga, certificados SSL, monitoreo, etc.

> ✅ Esto permite que la aplicación completa se levante con un solo comando desde el repositorio de despliegue.
> 

---

### 🌐 Entorno de producción

- La aplicación se ejecuta en una instancia **EC2** de Amazon Web Services.
- Se utiliza una base de datos gestionada con **RDS** para producción.
- En el futuro se añadirá:
    - 🟡 Compra y configuración de un dominio personalizado.
    - 🟡 Certificado **HTTPS** para navegación segura.
    - 🟡 Supervisión del sistema y alertas básicas.

---

### 📦 Beneficios de esta estrategia

- 🔁 **Automatización:** evita errores humanos y acelera el despliegue.
- 💡 **Reproducibilidad:** cualquiera puede replicar el entorno con los mismos pasos.
- 🛠️ **Separación de responsabilidades:** el despliegue se gestiona aparte del desarrollo.