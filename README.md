# UntitledProject

## Setup

### InfluxDB

Run influxdb in a detached container and use the current directory (run in UntitledProject/influxdbstorage)

`docker run -d -p 8086:8086 --name influxdb2 -v %cd%:/var/lib/influxdb2 influxdb:2.0`

Run influxdb auto setup. Replace variables. --force to skip confirmation

`docker exec influxdb2 influx setup --username $username --password $pwd --org $org --bucket $bucket --force`

Generate token

`docker exec influxdb2 influx auth list --user $username --hide-headers`