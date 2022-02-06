# Description
Iot Mosquitto Docker Service

## Create and start  mosquitto service
docker-compose up -d

## Add or update a authentication user account
docker-compose exec mosquitto mosquitto_passwd -b /mosquitto/config/password.txt admin uniovi

## Delete a authentication user account
docker-compose exec mosquitto mosquitto_passwd -D /mosquitto/config/password.txt admin

## Remove stop 
docker-compose stop

## Restart mosquitto service
docker-compose start

## Remove all resources
docker-compose down

## Get mosquitto logs
docker-compose logs

## Check a subscrive to the previous topic
mosquitto_sub -h localhost -u admin -P uniovi -t "sensor/temperature"

## Check and publish a message in a topic
mosquitto_pub -h localhost -u admin -P uniovi -t sensor/temperature -m 35
