# Food Service Application

A comprehensive full-stack food delivery and restaurant management platform built with Spring Boot and React.

---

## 📋 Project Overview

The **Food Service Application** is a complete ecosystem for managing food delivery operations with support for multiple user roles:

- **Customers**: Browse restaurants, order food, track deliveries
- **Restaurants**: Manage menus, process orders, coordinate delivery
- **Admins**: System administration, user management, analytics
- **Delivery Personnel**: Manage assigned orders and deliveries

---

## 🏗️ Project Structure

```
Food-Service-Application/
├── Backend/                    # Spring Boot REST API
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/org/food/
│   │   │   │   ├── config/          # Configuration classes
│   │   │   │   ├── controller/      # REST Controllers
│   │   │   │   ├── service/         # Business Logic
│   │   │   │   ├── repository/      # Database Access Layer
│   │   │   │   ├── entity/          # JPA Entities
│   │   │   │   ├── dto/             # Data Transfer Objects
│   │   │   │   ├── exception/       # Exception Handling
│   │   │   │   ├── security/        # Security Configuration
│   │   │   │   └── enum/            # Enumerations
│   │   │   └── resources/
│   │   │       └── application.properties
│   │   └── test/                    # Unit Tests
│   ├── pom.xml                      # Maven Configuration
│   ├── mvnw/mvnw.cmd               # Maven Wrapper
│   └── Admin-Panel.postman_collection.json
│
└── Frontend/                   # React Vite Application
    └── food-app/
        ├── src/
        │   ├── pages/               # Page Components
        │   ├── components/          # Reusable Components
        │   ├── AdminPages/          # Admin Dashboard
        │   ├── layouts/             # Layout Components
        │   ├── routes/              # Route Definitions
        │   ├── context/             # React Context (State Management)
        │   ├── api/                 # API Integration
        │   ├── assets/              # Static Assets
        │   ├── App.jsx
        │   ├── main.jsx
        │   └── index.css
        ├── public/                  # Public Assets
        ├── package.json             # NPM Dependencies
        ├── vite.config.js           # Vite Configuration
        └── eslint.config.js         # ESLint Configuration
```

---

## 🔧 Technology Stack

### Backend

| Component             | Technology            | Version                             |
| --------------------- | --------------------- | ----------------------------------- |
| **Language**          | Java                  | 17                                  |
| **Framework**         | Spring Boot           | 4.0.5                               |
| **Build Tool**        | Maven                 | 3.x                                 |
| **Security**          | Spring Security + JWT | 0.12.5                              |
| **Database ORM**      | Hibernate/JPA         | -                                   |
| **Validation**        | Spring Validation     | -                                   |
| **API Documentation** | Postman Collection    | Admin-Panel.postman_collection.json |

### Frontend

| Component            | Technology                | Version      |
| -------------------- | ------------------------- | ------------ |
| **Library**          | React                     | 19.2.4       |
| **Build Tool**       | Vite                      | Latest       |
| **Styling**          | Tailwind CSS              | 4.2.2        |
| **Routing**          | React Router              | 7.13.2       |
| **HTTP Client**      | Axios                     | 1.14.0       |
| **Icons**            | Lucide React, React Icons | 1.7.0, 5.6.0 |
| **State Management** | Context API               | -            |
| **Notifications**    | React Hot Toast           | 2.6.0        |
| **Linting**          | ESLint                    | 9.39.4       |

---

## 🚀 Getting Started

### Prerequisites

- **Java 17+** (for Backend)
- **Node.js 18+** (for Frontend)
- **Maven 3.x** (for Backend)
- **npm or yarn** (for Frontend)
- **Database** (MySQL, PostgreSQL, or as configured)

### Backend Setup

1. **Navigate to Backend directory**

   ```bash
   cd Backend
   ```

2. **Install dependencies**

   ```bash
   mvn install
   ```

3. **Configure application**
   - Edit `src/main/resources/application.properties`
   - Set database URL, username, password
   - Configure JWT secret key
   - Set server port (default: 8080)

4. **Run the application**

   ```bash
   mvn spring-boot:run
   ```

   Or compile and run:

   ```bash
   mvn clean install
   java -jar target/food-0.0.1-SNAPSHOT.jar
   ```

5. **Backend will be available at**: `http://localhost:8080`

### Frontend Setup

1. **Navigate to Frontend directory**

   ```bash
   cd Frontend/food-app
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Create environment configuration** (if needed)
   - Create `.env` file with API base URL
   - Example: `VITE_API_BASE_URL=http://localhost:8080`

4. **Run development server**

   ```bash
   npm run dev
   ```

   Frontend will be available at: `http://localhost:5173` (or displayed in terminal)

5. **Build for production**

   ```bash
   npm run build
   ```

6. **Preview production build**
   ```bash
   npm run preview
   ```

---

## 📡 API Documentation

### Postman Collection

- **File**: `Backend/Admin-Panel.postman_collection.json`
- **Usage**: Import this file into Postman to test all API endpoints
- **Features**: Pre-configured requests for Admin, Restaurant, Customer, and Delivery endpoints

### API Base URL

- **Development**: `http://localhost:8080`
- **Endpoints**: RESTful API with JWT authentication

