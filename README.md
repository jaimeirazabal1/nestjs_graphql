# 🚀 NestJS + GraphQL + Docker Demo

Este proyecto demuestra el poder de GraphQL con NestJS, mostrando cómo crear una API moderna, eficiente y fácil de mantener.

## ✨ Características

- 🎯 GraphQL con Apollo Server
- 🗄️ PostgreSQL como base de datos
- 🔄 TypeORM para el manejo de la base de datos
- 🐳 Docker para containerización
- 📊 pgAdmin para administración de la base de datos
- 🚀 Hot-reload en desarrollo

## 🛠️ Requisitos Previos

- Node.js (v18 o superior)
- Docker y Docker Compose
- npm o yarn

## 🚀 Instalación

1. Clona el repositorio:
```bash
git clone <tu-repositorio>
cd nestjs_graphql
```

2. Instala las dependencias:
```bash
npm install
```

3. Inicia los servicios con Docker:
```bash
docker-compose up -d
```

## 🏃‍♂️ Desarrollo

Para iniciar el servidor en modo desarrollo:

```bash
npm run start:dev
```

## 🌐 Acceso a los Servicios

- **GraphQL Playground**: http://localhost:3000/graphql
- **pgAdmin**: http://localhost:5050
  - Email: admin@admin.com
  - Password: admin

## 📝 Ejemplos de Consultas GraphQL

### Crear un Usuario
```graphql
mutation {
  createUser(createUserInput: {
    name: "Juan Pérez"
    email: "juan@example.com"
    password: "123456"
  }) {
    id
    name
    email
    createdAt
  }
}
```

### Obtener Todos los Usuarios
```graphql
query {
  users {
    id
    name
    email
    createdAt
  }
}
```

### Obtener un Usuario Específico
```graphql
query {
  user(id: "user-id") {
    id
    name
    email
    createdAt
  }
}
```

## 🏗️ Estructura del Proyecto

```
src/
  ├── users/                 # Módulo de usuarios
  │   ├── dto/              # Data Transfer Objects
  │   ├── entities/         # Entidades de TypeORM
  │   ├── users.module.ts   # Módulo de usuarios
  │   ├── users.service.ts  # Servicio de usuarios
  │   └── users.resolver.ts # Resolver de GraphQL
  ├── app.module.ts         # Módulo principal
  └── main.ts              # Punto de entrada
```

## 🔧 Configuración

### Variables de Entorno
Crea un archivo `.env` en la raíz del proyecto:

```env
# Database
DATABASE_HOST=postgres
DATABASE_PORT=5432
DATABASE_USERNAME=postgres
DATABASE_PASSWORD=postgres
DATABASE_NAME=nestjs_graphql

# App
PORT=3000
NODE_ENV=development
```

## 🐳 Docker

El proyecto incluye los siguientes servicios:

- **app**: Aplicación NestJS
- **postgres**: Base de datos PostgreSQL
- **pgadmin**: Interfaz de administración de PostgreSQL
- **redis**: Cache (opcional)

Para iniciar todos los servicios:
```bash
docker-compose up -d
```

Para detener los servicios:
```bash
docker-compose down
```

## 📚 Recursos Adicionales

- [Documentación de NestJS](https://docs.nestjs.com/)
- [Documentación de GraphQL](https://graphql.org/learn/)
- [Documentación de TypeORM](https://typeorm.io/)
- [Documentación de Docker](https://docs.docker.com/)

## 🤝 Contribuir

Las contribuciones son bienvenidas. Por favor, abre un issue primero para discutir los cambios que te gustaría hacer.

## 📝 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## 👥 Autores

- Jaime Irazabal -

## 🙏 Agradecimientos

- NestJS Team
- GraphQL Team
- TypeORM Team
- Docker Team
