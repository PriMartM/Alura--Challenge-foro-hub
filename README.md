# 🧠 Foro Hub - API RESTful con Spring Boot

Una poderosa API REST construida con Java 17 y Spring Boot 3.5.3, orientada a la gestión eficiente de tópicos en un foro de discusión. Esta aplicación permite registrar, autenticar y gestionar usuarios, así como realizar operaciones CRUD sobre tópicos.

---

## 📖 Descripción

**Foro Hub** es un backend educativo diseñado con una arquitectura en capas y buenas prácticas de desarrollo. Está centrado en la seguridad, validación de datos y control de versiones de base de datos, facilitando su mantenimiento y escalabilidad a largo plazo.

---

## ✨ Funcionalidades

- 🔐 **Autenticación y autorización** con JWT
- 🧾 **Operaciones CRUD completas** sobre tópicos
- 🧠 **Validación de datos** con Jakarta Bean Validation
- 🛡️ **Hashing de contraseñas** con BCrypt
- 🔄 **Migraciones de base de datos** gestionadas con Flyway
- 🧪 **Tests unitarios** con Spring Boot Test y Spring Security Test

---

## 🛠️ Tecnologías

| Categoría       | Tecnología                     |
|-----------------|--------------------------------|
| Lenguaje        | Java 17                        |
| Framework       | Spring Boot 3.5.3              |
| Seguridad       | Spring Security + JWT          |
| Base de Datos   | MySQL                          |
| ORM             | Spring Data JPA (Hibernate)    |
| Validación      | Jakarta Bean Validation        |
| Migraciones     | Flyway                         |
| Build Tool      | Maven                          |
| Utilidades      | Lombok, DevTools               |

---

---

## 🔐 Seguridad

- **JWT:** Protección de endpoints mediante tokens.
- **BCrypt:** Almacenamiento seguro de contraseñas.
- **Spring Security:** Configuración personalizada para roles y permisos.

---


---

## 🔐 Seguridad

- Cada endpoint protegido requiere un token **JWT válido** en el header `Authorization: Bearer <TOKEN>`.
- Las contraseñas se almacenan usando **BCrypt**, impidiendo el acceso en texto plano.
- Solo usuarios autenticados pueden crear, editar o eliminar tópicos. La lectura es pública.

---

## 📡 Endpoints de la API

### 🔑 Autenticación

POST /auth

**Request:**
```json
{
  "login": "alumno@gmail.com",
  "contrasena": "123456"
}
```
Response:
```
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```
📌 Gestión de Tópicos
POST /topicos → Crear tópico (requiere JWT)

GET /topicos → Listar todos (público)

GET /topicos/{id} → Detalle de tópico (requiere JWT)

PUT /topicos/{id} → Editar tópico (requiere JWT)

DELETE /topicos/{id} → Eliminar tópico (requiere JWT)




