# Airbnb Clone Project

This project is a simplified clone of Airbnb, built to understand and implement full-stack web development principles. The goal is to replicate core functionalities of Airbnb such as property listing, user authentication, booking system, and secure payments.

---

## 🚀 Project Goals

- Build a scalable and maintainable full-stack web application.
- Practice team collaboration and real-world software development workflows.
- Implement authentication, booking, and search features.
- Use secure and modern APIs.
- Follow agile methodology and CI/CD practices.

---

## 🧑‍🤝‍🧑 Team Roles

### Backend Developer
Responsible for developing the server-side logic, RESTful APIs, authentication, and managing interactions with the database.

### Frontend Developer
Handles the client-side logic and designs responsive interfaces for users to interact with the system.

### Database Administrator (DBA)
Designs and manages the database schema, ensures data integrity, and optimizes database performance.

### DevOps Engineer
Manages CI/CD pipelines, automates deployments, and ensures the system runs smoothly in development and production environments.

### Project Manager
Oversees the project lifecycle, coordinates between team members, manages deadlines, and ensures that project goals are met.

---

## 🛠️ Technology Stack

| Technology    | Purpose |
|---------------|---------|
| **Django**    | Backend web framework to build robust APIs and handle business logic. |
| **PostgreSQL**| Relational database for storing structured data such as users, properties, and bookings. |
| **GraphQL**   | Used optionally to allow clients to request specific data from the backend. |
| **React**     | Frontend library for building responsive user interfaces. |
| **Tailwind CSS** | Utility-first CSS framework for fast and consistent styling. |
| **Docker**    | Containerization tool for deploying the application consistently across environments. |
| **GitHub Actions** | Automates CI/CD pipelines for testing, building, and deploying the application. |

---

## 🧩 Database Design

### Entities and Fields:

#### Users
- `id`
- `name`
- `email`
- `password`
- `is_host`

#### Properties
- `id`
- `title`
- `location`
- `price`
- `host_id` (foreign key to Users)

#### Bookings
- `id`
- `user_id`
- `property_id`
- `check_in`
- `check_out`

#### Reviews
- `id`
- `user_id`
- `property_id`
- `rating`
- `comment`

#### Payments
- `id`
- `booking_id`
- `amount`
- `status`

### Relationships:
- A **user** can list multiple **properties**.
- A **user** can make multiple **bookings**.
- A **property** can have multiple **reviews**.
- A **booking** is linked to a **payment**.

---

## 🧰 Feature Breakdown

### User Management
Enables users to register, log in, and manage their profile. Hosts can list their properties and manage bookings.

### Property Management
Hosts can list, update, and delete their properties. Each property includes details such as title, description, images, price, and location.

### Booking System
Users can check availability and book properties for specific dates. Hosts receive booking notifications.

### Review System
Users can leave reviews for properties they’ve stayed in. Reviews include star ratings and comments.

### Search and Filter
Allows users to search for properties based on location, date range, price, and more.

### Payment Integration
Securely handles payment processing through a payment gateway (e.g., Stripe).

---

## 🔐 API Security

### Authentication
Only registered users can access protected endpoints. Token-based authentication (e.g., JWT) will be used.

### Authorization
Role-based access control ensures only hosts can list properties and only users who booked can leave reviews.

### Rate Limiting
Prevents abuse of APIs by limiting the number of requests per IP/user.

### Input Validation
All user inputs will be validated to prevent injection attacks and ensure data consistency.

### Importance
- **Protect user data** (emails, passwords).
- **Secure transactions** (payment data).
- **Prevent abuse** of the platform (bot activity, spamming).

---

## 🔄 CI/CD Pipeline

### What is CI/CD?
CI/CD (Continuous Integration and Continuous Deployment) automates the software development process — code is tested, integrated, and deployed automatically with every update.

### Tools Used
- **GitHub Actions**: For running automated tests and builds.
- **Docker**: For building consistent containers across dev, staging, and production.
- **Heroku / Render / AWS**: Deployment platforms for the live app.

### Why It’s Important
- Ensures faster, more reliable deployments.
- Reduces human error during deployment.
- Improves team productivity and confidence in code changes.

---

## 📦 Getting Started

```bash
# Clone the repository
git clone https://github.com/your-username/airbnb-clone-project.git

# Navigate into the directory
cd airbnb-clone-project

# Install backend dependencies
pip install -r requirements.txt

# Install frontend dependencies
cd client && npm install

# Start development servers
npm run dev  # For frontend
python manage.py runserver  # For backend
