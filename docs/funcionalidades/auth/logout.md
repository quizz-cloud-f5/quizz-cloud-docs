---
sidebar_position: 1
id: logout
title: Logout
sidebar_label: Logout
---

> Como **usuario autenticado**,  
> quiero **cerrar sesión de forma segura**,  
> para **salir de mi cuenta y proteger mi información personal**.

---

## ✅ Criterios de aceptación cumplidos

- [x] El usuario puede cerrar sesión desde cualquier página de la plataforma.
- [x] Al hacer logout se elimina el token de autenticación.
- [x] El usuario es redirigido automáticamente a la pantalla de inicio público.

---

## 📲 API relacionada

> En la mayoría de implementaciones con JWT, el logout **se maneja del lado del cliente**.
> No es necesaria una petición al backend, salvo que se quiera registrar la acción.

| Método | Endpoint          | Descripción                  |
|--------|-------------------|------------------------------|
| N/A    | N/A               | El logout es gestionado por frontend. |

---

## 🧩 Archivos implicados

- `frontend/src/context/AuthContext.tsx`
- `frontend/src/components/Navbar.tsx`
- `frontend/src/services/auth.ts`
- `frontend/src/pages/Login.tsx`

---

## 🖼️ Capturas

> (Opcionalmente puedes añadir un botón de logout visible en la barra superior)

```tsx
<Button onClick={logout}>Cerrar sesión</Button>
```

---

## ⚠️ Validaciones

- El token se elimina correctamente de `localStorage` o cookies.
- El estado de usuario (AuthContext) se reinicia.
- El usuario no puede acceder a rutas privadas tras cerrar sesión.
- Se previene la navegación hacia atrás a zonas protegidas.

---

## 🧪 Casos de prueba

- ✅ Usuario cierra sesión → token eliminado → redirige a `/login`.
- ❌ Intenta acceder a `/dashboard` tras logout → redirige a `/login`.
- ✅ Botón de logout siempre visible cuando el usuario está logueado.

---

## 🧠 Notas

- En caso de necesitar control más estricto, puede implementarse un **logout activo en backend** para registrar cierre de sesión o invalidar refresh tokens.
- Se recomienda eliminar cualquier información sensible en memoria al hacer logout.
- Si se usa refresco automático de sesión (tokens de renovación), también debe invalidarse ese flujo en logout.
