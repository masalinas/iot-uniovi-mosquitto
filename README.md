# Description
Iot Mosquitto Docker Service

## Create and start service
```shell
docker-compose up -d
```

## Add or update a authentication user account
The default account created its: admin/password

```shell
docker-compose exec mosquitto mosquitto_passwd -b /mosquitto/config/password.txt admin uniovi
```

## Delete a authentication user account
```shell
docker-compose exec mosquitto mosquitto_passwd -D /mosquitto/config/password.txt admin
```

## Stop service
```shell
docker-compose stop
```

## Restart service
```shell
docker-compose start
```

## Remove service resources
```shell
docker-compose down
```

## Get service logs
```shell
docker-compose logs
```

## Subscribe to a broker topic
```shell
mosquitto_sub -h localhost -u admin -P uniovi -t sensor/temperature
```

## Publish a message to a broker topic
```shell
mosquitto_pub -h localhost -u admin -P uniovi -t sensor/temperature -m 35
```