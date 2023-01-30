microservices

## Symfony:  Очереди сообщений AMQP с использованием RabbitMQ

Stack used: Symfony 6.1, PHP 8.1, RabbitMQ 3

### Установка

```shell
git clone https://github.com/vlad-planet/ms_symfony-rabitmq_docker
cd ms_symfony-rabitmq_docker/
docker-compose up --build -d
```

### Запуск тэста

Запустить сервер 
```shell
docker exec -it app2 php bin/console app:send
```

Выходные данные
```shell
docker exec -it app2 php bin/console messenger:consume -vv async
```

В качестве выходных данных вы должны увидеть сообщения.
```shell
[warning] APP2: {STATUS_UPDATE} - Worker X assigned to Y
[info] Message App\Message\StatusUpdate handled by App\Handler\StatusUpdateHandler::__invoke
[info] App\Message\StatusUpdate was handled successfully (acknowledging to transport).
```
