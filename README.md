## Overview

This is an **Dockerized** and authentication-protected Todo App using **Node.js**, **Express.js**, **bcrypt**, **JWT authentication**, **Prisma**, and **PostgreSQL**. The app allows users to:

- **Register**: Create a new account.
- **Login**: Authenticate and receive a JWT token.
- **Manage Todos**: Perform auth protected CRUD operations on their own todo tasks after logging in.

### Example Workflow

1. **Define or Update Schema**: Modify the `schema.prisma` file to change your database structure.
2. **Create Migrations**: Use Prisma to generate and apply migrations.
3. **Run Docker Compose**: Build and run the Node.js app and PostgreSQL using Docker Compose.
4. **Interact with the API**: Use the frontend or API client (e.g., Postman) to register, login, and manage todos.

This project structure and workflow will help organize your code and make it easier to maintain and scale as your application grows.

## Getting Started

0. **Install Docker Desktop**

1. **Clone the Repository**:

```bash
git clone https://github.com/Goutam-Mahur/todo-app.git
cd todo-app
```

2. **Generate the Prisma Client**:

```bash
npx prisma generate
```

3. **Build your docker images**:

```bash
docker compose build
```

4. **Create PostgreSQL migrations and apply them**:

```bash
docker compose run app npx prisma migrate dev --name init
```

_Also_ - to run/apply migrations if necessary:

```bash
docker-compose run app npx prisma migrate deploy
```

5. **Boot up 2x docker containers**:

```bash
docker compose up
```

_or_

```bash
docker compose up -d
```

If you want to boot it up without it commandeering your terminal (you'll have to stop if via Docker Desktop though).

6. **To login to docker PostgreSQL database (from a new terminal instance while docker containers are running) where you can run SQL commands and modify database!**:

```bash
docker exec -it postgres-db psql -U postgres -d todoapp
```

7. **To stop Docker containers**:

```bash
docker compose down
```

8. **To delete all docker containers**:

```bash
docker system prune
```

9. **Access the App**:

Open `http://localhost:5003` (or `localhost:3000` if changed) in your browser to see the frontend. You can register, log in, and manage your todo list from there.
