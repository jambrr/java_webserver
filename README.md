# Java Webserver

# MovieLibraryServer

A minimal Java REST API built using the built-in `HttpServer` class from `com.sun.net.httpserver`. It serves a basic movie library that supports adding and listing movies via HTTP.

## Features

* `GET /movies`: Returns a list of all movie titles.
* `POST /movies`: Adds a new movie to the library via raw JSON.

## Requirements

* Java 11+
* Gradle (for building and running)

## Project Structure

```
java_rest_api/
├── build.gradle
├── settings.gradle
└── src/main/java/java_rest_api/MovieLibraryServer.java
```

## Running the Server

1. Clone or download the repo.
2. Run using Gradle:

```bash
./gradlew run
```

Server will start on `http://localhost:8000`.

## Example Usage

### Add Movie (POST)

**Endpoint:** `/movies`
**Method:** POST
**Body (raw JSON):**

```json
{
  "id": "101",
  "title": "Inception",
  "director": "Christopher Nolan"
}
```

### Get All Movies (GET)

**Endpoint:** `/movies`
**Method:** GET

Response:

```
Inception
```

## Notes

* This is a simplified example meant for educational/demo purposes.
* No database or persistent storage — movies are stored in memory during runtime.
* The JSON parsing is done manually and not robust. For real-world apps, use libraries like [Gson](https://github.com/google/gson) or [Jackson](https://github.com/FasterXML/jackson).


## Example Usage

### Add Movie (POST)

**Endpoint:** `/movies`
**Method:** POST
**Content-Type:** `application/json`

```bash
curl -X POST http://localhost:8000/movies \
  -H "Content-Type: application/json" \
  -d '{"id": "101", "title": "Inception", "director": "Christopher Nolan"}'
```

**Response:**

```
Movie added
```

---

### Get All Movies (GET)

**Endpoint:** `/movies`
**Method:** GET

```bash
curl http://localhost:8000/movies
```

**Example Response:**

```
Inception
```

---