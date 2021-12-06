# Experimentations with Debezium

## Usage

### Launch

```
docker-compose up
curl -X POST --url http://localhost:8083/connectors --header 'Content-Type: application/json' --data @connect-sink-config
curl -X POST --url http://localhost:8083/connectors --header 'Content-Type: application/json' --data @connect-source-config
```

### Update source DB

```
docker exec -it debezium-el-redpanda-1 /bin/bash
debezium-el-redpanda-1> mysql -u mysqluser -pmysqlpw
mysql> use inventory;
mysql> UPDATE customers SET first_name='Anne Marie' WHERE id=1004;
```