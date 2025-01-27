## TODO API

This CRUD project uses [warp](https://docs.rs/warp/latest/warp/) web framework and [tokio](https://docs.rs/tokio/latest/tokio/) for building asynchronous applications.

### Purpose

Learn and understand how Rust works. This project doesn't support a SQL database server, it persists the data in memory.
It was based on an article I found on the internet

### Depdencies

- Rust 1.85.0 (nightly version)
- chrono 0.4.39
- pretty_env_logger 0.5.0
- serde 1.0.216
- tokio 1.42.0
- uuid 1.11.0
- warp 0.3.7
- Docker

### Running with docker

Currently the service is setup to run over port 3000

```
$docker-compose up
```

### API

List of routes

#### Health checker

```
curl --location --request GET 'localhost:3000/api/ping'
```

#### GET - TODOs list

```
curl --location --request GET 'localhost:3000/api/todos'
```

#### POST - Create TODO

```
curl --location 'localhost:3000/api/todos' \
--header 'Content-Type: application/json' \
--data '{
    "title": "Testing RUST",
    "content": "I really don'\''t know"
}'
```

#### PATCH - Editing TODO

```
curl --location --globoff --request PATCH 'localhost:3000/api/todos/{todo_id}' \
--header 'Content-Type: application/json' \
--data '{
    "title": "Testing RUST 123",
    "content": "I really don'\''t know"
}'
```
