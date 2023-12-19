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

## AWS configure
--> IAM for id and secret
--> Create ECR repository

aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/s4r5j5i1
docker build -t api_serverless .
docker tag api_serverless:latest public.ecr.aws/s4r5j5i1/api_serverless:latest
docker push public.ecr.aws/s4r5j5i1/api_serverless:latest
