# Docker Starter Kit

This Docker Starter Kit provides a simple and structured way to containerize applications using Docker. It includes basic instructions for setting up, building, and running Docker containers efficiently.

## Prerequisites

Before using this starter kit, ensure you have the following installed:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/) (if needed)

## Getting Started

### 1. Clone the Repository
```sh
 git clone https://github.com/your-repo/docker-starter-kit.git
 cd docker-starter-kit
```

### 2. Start Services Using Docker Compose
```sh
 docker-compose up -d
```

### 3. Stop Services
```sh
 docker-compose down
```

## Services Overview

The Docker Compose setup includes the following services:

- **Client** (Frontend)
  - Uses `Dockerfile.client`
  - Runs on port `8080`
  - Watches for changes in the `client` directory
  - Communicates with the `server` service

- **Server** (Backend)
  - Uses `Dockerfile.server`
  - Runs on port `3000`
  - Watches for changes in the `server` directory
  - Connects to PostgreSQL, MySQL, and MongoDB databases

- **PostgreSQL**
  - Uses `postgres:15-alpine` image
  - Runs on port `5432`
  - Stores data in `postgres_data` volume

- **MySQL**
  - Uses `mysql:8.0` image
  - Runs on port `3306`
  - Stores data in `mysql_data` volume

- **MongoDB**
  - Uses `mongo:6` image
  - Runs on port `27017`
  - Stores data in `mongo_data` volume

## Folder Structure
```
├── Dockerfile.client
├── Dockerfile.server
├── docker-compose.yml
├── .dockerignore
├── client/               # Frontend source code
├── server/               # Backend source code
└── README.md
```

## Environment Variables

- **Client**:
  - `NODE_ENV=development`
  - `VITE_API_URL=http://server:3000`

- **Server**:
  - `NODE_ENV=development`
  - `POSTGRES_URL=postgresql://postgres:postgres@postgres:5432/app_db`
  - `MYSQL_URL=mysql://root:root@mysql:3306/app_db`
  - `MONGODB_URL=mongodb://mongo:27017/app_db`

## Troubleshooting

- Check container logs:
  ```sh
  docker logs my-app-container
  ```
- Restart Docker if necessary.
- Ensure ports are not occupied by other applications.

## License

This project is licensed under the MIT License.

---

Happy Dockering! 🚀

