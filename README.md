# Backend API LUZ of Armando Marelius Garcia Paulsen

# Node.js API Server

This is a simple Node.js API server built with Express that provides endpoints for managing users and retrieving electricity prices from an external API.

## Features
- User management: Register and retrieve users from a database.
- Price data management: Fetch electricity prices from an external API and store them in a database.
- SQLite database for data storage.

## Installation
### Prerequisites
Make sure you have the following installed:
- [Node.js](https://nodejs.org/)
- [SQLite3](https://www.sqlite.org/download.html)

### Steps
1. Clone this repository:
   ```sh
   git clone https://github.com/armandomarelius/LightPricesAPI-NodeJS-PROJECT.git
   cd LightPricesAPI-NodeJS-PROJECT
   ```

2. Install dependencies:
   ```sh
   npm install
   ```

3. Create a `.env` file in the root directory and add the following variables:
   ```env
   PORT=3000
   DATABASE_PATH=./database/luzdb.sqlite
   URL_API=https://apidatos.ree.es/es/datos/mercados/precios-mercados-tiempo-real?start_date=2024-01-01T00:00&end_date=2024-01-31T23:59&time_trunc=hour
   ```

4. Start the server:
   ```sh
   npm start
   ```
   The server will run at `http://localhost:3000`.

## Project Structure
```
📂 project-directory
│-- 📂 config            # Configuration files
│-- 📂 controllers       # Business logic
│-- 📂 database          # Database files
│-- 📂 models           # Database queries
│-- 📂 routes            # API route definitions            
│-- 📜 .env              # Environment variables
│-- 📜 app.js         # Main server file
│-- 📜 package.json      # Dependencies and scripts
```

## API Endpoints
### User Routes
| Method | Endpoint           | Description        |
|--------|-------------------|--------------------|
| GET    | `/api/users`      | Get all users     |
| POST   | `/api/users/register` | Register a new user |

### Price Routes
| Method | Endpoint             | Description |
|--------|---------------------|-------------|
| GET    | `/api/prices`       | Get all price data from the database |
| GET    | `/api/prices/initialize` | Fetch and store new price data from the API |

## Database
- The project uses SQLite for database storage.
- The database file is located at `./database/luzdb.sqlite`.

## Notes
- Ensure that the API URL in `.env` is correct.
- The `/initialize` route will delete and reinsert data from the API into the database.

## License
This project is licensed under the MIT License.


