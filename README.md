## Methods

### HEALTH CHECK
curl --location 'http://localhost:8080/health' \
--header 'Content-Type: application/json'

### GET
curl --location 'http://localhost:8080/api/proxy' \
--header 'Content-Type: application/json' \
--data '{
    "url": "https://reqres.in/api/users?page=2",
    "method": "GET"
}'

### POST
curl --location 'http://localhost:8080/api/proxy' \
--header 'Content-Type: application/json' \
--data '{
    "url": "https://reqres.in/api/users",
    "method": "POST",
    "body": {
        "name": "morpheus",
        "job": "leader"
    }
}'

### PUT
curl --location 'http://localhost:8080/api/proxy' \
--header 'Content-Type: application/json' \
--data '{
    "url": "https://reqres.in/api/users/2",
    "method": "PUT",
    "body": {
        "name": "morpheus",
        "job": "zion resident"
    }
}'

### DELETE
curl --location 'http://localhost:8080/api/proxy' \
--header 'Content-Type: application/json' \
--data '{
    "url": "https://reqres.in/api/users/2",
    "method": "DELETE"
}'


## Docker

docker-compose build
docker-compose up -d
docker-compose down
