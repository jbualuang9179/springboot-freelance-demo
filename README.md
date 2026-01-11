# springboot-freelance-demo
Microservices  Kafka (Async / Event-driven)  Redis Cache  Security (JWT)  Run  Docker Compose

## Run
1) build jar
   mvn -q -DskipTests clean package

2) start
   docker compose up --build

## Get token
curl -X POST "http://localhost:8081/auth/token?user=demo"

## Create order
curl -X POST http://localhost:8081/api/orders \
  -H "Authorization: Bearer <TOKEN>" \
  -H "Content-Type: application/json" \
  -d '{"productId":"P001","amount":1000}'

## Check status (from Redis/DB)
curl -X GET http://localhost:8081/api/orders/<ORDER_ID> \
  -H "Authorization: Bearer <TOKEN>"

