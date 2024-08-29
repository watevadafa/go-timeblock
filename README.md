# Go TimeBlock - A Time Management API / CLI

TimeBlock is a robust time blocking application designed to help users manage their time effectively. Built with Go and modern web technologies, it offers a scalable and efficient solution for personal and professional time management.

## Features

- User registration and authentication
- User Profile (basic demographic information, time zone...)
- User Preferences (duration of a timeblock, day start/end times)
- Create, read, update, and delete time blocks, filter view by given date
- Support for users in different time zones
- JWT-based authentication
- Redis caching for improved performance


## Technical Stack

| Description | Stack |
| --- | --- |
| Backend | [Golang](https://go.dev) |
| Database | [PostgreSQL](https://www.postgresql.org) |
| Web Framework | [Gin](https://pkg.go.dev/github.com/gin-gonic/gin) |
| Database Driver | [pgx](https://pkg.go.dev/github.com/jackc/pgx/v5) | 
| Authentication | [JWT](https://pkg.go.dev/github.com/golang-jwt/jwt/v5) |
| Caching | [Redis](https://pkg.go.dev/github.com/go-redis/redis/v8) |
| CORS handler | [CORS](https://pkg.go.dev/github.com/rs/cors) |
| Logging | [Zap](https://pkg.go.dev/go.uber.org/zap) |

## Project Structure

```
go-timeblock/
├── cmd/
│   └── server/
│       └── main.go
├── internal/
│   ├── api/
│   │   ├── handlers/
│   │   │   ├── auth.go
│   │   │   ├── timeblock.go
│   │   │   └── user.go
│   │   ├── middlewares/
│   │   │   └── auth.go
│   │   └── routes.go
│   ├── config/
│   │   └── config.go
│   ├── models/
│   │   ├── timeblock.go
│   │   └── user.go
│   ├── repository/
│   │   ├── postgres/
│   │   │   ├── timeblock.go
│   │   │   └── user.go
│   │   └── redis/
│   │       └── cache.go
│   └── service/
│       ├── auth.go
│       ├── timeblock.go
│       └── user.go
├── migrations/
│   └── ... (database migration files)
├── pkg/
│   ├── logger/
│   │   └── logger.go
│   └── utils/
│       └── time.go
├── scripts/
│   └── ... (build and deployment scripts)
├── .env
├── .gitignore
├── go.mod
├── go.sum
└── README.md

```

## Getting Started

1. Clone the repository
2. Copy `.env.example` to `.env` and fill in the required environment variables
3. Run database migrations:
   ```
   ./scripts/run_migrations.sh
   ```
4. Build and run the application:
   ```
   go build -o timeblock ./cmd/api ./timeblock
   ```

## API Endpoints

| Method | Endpoint | Description |
| ------ | -------- | ----------- |
| POST | /api/v1/auth/register | Register a new user |
| POST | /api/v1/auth/login | Login and receive JWT token |
| GET | /api/v1/auth/refresh | Refresh JWT token |
| GET | /api/v1/timeblocks | Get all time blocks for the authenticated user |
| POST | /api/v1/timeblocks | Create a new time block |
| GET | /api/v1/timeblocks/:id | Get a specific time block |
| PUT | /api/v1/timeblocks/:id | Update a specific time block |
| PATCH | /api/v1/timeblocks/:id | Update a specific time block (partial update) |
| DELETE | /api/v1/timeblocks/:id | Delete a specific time block |
| GET | /api/v1/timeblocks/:date | Get time blocks for a specific day |


## Development

To contribute to this project:

1. Fork the repository
2. Create a new branch for your feature
3. Implement your changes
4. Write or update tests as necessary
5. Submit a pull request


## Future Enhancements

- Recurring time blocks.
- Collaboration features (shared calendars, team time blocking)
- Analytics and reporting features
- Task dependencies and Gantt chart views
- AI-powered scheduling suggestions
- Pomodoro timer integration
- Custom categories and color-coding for time blocks
- Export/import functionality for time blocks
- Goal setting and progress tracking
- Customizable notification system
- Integration with popular calendar services (Google Calendar, Outlook)
- Integration with other productivity tools, such as project management software, communication tools, and more.


## License

[MIT License](/LICENSE.md)

## Contact

For any queries or support, please open an issue in the GitHub repository.
