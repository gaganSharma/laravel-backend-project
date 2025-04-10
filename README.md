# Laravel Backend Project

A RESTful API backend built with Laravel 12.x, providing a solid foundation for web applications and mobile apps. This project includes user authentication, data management, and API endpoints with proper documentation.

## Table of Contents

- [Project Overview](#project-overview)
- [Installation](#installation)
- [Environment Setup](#environment-setup)
- [Database Configuration](#database-configuration)
- [API Documentation](#api-documentation)
- [Testing](#testing)

## Project Overview

This Laravel backend provides a robust API for client applications. Key features include:

- User authentication and authorization
- RESTful API architecture
- SQLite database integration
- Comprehensive API documentation
- Test suite for reliable development

## Installation

### Prerequisites

- PHP 8.4 or higher
- Composer
- SQLite PDO extension enabled

### Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/gaganSharma/laravel-backend-project.git
   cd laravel-backend-project
   ```

2. Install dependencies:
   ```bash
   composer install
   ```

3. Create environment file:
   ```bash
   cp .env.example .env
   php artisan key:generate
   ```

4. Start the development server:
   ```bash
   php artisan serve
   ```

   The API will be available at `http://127.0.0.1:8000`

## Environment Setup

The `.env` file contains important configuration for your application. Key settings include:

```
APP_NAME=Laravel
APP_ENV=local
APP_KEY=base64:your-generated-key
APP_DEBUG=true
APP_URL=http://localhost

DB_CONNECTION=sqlite
# DB_DATABASE=absolute/path/to/database.sqlite

CACHE_DRIVER=file
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
```

## Database Configuration

This project uses SQLite for database storage. To set up the database:

1. Ensure the SQLite PDO extension is enabled in PHP
2. The database file is located at `database/database.sqlite`
3. Run migrations to create tables:
   ```bash
   php artisan migrate
   ```

To seed the database with test data:
```bash
php artisan db:seed
```

## API Documentation

### Authentication

| Method | Endpoint           | Description                    | Parameters                       |
|--------|-------------------|--------------------------------|----------------------------------|
| POST   | `/api/register`   | Register a new user            | name, email, password            |
| POST   | `/api/login`      | User login                     | email, password                  |
| POST   | `/api/logout`     | User logout (requires token)   | -                                |

### User Management

| Method | Endpoint           | Description                    | Parameters                       |
|--------|-------------------|--------------------------------|----------------------------------|
| GET    | `/api/user`       | Get authenticated user details | -                                |
| PUT    | `/api/user`       | Update user information        | name, email, etc.                |

### Other Resources

Additional endpoints will be added as the API develops. The standard RESTful convention is followed:

- GET `/api/resource` - List all resources
- POST `/api/resource` - Create a new resource
- GET `/api/resource/{id}` - Get a specific resource
- PUT `/api/resource/{id}` - Update a specific resource
- DELETE `/api/resource/{id}` - Delete a specific resource

## Testing

Run the test suite with:
```bash
php artisan test
```

## License

This project is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
