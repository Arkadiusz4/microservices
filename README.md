# Mircroservices
 
## Introduction
This project is a GoLang-based microservices architecture designed to handle various microservices such as:

- Broker Service
- Mail Service
- Authentication Service
- Listener Service
- Logger Service
The project utilizes technologies like PostgreSQL, MongoDB, MailHog, and RabbitMQ.

## Installation

### Prerequisites
- GoLang installed on your machine. If Go is not already installed on your system, you can download and install it from the [official Go website](https://go.dev/dl/).
- Docker and Kubernetes for containerization and orchestration.

### Steps
1. Clone the repository:
```vim
git clone https://github.com/Arkadiusz4/microservices.git
```

2. Navigate to the project directory and install dependencies:
```go
go mod tidy
```

3. Build the project:
```vim
make up_build
```

## Usage

### Docker
To build and run the application using Docker, execute the following commands:
```vim
make up_build
```

### Kubernetes
For Kubernetes deployment, make sure you have kubectl configured to your cluster. Then, use the provided Kubernetes manifests to deploy the application:
```vim
kubectl apply -f kubernetes/
```

## Makefile
The Makefile provides various helpful commands for managing the project:

- `make up`: Starts all containers in the background without forcing build
- `make up_build`: Stops docker-compose (if running), builds all projects and starts docker compose
- `make down`: Stop docker compose.
- `make build_broker`: Builds the broker binary as a linux executable
- `make build_auth`: Builds the auth binary as a linux executable
- `make build_logger`: Builds the logger binary as a linux executable
- `make build_mailer`: Builds the mailer binary as a linux executable
- `make build_listener`:  Builds the listener binary as a linux executable
- `make build_front`: Builds the front end binary
- `make build_front_linux`: Builds the front end linux binary
- `make stop`: Stop the front end

## Additional Components
The project relies on the following components:
- **PostgreSQL**: Ensure you have a PostgreSQL server running and update the database configuration in `docker-compose.yml` or `swarm.yml`.
- **MongoDB**: Similarly, ensure MongoDB is installed and configured. Update MongoDB connection details in `docker-compose.yml` or `swarm.yml`.
- **MailHog**: MailHog is used for email testing. You can either install it locally or use a hosted version. Update email configuration in `docker-compose.yml` or `swarm.yml` accordingly.
- **RabbitMQ**: RabbitMQ is used for messaging. Install and configure RabbitMQ, and update connection details in `docker-compose.yml` or `swarm.yml`.
