# Event Ticket API

This project is an Express-based REST API that provides authentication, session management. The API uses JWT tokens for authentication, Redis for session management, and Sequelize as the RDMS.

## Features

- User Authentication: Sign-up (Register) and sign-in (Login) functionality for users.
- Event Creation: Initializing an event.
- Event Booking: Booking an event.
- Canceling Events Booked.
- Event Status Check
- Testing: Comprehensive testing with `supertest` and `jest`.

## Technologies Used

- Node.js: JavaScript runtime
- Express.js: Web framework for building the API
- TypeScript: Statically typed JavaScript for scalability and reliability
- JWT (JSON Web Token): Token-based authentication
- Sequlize: RDMS database
- Redis: Session store
- Jest: Testing framework
- Supertest: HTTP assertions for testing API endpoints
- Faker.js: Generate fake data for testing

## Getting Started

### Prerequisites

- Node.js (v18 or higher)
- Docker (optional, for containerized development)
- Postgres
- Redis

### Installation

1. Clone the repository:

```bash
git clone https://github.com/OlaoluOfficial/event-ticket.git
```

2. Install dependencies:

```bash
npm install
```

3. Set up environment variables. Create a `.env` file in the root of your project and add the following:

```env
PORT=3000
DATABASE_NAME=event-ticket
DIALECT=postgres
DB_USERNAME=myuser
DB_PASSWORD=mypassword
DB_HOST=localhost
DB_PORT=5432
REDIS_URL=redis://localhost:6379
JWT_SECRET=secret

4. For testing purposes, create a `.env.test` file to store the environment variables used specifically for testing:

```env
PORT=3000
DATABASE_NAME=event-ticket
DIALECT=postgres
DB_USERNAME=myuser
DB_PASSWORD=mypassword
DB_HOST=localhost
DB_PORT=5432
REDIS_URL=redis://localhost:6379
JWT_SECRET=secret
```

### Running the Server

To start the server in development mode:

```bash
npm run dev
```

The server will start at `http://localhost:3210.

To start the server in production mode:

```bash
npm start
```

Ensure all environment variables are correctly set in your `.env` file for production.

### Running Tests

The project includes a suite of automated tests using `jest` and `supertest`. The tests will use the `test.env` file for environment variables.

To run the tests:

```bash
npm test
```

This command will:

- Execute the test suite using `jest` and `supertest`.
- Use the environment variables from `test.env` to run tests.

### Docker Setup

If you like to use Docker compose locally This project uses Docker for containerized development. A `docker-compose.yml` file is provided to help you get started quickly.

To start the containers:

```bash
npm run docker:build
npm run docker:bash
```
### API Endpoints

#### Auth Routes

- POST `/api/v1/auth/register` - Register a new user
- POST `/api/v1/auth/login` - Log in an existing user

#### Event Routes
- POST `/api/v1/events/initialize` - Create a new event
- POST `/api/v1/events/book` - Book a ticket
- POST `/api/v1/events/cancel` - Cancel an booking
- GET `/api/v1/events/status/:eventId` - Get event status


### Project Structure

The project follows a modular folder structure:

```
src/
│
├── controller/       # Handles API requests and responses
├── models/           # Mongoose models (e.g., User, Event, Order, WaitingList)
├── routes/           # Defines API routes
├── middleware/       # Authentication and other middlewares
├── services/         # Business logic and services
├── utils/            # Utility functions (e.g., JWT handling, api-response, etc)
├── config/           # Configuration files (e.g., Redis)
└── validations/      # Input validation schemas and logic
```
