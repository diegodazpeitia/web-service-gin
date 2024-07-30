# Album Web Service

This is a simple web service built using Go and the Gin framework. It provides an API for managing a collection of music albums. The service allows you to retrieve, add, and query album information.

> **Note:** This project is intended as a basic example for understanding REST APIs in Go. It covers fundamental concepts and provides a foundation for building more complex services.

## Features

- **GET /albums**: Retrieve a list of all albums.
- **GET /albums/:id**: Retrieve a specific album by its ID.
- **POST /albums**: Add a new album to the collection.

## API Endpoints

### Get All Albums

- **URL**: `/albums`
- **Method**: `GET`
- **Response**: 
  - **Status Code**: `200 OK`
  - **Body**: JSON array of all albums

### Get Album By ID

- **URL**: `/albums/:id`
- **Method**: `GET`
- **URL Parameters**: 
  - `id` (string): The ID of the album to retrieve.
- **Response**: 
  - **Status Code**: `200 OK` (if album is found)
  - **Body**: JSON object of the requested album
  - **Status Code**: `404 Not Found` (if album is not found)
  - **Body**: JSON object with a message indicating that the album was not found

### Add a New Album

- **URL**: `/albums`
- **Method**: `POST`
- **Request Body**: JSON object representing the album to be added
  ```json
  {
    "id": "string",
    "title": "string",
    "artist": "string",
    "price": number
  }
  ```
- **Response**: 
  - **Status Code**: `201 Created`
  - **Body**: JSON object of the newly created album

## Example Usage

### Get All Albums

```bash
curl -X GET http://localhost:8080/albums
```

### Get Album By ID

```bash
curl -X GET http://localhost:8080/albums/1
```

### Add a New Album

```bash
curl -X POST http://localhost:8080/albums \
  -H "Content-Type: application/json" \
  -d '{
    "id": "4",
    "title": "Giant Steps",
    "artist": "John Coltrane",
    "price": 45.99
  }'
```

## Setup and Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/diegodazpeitia/web-service-gin.git
   ```

2. **Navigate to the project directory:**

   ```bash
   cd web-service-gin
   ```

3. **Install dependencies:**

   Ensure you have Go installed and then run:

   ```bash
   go mod tidy
   ```

4. **Run the application:**

   ```bash
   go run main.go
   ```

   The service will start and listen on `localhost:8080`.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Feel free to open issues or submit pull requests to improve the project.
