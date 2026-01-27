# Task 6 — Docker Compose

## Репозитории демо-приложения

Backend:
[https://gitlab.com/ratrace11/backend-demo1/-/tree/mmain](https://gitlab.com/ratrace11/backend-demo1/-/tree/mmain)

Frontend:
[https://gitlab.com/ratrace11/frontend-demo1/-/tree/mmain](https://gitlab.com/ratrace11/frontend-demo1/-/tree/mmain)

## Сборка Docker-образов

### Backend
```bash
cd backend-demo
docker build -t task6-backend .
Frontend
cd frontend-demo
docker build -t task6-frontend .
Запуск приложения
cd task6
docker compose up -d
После запуска:
Frontend доступен по адресу: http://localhost:8080
Backend доступен по адресу: http://localhost:8081

---
