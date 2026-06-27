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
3. Update the local Spring configuration file:
   - Edit the file at `src/main/resources/application.properties`
   - Set your own database and email credentials locally
   - This file is intentionally ignored by Git so secrets are not pushed
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

## Notes
- Build output, logs, IDE files, and local configuration are ignored to keep the repository clean and safe for GitHub.
- If you want to share a sample configuration, create a file such as `application-example.properties` and keep it committed.