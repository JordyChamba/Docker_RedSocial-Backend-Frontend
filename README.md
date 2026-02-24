# 🚀 SocialHub Fullstack Project

Este repositorio agrupa los dos subproyectos que constituyen SocialHub: un backend en Java/Spring Boot y un frontend en React/TypeScript. Además se incluye una configuración Docker para levantar ambos servicios fácilmente.

---

## 📁 Estructura general

```
/socialHub
├── backend/       # Aplicación Spring Boot (Java 21+, Maven)
├── frontend/      # SPA React + Vite + TypeScript
├── docker-compose.yml  # Orquesta backend + frontend
├── Dockerfile?         # (solo generados en cada subcarpeta)
└── README.md           # Este fichero
```

Cada subcarpeta es a su vez un proyecto Git independiente; puedes tratarlos como submódulos o simplemente borrar los `.git` internos y gestionar todo como un monorepo (ver notas abajo).

---

## 🧩 ¿Qué contiene cada subproyecto?

### Backend (`/backend`)
- API REST con **Spring Boot 3**, seguridad JWT y comunicación WebSocket para notificaciones.
- Modelado en PostgreSQL, servicios, repositorios, DTOs, controladores, etc.
- Tests unitarios básicos ya incluidos.
- Documentación Swagger integrada.

Lee el README localizado en `/backend/README.md` para instrucciones detalladas de instalación, ejecución y uso.

### Frontend (`/frontend`)
- Single‑page application con **React 18**, **TypeScript**, **Vite** y **Tailwind CSS**.
- Gestiona autenticación, feeds, posts, comentarios, notificaciones en tiempo real y más.
- Configuración de proxy para llamadas a la API.

Encuentra la guía completa en `/frontend/README.md`.

---

## 🐳 Docker & Docker Compose

Se han proporcionado `Dockerfile` en cada subcarpeta; el `docker-compose.yml` en la raíz construye y arranca ambos servicios:

```bash
cd /home/jpeter/Escritorio/socialHub
docker compose up --build
```

- Backend disponible en `http://localhost:8080`
- Frontend servido en `http://localhost:3000`

El compose usa una red `app-net` interna; puedes ajustar variables de entorno mediante un `.env` o directamente en el fichero.

---

## 📦 Gestión de Git

Opciones:
1. **Monorepo**: elimina los `.git` internos en `backend` y `frontend` y versiona todo desde la raíz.
2. **Repositorios separados**: conserva cada subcarpeta con su propio control de versiones y añádelas como submódulos o subtrees al repo principal.

Elige la estrategia que encaje con tu flujo de trabajo.

---

## 🧪 Comandos rápidos

```bash
# backend
cd backend
mvn clean install      # compila
mvn spring-boot:run    # ejecuta

# frontend
dd frontend
npm install
tnpm run dev           # servidor dev

# docker
docker compose up --build
```

---

## 📚 Recursos adicionales

- `/backend/README.md` – detalles del backend
- `/frontend/README.md` – detalles del frontend
- `/backend/HELP.md` – información de ayuda interna
- `/backend/API_DOCUMENTATION.md` – documentación de la API

---

¡Feliz hacking! 🛠️  
Este proyecto está preparado para escalar y servir como base para cualquier red social real.
