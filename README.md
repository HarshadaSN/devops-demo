# devops-demo

Spring Boot REST app, containerised with Docker and built by Jenkins.

## Tech
Java 17, Spring Boot, MySQL, Docker, Docker Compose, Jenkins

## Run locally
```
docker compose up -d --build
curl http://localhost:8080/actuator/health
```

## API
- GET /items: list items
- POST /items: add an item, body `{"name":"laptop"}`

## CI
Jenkins pipeline (Jenkinsfile) builds the image and pushes it to Docker Hub
as `harshadasn/devops-demo:<build-number>` and `latest`.

## Roadmap
- [x] Docker, Compose, Jenkins build and push
- [ ] Kubernetes deployment
- [ ] Prometheus and Grafana monitoring
- [ ] Terraform on AWS