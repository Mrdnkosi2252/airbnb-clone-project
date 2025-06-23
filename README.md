# Airbnb Clone Project

## Overview
The Airbnb Clone Project is a full-stack web application simulating a booking platform like Airbnb. It aims to develop a scalable backend using Django, PostgreSQL, and GraphQL, with secure APIs and automated CI/CD pipelines. The project enhances skills in collaborative development, database design, and industry-standard practices.

## Project Goals
- Build a robust backend with Django and GraphQL for efficient API communication.
- Design a relational PostgreSQL database for users, properties, and bookings.
- Implement secure APIs with authentication, authorization, and rate limiting.
- Automate testing and deployment using CI/CD pipelines with GitHub Actions.
- Foster collaboration via GitHub workflows and team roles.

## Team Roles
The project involves key roles to ensure successful development, aligned with industry standards:

- **Backend Developer**: Implements server-side logic, RESTful APIs, and GraphQL queries using Django.
- **Database Administrator**: Designs and optimizes PostgreSQL schemas for data integrity and performance.
- **DevOps Engineer**: Configures CI/CD pipelines with GitHub Actions and Docker for automated testing and deployment.
- **Security Specialist**: Ensures API security through JWT authentication, role-based authorization, and rate limiting.
- **Project Manager**: Coordinates tasks, tracks progress, and aligns deliverables with project goals.

## Technology Stack
The project leverages modern technologies to build a scalable platform:

- **Django**: Python framework for developing RESTful APIs and server-side logic.
- **PostgreSQL**: Relational database for storing users, properties, bookings, reviews, and payments.
- **GraphQL**: Query language for efficient, flexible API data retrieval.
- **Docker**: Containerization tool for consistent development and deployment environments.
- **GitHub Actions**: CI/CD tool for automating testing, linting, and deployment workflows.

Each technology enhances the project’s scalability, performance, and maintainability.

## Database Design
The database supports core functionalities with the following entities, fields, and relationships:

- **Users**:
  - `user_id`: Primary key, unique identifier.
  - `email`: Unique email for login.
  - `password`: Hashed password for security.
  - `name`: Full name of the user.
  - `phone`: Contact number for notifications.
- **Properties**:
  - `property_id`: Primary key, unique identifier.
  - `title`: Property name (e.g., “Cozy Apartment”).
  - `owner_id`: Foreign key to Users (property owner).
  - `location`: Address or coordinates.
  - `price_per_night`: Nightly rate in ZAR.
- **Bookings**:
  - `booking_id`: Primary key, unique identifier.
  - `user_id`: Foreign key to Users (guest).
  - `property_id`: Foreign key to Properties.
  - `check_in`: Check-in date.
  - `check_out`: Check-out date.
- **Reviews**:
  - `review_id`: Primary key, unique identifier.
  - `user_id`: Foreign key to Users (reviewer).
  - `property_id`: Foreign key to Properties.
  - `rating`: Score (1–5).
  - `comment`: Text feedback.
- **Payments**:
  - `payment_id`: Primary key, unique identifier.
  - `booking_id`: Foreign key to Bookings.
  - `amount`: Payment amount in ZAR.
  - `status`: Status (e.g., pending, completed).
  - `date`: Transaction date.

### Relationships
- A User can own multiple Properties and make multiple Bookings.
- A Property belongs to one User (owner) and has multiple Bookings and Reviews.
- A Booking belongs to one User (guest) and one Property.
- A Review belongs to one User (reviewer) and one Property.
- A Payment is linked to one Booking.

The design ensures data integrity and supports efficient queries for booking operations.

## Feature Breakdown
The project includes core features to replicate Airbnb’s functionality:

- **User Management**: Enables user registration, login, and profile updates with secure authentication. Supports personalized interactions for guests and hosts.
- **Property Management**: Allows hosts to list and manage properties; provides search filters for guests. Drives the platform’s core listing functionality.
- **Booking System**: Facilitates booking requests, availability checks, and cancellations. Ensures seamless guest-host transactions.
- **Review System**: Permits guests to rate and comment on properties post-stay. Enhances trust and informs booking decisions.
- **Payment System**: Processes secure payments for bookings via multiple methods. Ensures reliable financial transactions.

## API Security
The project prioritizes API security to protect user data and transactions:

- **Authentication**: Uses JSON Web Tokens (JWT) to verify user identity, preventing unauthorized access to endpoints like `/api/bookings`.
- **Authorization**: Implements role-based access (e.g., guest, host, admin) to restrict actions, such as hosts editing only their properties.
- **Rate Limiting**: Caps API requests per user to prevent abuse and ensure server stability during high traffic.
- **Data Encryption**: Employs HTTPS and TLS to secure data in transit, safeguarding sensitive information like payment details.

These measures ensure data integrity, user privacy, and compliance with security
