# Mutual Fund Portfolio

A Spring Boot-based mutual fund portfolio web application for managing user accounts, mutual fund schemes, investments, redemptions, and email notifications.

## Features
- User registration and login
- Explore mutual fund schemes
- Invest and redeem funds
- Admin-side management views
- Email notifications for transactions

## Tech Stack
- Java 17
- Spring Boot 3.1
- Maven
- Spring Security
- Thymeleaf
- MySQL
- Docker Compose (optional)

## Prerequisites
- JDK 17 or later
- Maven 3.9+
- MySQL 8+ or Docker Desktop
- Git

## Project Setup
1. Clone the repository:
   ```bash
   git clone <your-repository-url>
   cd mutual-fund-portfolio
   ```
2. Start MySQL (optional if you use Docker):
   ```bash
   docker compose up -d
   ```
3. Configure Spring properties:
   - Copy the sample configuration as your local file:
     ```bash
     cp src/main/resources/application-sample.properties src/main/resources/application.properties
     ```
   - Edit the file at `src/main/resources/application.properties` with your credentials:
     - Update email (Gmail SMTP username and app password)
     - Update database URL, username, and password as needed
     - This file is ignored by Git so secrets are never pushed
4. Run the application:
   - Windows:
     ```bash
     mvnw.cmd spring-boot:run
     ```
   - Linux/macOS:
     ```bash
     ./mvnw spring-boot:run
     ```
5. Open the app in your browser:
   ```text
   http://localhost:5000
   ```

## GitHub Commit Steps
```bash
git status
git add .
git commit -m "Initial project setup"
git branch -M main
git remote add origin <your-github-repo-url>
git push -u origin main
```

## Project Structure
```
mutual-fund-portfolio/
├── src/main/
│   ├── java/com/valtech/poc/        # Application source code
│   ├── resources/
│   │   ├── application-sample.properties   # Sample configuration template (tracked)
│   │   ├── application.properties          # Local configuration (ignored by Git)
│   │   ├── logback-spring.xml              # Logging configuration
│   │   ├── static/                         # CSS, JS, images
│   │   └── templates/                      # Thymeleaf HTML templates
│   └── test/java/                         # Test classes
├── pom.xml                           # Maven build configuration
├── dockerfile                        # Docker image definition
├── docker-compose.yaml               # Multi-container orchestration
└── README.md                         # This file
```

## Database Setup

### Option 1: Using Docker (Recommended)
The project includes `docker-compose.yaml` that automatically sets up MySQL:
```bash
docker compose up -d
# MySQL will be available at: localhost:3306
```

### Option 2: Manual MySQL Installation
If you prefer a local MySQL installation:
1. Install MySQL 8+ from [mysql.com](https://www.mysql.com/)
2. Start the MySQL server
3. Create the database:
   ```sql
   CREATE DATABASE mutualfundpoc;
   ```
4. Update `application.properties` with your connection details:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/mutualfundpoc
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   ```

## Running Tests
```bash
# Run all tests
mvn test

# Run specific test class
mvn test -Dtest=YourTestClass

# Run tests with coverage
mvn test jacoco:report
```

## Troubleshooting

### Port already in use
If port 5000 is already in use, update `application.properties`:
```properties
server.port=8080  # Or any available port
```

### Database connection failed
- Verify MySQL is running: `mysql -u root -p`
- Check connection string in `application.properties`
- Ensure database `mutualfundpoc` exists

### Email sending fails
- Enable "Less secure app access" if using Gmail (deprecated)
- Use Gmail App Password instead: [Generate here](https://myaccount.google.com/apppasswords)
- Verify SMTP credentials in `application.properties`

### Thymeleaf template errors
- Ensure all template files are in `src/main/resources/templates/`
- Check for typos in template names in controller mappings

## Contributing
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/YourFeature`
3. Commit changes: `git commit -m "Add YourFeature"`
4. Push to branch: `git push origin feature/YourFeature`
5. Open a Pull Request

## Support
For issues or questions, please open an issue on GitHub or contact the development team.