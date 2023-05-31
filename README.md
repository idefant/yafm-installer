# Установщик YAFM + ExRates

Сборка адаптирована под работу с Traefik. Если Traefik еще не развернут, необходимо поднять контейнер с ним. Перед использованием обязательно заполнить домен и email для Let's Encrypt.

```sh
cd traefik
docker compose up -d
```

После того, как перешли на домен и убедились в работоспособности Traefik, необходимо
- запустить скрипт `install.sh`, который скачает репозитории `yafm`, `yafm-api`, `exrates-api`
- заменить параметры в `.env` в каждом проекте на свои
- заменить домены в `docker-compose.yml`
- поднять контейнеры:

```sh
chmod +x install.sh
./install.sh

nano yafm/.env
nano yafm-api/.env
nano exrates-api/.env

docker compose up -d
```