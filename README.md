<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

# User Management API

A simple Laravel REST API for user management.

---

## 🚀 Setup Project

1. **Clone repository**
   ```bash
   git clone <repo-url>
   cd be-usermanagement
   ```

2. **Install dependencies**
   ```bash
   composer install
   ```

3. **Copy & edit environment**
   ```bash
   cp .env.example .env
   # Edit .env for your DB settings
   ```

4. **Generate app key**
   ```bash
   php artisan key:generate
   ```

5. **Run migrations**
   ```bash
   php artisan migrate
   ```

6. **Run the server**
   ```bash
   php artisan serve
   ```
   API will be available at `http://localhost:8000/api`

---

## 📄 API Documentation

### User Management Endpoints

#### Get All Users

- **GET** `/api/users`
- **Response:** `200 OK`
- **Body:**  
  ```json
  [
    {
      "id": 1,
      "name": "John Doe",
      "email": "john@example.com",
      "phone": "081234567890",
      "is_active": true,
      "department": "IT",
      "created_at": "...",
      "updated_at": "..."
    }
  ]
  ```

#### Create User

- **POST** `/api/users`
- **Body:**
  ```json
  {
    "name": "John Doe",
    "email": "john@example.com",
    "phone": "081234567890",
    "is_active": true,
    "department": "IT",
    "password": "password123",
    "password_confirmation": "password123"
  }
  ```
- **Response:**  
  - `201 Created` (user created)
  - `422 Unprocessable Entity` (validation error)

#### Get User by ID

- **GET** `/api/users/{id}`
- **Response:**  
  - `200 OK` (user found)
  - `404 Not Found` (user not found)

#### Update User

- **PUT** `/api/users/{id}`
- **Body:** (any updatable field, password optional)
- **Response:**  
  - `200 OK` (user updated)
  - `422 Unprocessable Entity` (validation error)
  - `404 Not Found` (user not found)

#### Delete User

- **DELETE** `/api/users/{id}`
- **Response:**  
  - `200 OK` (user deleted)
  - `404 Not Found` (user not found)

---

## 📦 Tools

- Laravel 10+
- PHP 8+
- MySQL/PostgreSQL/SQLite

---

## 📚 Referensi

- [Laravel Docs](https://laravel.com/docs)
- [Swagger Editor](https://editor.swagger.io/)

---

## License

MIT
