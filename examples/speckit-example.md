# SpecKit Examples

This document demonstrates how to use SpecKit for creating specifications and documentation.

## Directory Structure

```
specs/
├── api/          # API specifications (OpenAPI/Swagger)
├── features/     # Feature specifications (Gherkin)
└── architecture/ # Architecture documentation
```

## API Specification Example

Create a file `specs/api/users.yaml`:

```yaml
openapi: 3.0.0
info:
  title: User Management API
  version: 1.0.0
  description: API for managing users

paths:
  /users:
    get:
      summary: List all users
      responses:
        '200':
          description: Successful response
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: '#/components/schemas/User'
    
    post:
      summary: Create a new user
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/UserInput'
      responses:
        '201':
          description: User created
        '400':
          description: Invalid input

components:
  schemas:
    User:
      type: object
      properties:
        id:
          type: string
        email:
          type: string
        name:
          type: string
    
    UserInput:
      type: object
      required:
        - email
        - name
      properties:
        email:
          type: string
        name:
          type: string
```

## Feature Specification Example

Create a file `specs/features/user-registration.feature`:

```gherkin
Feature: User Registration
  As a new user
  I want to register for an account
  So that I can access the application

  Scenario: Successful registration
    Given I am on the registration page
    When I fill in "Email" with "user@example.com"
    And I fill in "Password" with "SecurePass123!"
    And I fill in "Name" with "John Doe"
    And I click "Register"
    Then I should see "Registration successful"
    And I should receive a confirmation email

  Scenario: Registration with existing email
    Given a user exists with email "existing@example.com"
    When I try to register with email "existing@example.com"
    Then I should see "Email already registered"
    And I should not be registered

  Scenario: Registration with invalid email
    Given I am on the registration page
    When I fill in "Email" with "invalid-email"
    And I click "Register"
    Then I should see "Please enter a valid email address"
```

## Architecture Documentation Example

Create a file `specs/architecture/system-overview.md`:

```markdown
# System Architecture

## Overview

This document describes the high-level architecture of the application.

## Components

### Frontend
- React-based single-page application
- Redux for state management
- Material-UI for components

### Backend
- Node.js with Express
- RESTful API architecture
- JWT-based authentication

### Database
- PostgreSQL for relational data
- Redis for caching and sessions

### Infrastructure
- Docker containers
- Kubernetes orchestration
- AWS cloud hosting

## Data Flow

1. User interacts with React frontend
2. Frontend makes API calls to Express backend
3. Backend authenticates requests via JWT
4. Backend queries PostgreSQL database
5. Results cached in Redis for performance
6. Response returned to frontend

## Security

- HTTPS for all communications
- JWT tokens with expiration
- Password hashing with bcrypt
- SQL injection prevention
- XSS protection
- CSRF tokens

## Scalability

- Horizontal scaling of backend services
- Database read replicas
- CDN for static assets
- Load balancing
```

## SpecKit Configuration

The `.speckit.json` file controls how specifications are processed:

```json
{
  "speckit": {
    "templates": {
      "api": {
        "path": "./specs/api",
        "format": "openapi"
      }
    },
    "documentation": {
      "output": "./docs"
    }
  }
}
```

## Benefits of SpecKit

1. **Standardized Specs**: Consistent format across projects
2. **Auto-generation**: Generate docs from specs
3. **Validation**: Ensure specs are correct
4. **Integration**: Works with CI/CD pipelines
5. **Collaboration**: Share specs with team members

## Workflow

1. Write specifications first (spec-driven development)
2. Generate documentation automatically
3. Validate specs in CI/CD
4. Use specs to guide implementation
5. Keep specs in sync with code

## Best Practices

- Write specs before code
- Keep specs up to date
- Review specs in pull requests
- Use specs for API contracts
- Generate client SDKs from specs
- Validate API responses against specs

## Learn More

- [SpecKit Documentation](https://speckit.dev/docs)
- [OpenAPI Specification](https://swagger.io/specification/)
- [Gherkin Reference](https://cucumber.io/docs/gherkin/reference/)
