Часть 1 - Helm и Kompose.
Из docker-compose проекта prometheus-grafana создал helm-chart через kompose convert --chart.
Доработал grafana-service.yaml, добавил LoadBalancer и externalIPs.
Вынес параметры в values.yaml. Установил релиз helm install promgra ./promgra.
Проверил апгрейд: helm upgrade promgra ./ --set EXTERNAL_PORT=3456.

Часть 2 - Kustomize.
Из базового проекта flask+redis развернул dev и prod окружения.
Вынес имя Redis-сервера в переменную окружения REDIS_HOST в app.py.
Dev: префикс dev-, порт 54321, 2 реплики, ENV=DEVELOPMENT.
Prod: префикс prod-, порт 12345, 5 реплик, ENV=PRODUCTION.