### Authentication

- Login endpoint returns JWT token
- Include token in `Authorization: Bearer <token>` header for protected routes

---

## 🧪 Testing

### Backend Unit Tests

**Run all tests**:

```bash
cd Backend
mvn test
```

**Run specific test class**:

```bash
mvn test -Dtest=TestClassName
```

**Run with code coverage**:

```bash
mvn test jacoco:report
```

**Skip tests during build**:

```bash
mvn clean install -DskipTests
```

---

## 👥 User Roles & Features

### 🛍️ Customer

- Browse available restaurants
- View restaurant menus
- Add items to cart
- Place orders
- Make payments
- Track order status
- View order history
- Leave reviews and feedback

### 🍽️ Restaurant

- Manage restaurant profile
- Create and update menus
- View incoming orders
- Update order status
- Manage delivery personnel
- Track earnings
- View analytics

### 👨‍💼 Admin

- Manage users (customers, restaurants, delivery)
- View all orders and analytics
- Manage coupons and discounts
- Review system feedback
- Handle restaurant requests
- System statistics and reports

### 🚚 Delivery Personnel

- View assigned deliveries
- Update delivery status
- Navigate to delivery locations
- Track earnings
- Manage delivery history

---

## 🔐 Security Features

- **JWT Authentication**: Secure token-based authentication
- **Spring Security**: Role-based access control
- **Password Validation**: Secure password handling
- **CORS Configuration**: Cross-origin resource sharing
- **Encrypted Communication**: HTTPS ready
- **Input Validation**: Server-side validation of all inputs

---

## 📁 Key Components

### Backend Modules

#### Controller Layer

RESTful endpoints for all user roles and operations.

#### Service Layer

Business logic for:

- User authentication and authorization
- Order processing
- Payment handling
- Restaurant management
- Delivery coordination

#### Repository Layer

Database operations using Spring Data JPA.

#### Security Layer

- JWT token generation and validation
- Role-based access control
- Authentication filters

### Frontend Components

#### Pages

- `Login.jsx` - User authentication
- `Signup.jsx` - User registration
- `Home.jsx` - Landing page
- `DashBoard.jsx` - Dashboard
- `Cart.jsx` - Shopping cart
- `Payment.jsx` - Payment processing

#### Customer Pages

- `RestaurantsPage.jsx` - Browse restaurants
- `RestaurantMenuPage.jsx` - View menu
- `CustomerCartPage.jsx` - Cart management
- `CheckoutPage.jsx` - Order checkout
- `CustomerOrdersPage.jsx` - Order history

#### Admin Pages

- `AdminDashboard.jsx` - Overview
- `UserManagement.jsx` - Manage users
- `OrderHistory.jsx` - View orders
- `CouponsAndOrders.jsx` - Manage coupons
- `ReviewsAndFeedBack.jsx` - Customer feedback
- `RestaurantRequest.jsx` - Restaurant applications

#### Layouts

- `CustomerLayout.jsx` - Customer interface
- `RestaurantLayout.jsx` - Restaurant interface
- `AdminLayout.jsx` - Admin interface

---

## 🛠️ Development Commands

### Backend

```bash
# Install dependencies
mvn install

# Run application
mvn spring-boot:run

# Clean build
mvn clean install

# Run tests
mvn test

# Generate JAR
mvn package

# Skip tests
mvn clean install -DskipTests
```

### Frontend

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview

# Run ESLint
npm run lint
```

---

## 📝 Environment Configuration

### Backend (`application.properties`)

```properties
# Server
server.port=8080

# Database
spring.datasource.url=jdbc:mysql://localhost:3306/food_db
spring.datasource.username=root
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update

# JWT
jwt.secret.key=your_secret_key
jwt.expiration=86400000

# Server servlet path
server.servlet.context-path=/api
```

### Frontend (`.env`)

```
VITE_API_BASE_URL=http://localhost:8080
```

---

## 🐛 Troubleshooting

### Backend Issues

- **Port 8080 in use**: Change port in `application.properties`
- **Database connection failed**: Verify database credentials and URL
- **Maven build failures**: Run `mvn clean install` to rebuild
- **JWT errors**: Check JWT secret key configuration

### Frontend Issues

- **Port 5173 in use**: Vite will use next available port
- **API connection errors**: Verify backend is running and API URL is correct
- **Dependencies not installing**: Delete `node_modules` and run `npm install` again
- **Build errors**: Clear cache with `npm cache clean --force`

---

## 📚 Additional Resources

- [Spring Boot Documentation](https://spring.io/projects/spring-boot)
- [React Documentation](https://react.dev)
- [Tailwind CSS Documentation](https://tailwindcss.com)
- [React Router Documentation](https://reactrouter.com)

---

## 📞 Support

For issues or questions:

1. Check existing documentation in Backend/README.md and Frontend/food-app/README.md
2. Review Postman collection for API examples
3. Check browser console for frontend errors
4. Review application logs for backend errors

---

## 📄 License

This project is provided as-is for educational and commercial purposes.

---

**Last Updated**: April 2026  
**Version**: 0.0.1  
**Status**: Active Development
