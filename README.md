# Roboshop Application Dockerfiles

This repository contains Dockerfiles for the **Roboshop Application**, a microservices-based e-commerce platform for selling robots. Each service within Roboshop has its own dedicated Dockerfile, following industry best practices for containerization and security.

## Key Features

- **Minimal Images**: All Dockerfiles use minimal base images to reduce image size and improve security.
- **Official Images**: Official images from trusted sources are used as base images for all services.
- **Non-Root Containers**: Containers are configured to run as non-root users, enhancing security.
- **Multi-Stage Builds**: Dockerfiles employ multi-stage builds to ensure only required artifacts are present in final images.
- **Optimized Docker Layers**: Dockerfiles are structured to optimize layer caching and improve build times.

## How to Build Docker Images

You can build images for each microservice by navigating to the respective directory and running:

```sh
docker build -t <service-name>:<tag> .
```

Replace `<service-name>` and `<tag>` with the appropriate values for the microservice.

## Running with Docker Compose

The recommended way to run the entire Roboshop application is with Docker Compose. Ensure you have a valid `docker-compose.yml` file at the root of your project (or the location of your choice).

To start all services:

```sh
docker-compose up -d
```

To stop all services:

```sh
docker-compose down
```

## Directory Structure

```
├── cart/
│   └── Dockerfile
├── catalogue/
│   └── Dockerfile
├── frontend/
│   └── Dockerfile
├── mongodb/
│   └── Dockerfile
├── mysql/
│   └── Dockerfile
├── payment/
│   └── Dockerfile
├── shipping/
│   └── Dockerfile
├── user/
│   └── Dockerfile
├── docker-compose.yml
└── README.md
```

## Best Practices Followed

- Each service runs as a non-root user.
- Only necessary files are included in the final image.
- Layer ordering minimizes rebuild times and leverages Docker cache effectively.
- Multi-stage builds ensure security and small image sizes.
- Official and minimal images are selected as base images.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Contributing

Contributions are welcome. Please open issues or pull requests for improvements or suggestions.

## License

This project is licensed under the [MIT License](LICENSE).

---

> **Note:** For service-specific build or run instructions, refer to the respective microservice's directory.
