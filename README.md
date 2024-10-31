# KeyShelf

**KeyShelf** is a web application designed to store and manage user data, including social links and static files. Users can access their information using a simple URL structure: `username/{key}`, where `{key}` represents values associated with user static files and social profiles.

## Table of Contents
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)

## Features
- User authentication (registration, login, password reset)
- User profile management
- Key management (create, update, delete keys)
- Redirection to social links and static files based on username and key
- File storage and management
- Admin panel for user management

## Tech Stack
- **Frontend:**
  - React
  - Tailwind CSS
  - React Router
- **Backend:**
  - Spring Boot
  - Spring Security (for authentication)
- **Database:**
  - MongoDB

## Installation

### Prerequisites
- Node.js (v14 or later)
- Java (JDK 11 or later)
- Maven (for building the Spring Boot application)
- MongoDB or MySQL (for database)

### Frontend Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/keyshelf-frontend.git
   cd keyshelf-frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm start
   ```

### Backend Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/keyshelf-backend.git
   cd keyshelf-backend
   ```

2. Build the project using Maven:
   ```bash
   mvn clean install
   ```

3. Run the Spring Boot application:
   ```bash
   mvn spring-boot:run
   ```

4. Configure your database settings in `application.properties` (located in `src/main/resources`):
   ```properties
   spring.data.mongodb.uri=mongodb://localhost:27017/keyshelf
   # OR for MySQL
   spring.datasource.url=jdbc:mysql://localhost:3306/keyshelf
   spring.datasource.username=yourusername
   spring.datasource.password=yourpassword
   ```

## Usage

1. **User Registration:** Users can create an account by visiting the registration page.
2. **User Login:** Registered users can log in to access their profile and manage their keys.
3. **Key Management:** Users can create, update, or delete keys linked to their profiles.
4. **Accessing Links:** Users can access their social profiles or static files using the URL structure `https://yourdomain.com/{username}/{key}`.

## API Endpoints

### User Authentication
- **POST** `/api/register` - Register a new user
- **POST** `/api/login` - Log in a user
- **POST** `/api/logout` - Log out a user
- **POST** `/api/password-reset` - Reset user password

### User Profile
- **GET** `/api/user/profile` - Get user profile information
- **PUT** `/api/user/profile` - Update user profile

### Key Management
- **POST** `/api/{username}/keys` - Create a new key
- **GET** `/api/{username}/keys` - List all keys for a user
- **PUT** `/api/{username}/keys/{key}` - Update an existing key
- **DELETE** `/api/{username}/keys/{key}` - Delete a key

### Redirection
- **GET** `/api/{username}/{key}` - Redirect to the corresponding link or serve static file

### File Management
- **POST** `/api/{username}/files` - Upload a file
- **GET** `/api/{username}/files` - List all files for a user
- **DELETE** `/api/{username}/files/{fileId}` - Delete a file

## Contributing
Contributions are welcome! Please read the [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to contribute to this project.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
