# Task 6 — Docker Compose

## Репозитории демо-приложения

Backend:
[https://gitlab.com/ratrace11/backend-demo1/-/tree/mmain](https://gitlab.com/ratrace11/backend-demo1/-/tree/mmain)

Frontend:
[https://gitlab.com/ratrace11/frontend-demo1/-/tree/mmain](https://gitlab.com/ratrace11/frontend-demo1/-/tree/mmain)

## Сборка Docker-образов


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

### Дополнительно: балансировка фронтенда

Для демонстрации работы балансировщика запущено два экземпляра frontend-контейнера:

- frontend1 и frontend2 внутри Docker-сети
- Nginx балансирует трафик между ними на порту 8080

После запуска docker compose up -d:

- Frontend: http://localhost:8080 — nginx распределяет запросы между frontend1 и frontend2  
- Backend: http://localhost:8081

> Для проверки балансировки можно обновлять страницу несколько раз или добавить разный идентификатор в index.html двух фронтендов, чтобы видеть, какой экземпляр отвечает.
