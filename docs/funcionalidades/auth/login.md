---
sidebar_position: 1
id: login
title: Login
sidebar_label: Login
---


> Como **usuario registrado**,  
> quiero **iniciar sesión con mi email y contraseña**,  
> para **acceder a mi cuenta y realizar simulaciones personalizadas**.

---

## ✅ Criterios de aceptación cumplidos

- [x] El usuario puede iniciar sesión con credenciales válidas.
- [x] Se muestra un mensaje de error si las credenciales no son válidas.
- [x] Tras el login exitoso, se redirige al panel principal o dashboard.

---

## 📲 API relacionada

| Método | Endpoint          | Descripción                          |
|--------|-------------------|--------------------------------------|
| POST   | /api/auth/login   | Inicia sesión y retorna un JWT token |

### 🔸 Ejemplo de Request:
```json
{
  "email": "usuario@dominio.com",
  "password": "********"
}
```

### 🔹 Ejemplo de Response:
```json
{
  "token": "jwt-token-generado",
  "user": {
    "id": "123",
    "name": "Nombre del Usuario",
    "role": "alumno"
  }
}
```

---

## 🧩 Archivos implicados
- `frontend/src/modules/auth`

---

## 🖼️ Capturas

<img width="454" alt="Pantalla de login" src="https://github.com/user-attachments/assets/41aaed1b-3811-4975-8074-cca4ac004c03" />

---

## ⚠️ Validaciones

- **Email**: obligatorio, debe tener formato válido (`usuario@dominio.com`)
- **Contraseña**: obligatoria, mínimo 6 caracteres
- Desactivación del botón mientras se procesa el login
- Mensajes claros en caso de:
  - Credenciales inválidas
  - Error del servidor
  - Campos vacíos

---

## 🧪 Casos de prueba

- ✅ Usuario introduce email y contraseña correctos → redirige a `/dashboard`
- ❌ Email válido + contraseña incorrecta → mensaje de error “Credenciales inválidas”
- ❌ Campos vacíos → mensaje “Campo requerido”
- ❌ Email con formato inválido → validación cliente

---

## 🧠 Notas

- El token JWT se almacena en `localStorage` o en cookies (según la implementación de seguridad).
- Se utiliza `AuthContext` para compartir el estado de sesión en todo el frontend.
- En el backend:
  - Se utiliza `bcrypt` para verificar la contraseña.
  - El token tiene expiración definida (por ejemplo, 1h).
- El diseño está optimizado para dispositivos móviles.
- En el futuro se puede implementar login con Google u otro proveedor OAuth.
