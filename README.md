# Task 7

## Nginx
- Обратный прокси для сервисов:
  - / → фронтенд (`frontend1` + `frontend2`)
  - /api/ → backend
- Редирект HTTP → HTTPS
- SSL-сертификаты: nginx/ssl

## Мониторинг
- Prometheus собирает метрики всех сервисов:
  - Node Exporter → контейнеры
  - Nginx Exporter → Nginx
  - Postgres Exporter → база данных
  - Prometheus → сам
- Метрики доступны: [http://localhost:9090/targets](http://localhost:9090/targets)

## Логирование
- Loki + Promtail для централизованного сбора логов всех контейнеров
- Grafana подключена к Loki как источнику данных
- Дашборды: [http://localhost:3000](http://localhost:3000)

## Запуск
```bash
docker-compose up -d --build
Проверка
Список запущенных контейнеров:
docker ps
Метрики Prometheus: http://localhost:9090/targets
Grafana: http://localhost:3000
