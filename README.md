# Assignment 1 – Docker Multi-Container Application

This project demonstrates a simple multi-container Docker application built using Docker Compose.  
It consists of a PostgreSQL database container and a Python application container that interact to query data, compute basic statistics, and produce structured output.

## Project Overview

The application performs the following tasks:

- Launches a PostgreSQL database with a pre-seeded `trips` table
- Runs a Python application that connects to the database
- Executes queries on trip data
- Computes basic statistics from the results
- Outputs a JSON summary to the terminal
- Saves the same summary to a file for later use

## Tech Stack

- Docker & Docker Compose
- PostgreSQL
- Python

## How to Run the Application

Ensure Docker Desktop is running on your system.  
From the root directory of the project, run:

```bash
docker compose up --build
```

To stop the application and remove containers and volumes:

```bash
docker compose down -v
```

## Output

The application generates output in two locations:

- A JSON summary printed to the terminal
- A JSON file saved at `out/summary.json`

### Sample Output

```json
{
  "total_trips": 6,
  "avg_fare_by_city": [
    { "city": "Charlotte", "avg_fare": 16.25 },
    { "city": "New York", "avg_fare": 19.0 },
    { "city": "San Francisco", "avg_fare": 20.25 }
  ],
  "top_by_minutes": [
    { "city": "San Francisco", "minutes": 28, "fare": 29.3 },
    { "city": "New York", "minutes": 26, "fare": 27.1 }
  ]
}
```

## Troubleshooting

- If the application fails to connect to the database, wait a few seconds and try again
- Make sure Docker Desktop is running before starting the containers
- Ensure port 5432 is not already in use on your system
