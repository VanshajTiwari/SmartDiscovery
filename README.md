# SmartDiscovery

**An AI-powered discovery and recommendation platform built with Android, Java, Spring Boot, and MongoDB.**

## 1. Overview

SmartDiscovery is an independent discovery and recommendation application that analyzes synthetic or explicitly authorized demo profiles and recommends relevant profiles based on user-defined preferences, interests, and configurable similarity scores.

The platform consists of:

- An Android application for user interaction.
- A Spring Boot backend for business logic and REST APIs.
- MongoDB for persistent data storage.
- An AI integration layer supporting multiple AI providers.
- A configurable recommendation engine for ranking and explaining recommendations.

The project is designed with a modular architecture so that individual components can be developed, tested, and maintained independently.

## 2. Key Features

- User registration and preference management.
- Demo profile creation and management.
- AI-powered profile analysis.
- Interest and preference similarity analysis.
- Configurable recommendation scoring.
- Ranked recommendations with explanations.
- Discovery session management.
- Dynamic discovery radius expansion.
- Multiple AI provider support.
- Analytics and usage tracking.
- Local Android data caching.
- Simulated interactions for testing.

## 3. Technology Stack

| Component | Technology |
|---|---|
| Android | Java, XML |
| Architecture | MVVM |
| UI | Material Components |
| Backend | Java, Spring Boot |
| API | REST, JSON |
| Database | MongoDB Atlas |
| Local Storage | Room Database |
| Networking | Retrofit, OkHttp |
| Authentication | Spring Security, JWT |
| AI Integration | Pluggable AI providers |
| API Documentation | Springdoc OpenAPI |
| Monitoring | Spring Boot Actuator |
| Backend Testing | JUnit 5, Mockito |
| Android Testing | JUnit, Espresso |
| Build Tools | Gradle, Maven |
| Version Control | Git, GitHub |

## 4. Architecture

```text
             ANDROID APPLICATION
                     |
              UI / XML Screens
                     |
                  ViewModel
                     |
                 Repository
                     |
               Retrofit / API
                     |
                     v
              SPRING BOOT BACKEND
                     |
          -------------------------
          |           |           |
       Services   AI Engine   Security
          |           |           |
          |       AI Providers    |
          |                      |
          -----------|------------
                     |
                     v
                  MongoDB
```

**Architecture principles:**

- Maintain separation of concerns.
- Keep business logic out of controllers and Android UI components.
- Use interfaces for external AI providers.
- Keep recommendation logic independent of AI providers.
- Use DTOs for API communication.
- Validate incoming requests.
- Write unit and integration tests.
- Never expose secrets or API keys in the Android application.

## 5. Repository Structure

```text
SmartDiscovery/
│
├── android-app/
│   └── Android application
│
├── backend/
│   └── Spring Boot application
│
├── docs/
│   ├── architecture/
│   ├── modules/
│   ├── database/
│   └── api-contracts/
│
├── sample-data/
│   └── Synthetic demo data
│
├── deployment/
│   └── Deployment configurations
│
├── DEVELOPMENT_RULES.md
├── PROJECT_STATUS.md
└── README.md
```

## 6. Prerequisites

Install the following before starting development:

- Java JDK (version specified in the backend build configuration).
- Android Studio.
- Android SDK.
- Git.
- Maven.
- MongoDB Atlas account or a compatible local MongoDB instance.
- Visual Studio Code or another preferred IDE.

## 7. Getting Started

### Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/smart-discovery.git

cd smart-discovery
```

### Backend Setup

Navigate to the backend directory:

```bash
cd backend
```

Configure the required environment variables:

```properties
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
AI_PROVIDER_API_KEY=your_ai_provider_key
```

Keep actual credentials in environment variables or a secret manager. Never commit them to GitHub.

Build the backend:

```bash
mvn clean install
```

Run the application:

```bash
mvn spring-boot:run
```

### Android Setup