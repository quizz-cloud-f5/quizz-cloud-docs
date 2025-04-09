---
sidebar_position: 1
id: production-stack
title: Stack en Producción
sidebar_label: Stack en Producción
---

El sistema de QuizzCloud está desplegado en un entorno de producción en la nube, utilizando tecnologías modernas y contenedores para facilitar el mantenimiento y la escalabilidad.

---

### 🔍 Vista general del stack

---

### 🧱 Componentes principales

### 🌐 Frontend

- **React + Vite**
- Desplegado como imagen Docker con ngnx
- Sirve la interfaz de usuario
- Comunica con el backend a través de API REST por /api
- Gestión del estado y rutas protegidas con JWT

### 🧠 Backend

- **Spring Boot (Java)**
- API REST segura con JWT y roles
- Expone endpoints públicos y privados
- Validación, autenticación y lógica de negocio
- Integración continua con GitHub Actions

### 🐳 Infraestructura

- **Contenedores Docker** para frontend y backend
- **docker-compose** en un repo separado para orquestar todo
- Montado en una **instancia EC2 en AWS**
- Conexión a **PostgreSQL en Amazon RDS**

---

### 🚀 Proceso de despliegue (CD)

1. Al hacer `merge` a `main`, se crea un **tag** (ej: `v1.1.0`)
2. GitHub Actions construye las imágenes Docker del frontend y backend
3. Se suben las imágenes y el `docker-compose` las usa para desplegar
4. Se conecta automáticamente al servidor EC2
5. Se levanta la aplicación con `docker-compose up -d`

---

### 🔐 Seguridad y producción

- Certificados HTTPS (pendiente de configurar)
- Variables de entorno sensibles gestionadas con `.env` en EC2 (no versionadas)
- Puerto 443 abierto para HTTPS
- Protecciones básicas activadas en Spring Security