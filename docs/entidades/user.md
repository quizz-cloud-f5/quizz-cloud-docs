---
sidebar_position: 1
id: user_entity
title: User
sidebar_label: User
---



## 🧾 Descripción

La entidad `User` representa a un usuario autenticado dentro del sistema. Está integrada con Spring Security a través de la implementación de la interfaz `UserDetails`, lo que permite utilizarla directamente en los mecanismos de autenticación y autorización del backend.

---

## 🗂️ Ubicación

`org.quizzcloud.backend.auth.model.User`

---

## 🧩 Campos

| Campo         | Tipo        | Descripción                                                |
|---------------|-------------|------------------------------------------------------------|
| `id`          | `String`    | Identificador único del usuario (UUID generado al crear). |
| `email`       | `String`    | Correo electrónico del usuario, único y requerido.        |
| `password`    | `String`    | Contraseña codificada del usuario (**@JsonIgnore**).      |
| `role`        | `Enum<Role>`| Rol del usuario en la plataforma (`USER`, `ADMIN`, etc). |
| `firstLogin`  | `boolean`   | Indica si el usuario está accediendo por primera vez.     |

---

## 🛠️ Comportamiento

- El `id` se genera automáticamente con `UUID` al persistir el usuario si no fue establecido.
- El campo `password` está anotado con `@JsonIgnore` para evitar su exposición en respuestas JSON.
- La propiedad `role` se convierte en una autoridad con el prefijo `"ROLE_"` para integración con Spring Security.

---

## 🔐 Métodos de seguridad (`UserDetails`)

Implementa los siguientes métodos requeridos por Spring Security:

| Método                        | Retorno | Descripción                                             |
|------------------------------|---------|---------------------------------------------------------|
| `getAuthorities()`           | `List`  | Devuelve la autoridad basada en el rol del usuario.     |
| `getUsername()`              | `String`| Devuelve el email del usuario.                          |
| `isAccountNonExpired()`      | `true`  | No se expiran cuentas (por defecto).                    |
| `isAccountNonLocked()`       | `true`  | No se bloquean cuentas (por defecto).                   |
| `isCredentialsNonExpired()` | `true`  | No se expiran credenciales (por defecto).               |
| `isEnabled()`                | `true`  | El usuario está habilitado (por defecto).               |

---

## 📦 Anotaciones clave

- `@Entity` → Marca la clase como una entidad JPA.
- `@Table(name = "users")` → Define la tabla `users` en la base de datos.
- `@Builder`, `@Getter`, `@Setter`, `@NoArgsConstructor`, `@AllArgsConstructor` → Anotaciones de Lombok para facilitar la construcción de objetos y acceso a propiedades.
- `@Enumerated(EnumType.STRING)` → Guarda el valor del `role` como texto en la base de datos.

---

## 🧠 Consideraciones futuras

- Se puede extender con campos como `name`, `createdAt`, `lastLogin`, etc.
- Puede integrarse con auditoría (`@CreatedDate`, `@LastModifiedDate`) o logging de actividad.
- Es recomendable implementar control de bloqueo/expiración real si se requieren restricciones más estrictas.
