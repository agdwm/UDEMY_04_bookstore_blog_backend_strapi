# Backend Strapi - Bookstore & Blog CMS

Backend API REST construido con **Strapi v5.31.2** para gestionar contenido de libros, posts de blog y usuarios. Actúa como CMS headless para la aplicación frontend _Next.js_.

## 📋 Descripción del Proyecto

Este backend es el sistema de gestión de contenidos para una aplicación de tienda de libros e blog. Proporciona APIs REST para:

- **Gestión de Libros**: CRUD de libros con precios, stock, descripción rica e imágenes
- **Gestión de Posts**: Publicación de artículos de blog con contenido enriquecido
- **Autenticación**: Gestión de usuarios con el plugin de permisos
- **Almacenamiento de Imágenes**: Integración con Cloudinary para subida y gestión de media
- **Base de Datos**: PostgreSQL para persistencia de datos

## 🔗 Repositorio Complementario

**Frontend**: [UDEMY_04_bookstore_blog_frontend_nextjs](https://github.com/agdwm/UDEMY_04_bookstore_blog_frontend_nextjs) - Aplicación frontend que consume este backend

## 🛠️ Tecnologías Utilizadas

### Core Framework

- **Strapi v5.31.2** - CMS headless y generador de APIs REST
- **Node.js** - v20.x - v24.x
- **TypeScript** - Tipado estático

### Dependencias principales

- **PostgreSQL (pg 8.8.0)** - Base de datos relacional
- **React 18** - Para el panel admin de Strapi
- **React Router DOM 6** - Enrutamiento en admin
- **Styled Components 6** - Estilos en el panel admin
- **Cloudinary** - Proveedor de almacenamiento para archivos media
- **Strapi Plugins**:
  - `@strapi/plugin-cloud` - Cloud deployment
  - `@strapi/plugin-users-permissions` - Gestión de permisos y usuarios

## 📦 Estructura del Proyecto

```
backend_strapi/
├── src/
│   ├── api/
│   │   ├── book/                 # API de libros
│   │   │   ├── controllers/
│   │   │   ├── routes/
│   │   │   ├── services/
│   │   │   └── content-types/
│   │   └── post/                 # API de posts
│   │       ├── controllers/
│   │       ├── routes/
│   │       ├── services/
│   │       └── content-types/
│   ├── admin/                    # Customizaciones del panel admin
│   └── extensions/
├── config/
│   ├── admin.ts                  # Config panel admin
│   ├── api.ts                    # Config API REST
│   ├── database.ts               # Config base de datos
│   ├── middlewares.ts
│   ├── plugins.ts
│   └── server.ts
├── public/
│   └── uploads/                  # Almacenamiento local de uploads
├── database/
│   └── migrations/               # Migraciones de BD
└── types/
    └── generated/                # Tipos TypeScript auto-generados
```

## 🚀 Inicio Rápido

### Requisitos Previos

- **Node.js**: v20.x o superior
- **npm** o **pnpm**: v6.0.0 o superior
- **PostgreSQL**: Base de datos configurada

### Instalación

1. **Clonar el repositorio y navegar al backend**:

```bash
cd backend_strapi
```

2. **Instalar dependencias**:

```bash
npm install
# o con pnpm
pnpm install
```

3. **Configurar variables de entorno**:
   Crear archivo `.env` en la raíz del proyecto:

```env
# Database
DATABASE_CLIENT=postgres
DATABASE_HOST=localhost
DATABASE_PORT=5432
DATABASE_NAME=strapi_db
DATABASE_USERNAME=postgres
DATABASE_PASSWORD=your_password

# App
APP_KEYS=your_app_keys
API_TOKEN_SALT=your_token_salt
ADMIN_JWT_SECRET=your_admin_secret
JWT_SECRET=your_jwt_secret

# Cloudinary (Opcional)
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_KEY=your_cloudinary_key
CLOUDINARY_SECRET=your_cloudinary_secret
```

### Comandos Disponibles

- **Desarrollo**:

```bash
npm run dev
# o
npm run develop
```

Inicia Strapi en modo desarrollo con auto-recarga.

- **Producción**:

```bash
npm start
```

Inicia Strapi en modo producción.

- **Build**:

```bash
npm run build
```

Construye el panel admin.

- **Console**:

```bash
npm run console
```

Abre una consola interactiva.

- **Actualizar Strapi**:

```bash
npm run upgrade
```

Actualiza Strapi a la última versión.

## 📚 Endpoints de API

Una vez iniciado el servidor (por defecto en `http://localhost:1337`):

### Libros

- `GET /api/books` - Obtener todos los libros
- `GET /api/books/:id` - Obtener un libro específico
- `POST /api/books` - Crear un nuevo libro (requiere autenticación)
- `PUT /api/books/:id` - Actualizar un libro (requiere autenticación)
- `DELETE /api/books/:id` - Eliminar un libro (requiere autenticación)

### Posts

- `GET /api/posts` - Obtener todos los posts
- `GET /api/posts/:id` - Obtener un post específico
- `POST /api/posts` - Crear un nuevo post (requiere autenticación)
- `PUT /api/posts/:id` - Actualizar un post (requiere autenticación)
- `DELETE /api/posts/:id` - Eliminar un post (requiere autenticación)

### Autenticación

- `POST /api/auth/local/register` - Registrar nuevo usuario
- `POST /api/auth/local` - Login de usuario
- `GET /api/users/me` - Obtener datos del usuario autenticado

## 🔑 Panel Admin

Acceder al panel admin de Strapi en: `http://localhost:1337/admin`

Aquí puedes:

- Crear, editar y eliminar contenido (libros y posts)
- Gestionar usuarios y permisos
- Subir y gestionar media
- Configurar plugins y extensiones
- Monitorear la aplicación

## 🗄️ Base de Datos

El proyecto utiliza **PostgreSQL**. Las migraciones se encuentran en `database/migrations/`.

Para resetear la base de datos:

```bash
npm run strapi migrate:reset
```

## 🚢 Despliegue

Strapi soporta múltiples opciones de despliegue:

- **Strapi Cloud** (Recomendado):

```bash
npm run deploy
```

- **Vercel, Heroku, Railway, etc.**:
  Consulta la [documentación de deployment](https://docs.strapi.io/dev-docs/deployment)

## 📖 Documentación y Recursos

- [Documentación Oficial de Strapi](https://docs.strapi.io)
- [Guía de API REST](https://docs.strapi.io/dev-docs/rest-api/introduction)
- [Guía de Plugins](https://docs.strapi.io/dev-docs/plugins/introduction)
- [Tutorials](https://strapi.io/tutorials)

## 📝 Licencia

Este proyecto está bajo la licencia especificada en el archivo `license.txt`.

---

**Backend desarrollado con Strapi v5.31.2** | [Documentación de Strapi](https://strapi.io)
