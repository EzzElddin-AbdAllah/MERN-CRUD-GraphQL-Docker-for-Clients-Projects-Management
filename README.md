# GraphQL Project

This project is built using GraphQL to provide a flexible and efficient API for managing clients and projects. It consists of a client-side application and a server-side backend, all orchestrated using Docker Compose.

## GraphQL Schema

This project utilizes GraphQL, a powerful query language for APIs, to define the schema for interacting with the server-side data. GraphQL enables clients to request only the data they need, allowing for more efficient and flexible API interactions.

### Types

- **ProjectType**: Represents a project entity, including its ID, name, description, status, and associated client.
- **ClientType**: Represents a client entity, including its ID, name, email, and phone number.

### Queries

- **projects**: Retrieves a list of all projects.
- **project**: Retrieves a specific project by its ID.
- **clients**: Retrieves a list of all clients.
- **client**: Retrieves a specific client by its ID.

### Mutations

- **addClient**: Adds a new client to the database.
- **deleteClient**: Deletes a client from the database by its ID. Also deletes any associated projects.
- **addProject**: Adds a new project to the database, associating it with a client.
- **deleteProject**: Deletes a project from the database by its ID.
- **updateProject**: Updates the details of a project in the database.

### Example GraphQL Query

```
query {
  projects {
    id
    name
    description
    status
    client {
      id
      name
    }
  }
}
```

## Directory Structure

- `client/`: Contains the frontend application files.

  - `public/`: Static assets and HTML template.
  - `src/`: React components, queries, mutations, and pages.
  - `package.json`, `package-lock.json`: Frontend dependencies and configuration.
  - `Dockerfile`: Docker configuration for building the client image.

- `server/`: Contains the backend application files.

  - `models/`: MongoDB models for Client and Project entities.
  - `schema/`: GraphQL schema definition.
  - `config/`: Database configuration and environment variables.
  - `index.js`: Entry point for the server application.
  - `package.json`, `package-lock.json`: Backend dependencies and configuration.
  - `Dockerfile`: Docker configuration for building the server image.

- `docker-compose.yml`: Docker Compose configuration for orchestrating the client, server, and MongoDB containers.

- `README.md`: This file.

## Running the Project

1. Ensure you have Docker installed on your machine.

2. Clone this repository to your local machine.

3. Navigate to the project directory in your terminal.

4. Run `docker-compose up -d --build` to build and start the Docker containers for the client, server, and MongoDB.

5. Once the containers are up and running, you can access the frontend application at `http://localhost:3000`.

6. Explore the GraphQL API at `http://localhost:5000/graphql`.

7. To stop the containers, press `Ctrl+C` in the terminal, then run `docker-compose down`.
