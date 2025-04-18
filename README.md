# 🧩 APIs Backend

Repositorio exclusivo para las dos APIs del sistema de inventario:

- 🔐 **API de Usuarios** (registro, login y autenticación con JWT)
- 📦 **API de Productos** (CRUD vinculado al usuario autenticado)

Estas APIs conforman la solución backend de la actividad **GA4-220501096-AA1-EV01** del programa de formación SENA – Técnico en Programación de Software.

---

## 📦 Estructura del repositorio

```
inventario-apis/
├── api-usuarios/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── server.js
│   └── .env
├── api-productos/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── middleware/
│   ├── server.js
│   └── .env
└── README.md
```

---

## 🛠️ Tecnologías utilizadas

- Node.js
- Express
- MongoDB (local o Atlas)
- JWT (autenticación)
- Dotenv (variables de entorno)
- CORS

---

## ⚙️ Funcionalidad general

### 🔐 API de Usuarios (`http://localhost:3000/api/usuarios`)
- `POST /registrar`: Registrar nuevo usuario
- `POST /login`: Iniciar sesión y recibir token JWT

> Incluye validaciones básicas y encriptación de contraseñas (si se aplica).

### 📦 API de Productos (`http://localhost:4000/api/productos`)
- `GET /`: Listar productos del usuario autenticado
- `POST /`: Crear producto
- `GET /:id`: Obtener un producto específico
- `PUT /:id`: Actualizar producto
- `DELETE /:id`: Eliminar producto

> Todas las rutas están protegidas por middleware de autenticación (`authMiddleware.js`), que valida el token JWT y asocia productos al usuario correspondiente.

---

## ✅ Requisitos previos

- Tener instaladas las dependencias:
  - Node.js 16+
  - MongoDB local o cuenta en [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)

- Archivos `.env` ya configurados en ambas APIs:
  - `PORT`
  - `MONGO_URI`
  - `JWT_SECRET`

---

## 🚀 Instrucciones de ejecución

### 1. Clona el repositorio

```bash
git clone https://github.com/tu-usuario/inventario-apis.git
cd inventario-apis
```

### 2. Ejecuta la API de usuarios

```bash
cd api-usuarios
npm install
node server.js
```

### 3. Ejecuta la API de productos

```bash
cd ../api-productos
npm install
node server.js
```

---

## 🔐 Autenticación

Las rutas protegidas de productos requieren enviar el token JWT generado en el login.  
Envia el token en los headers así:

```http
Authorization: Bearer <tu_token>
```

---

## 🧪 Pruebas sugeridas

Puedes usar herramientas como **Thunder Client**, **Postman** o **Insomnia** para probar los endpoints manualmente.

---

## 📄 Licencia

Este proyecto es de uso educativo, creado para fines formativos dentro del SENA.

_Evidencia GA4-220501096-AA1-EV01. API del proyecto_  
_Luis Eduardo Narváez Madera_  
_Servicio Nacional de Aprendizaje - SENA_
_Técnico en Programación de Software_  
_Ficha 3069978_  
_Miguel Ángel López Cacho_  
_2025_

**Programa:** Tecnólogo en Análisis y Desarrollo de Software