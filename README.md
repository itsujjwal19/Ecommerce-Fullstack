# Ecommerce Full-Stack Application

A full-stack e-commerce web application built using **React** for the frontend, **Spring Boot** for the backend, and **PostgreSQL** for database management.

The application provides product browsing, product management, image uploads, order placement, stock management, and order processing through REST APIs.

## 🚀 Features

- View all available products
- View individual product details
- Add new products
- Upload product images
- Product information management
- Place customer orders
- Manage order items
- Automatically calculate item prices
- Update product stock after an order
- View all placed orders
- RESTful API architecture
- PostgreSQL database integration
- React frontend connected with Spring Boot backend

## 🛠️ Tech Stack

### Frontend

- React
- JavaScript
- HTML
- CSS
- Axios
- Vite

### Backend

- Java
- Spring Boot
- Spring Data JPA
- Hibernate
- REST APIs
- Maven

### Database

- PostgreSQL

## 📁 Project Structure

```text
Ecommerce_FullStack/
│
├── Backend/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/telusko/SpringEcom/
│   │   │   │       ├── controller/
│   │   │   │       ├── model/
│   │   │   │       ├── repo/
│   │   │   │       └── service/
│   │   │   └── resources/
│   │   └── test/
│   ├── pom.xml
│   └── mvnw
│
├── Frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   ├── package-lock.json
│   └── vite.config.js
│
├── .gitignore
└── README.md

🔗 REST API Endpoints
📦 Product APIs
Get All Products
GET /api/products

Returns a list of all products.
Get Product by ID
GET /api/product/{id}

Returns the details of a specific product.
Add Product
POST /api/product

Adds a new product using multipart form data containing product information and an image.
🛒 Order APIs
Place Order
POST /api/orders/place

Creates a new order, calculates item prices, and updates product stock.
Get All Orders
GET /api/orders

Returns all placed orders with their order items.
🗄️ Database
This project uses PostgreSQL.
Create a database named:
telusko

The backend uses the following environment variables for database configuration:
DB_URL
DB_USERNAME
DB_PASSWORD

Example:
DB_URL=jdbc:postgresql://localhost:5432/telusko
DB_USERNAME=postgres
DB_PASSWORD=your_password

⚠️ Never commit your actual database password, API keys, or other sensitive credentials to GitHub.

⚙️ Backend Configuration
The backend uses environment variables instead of storing database credentials directly in the source code.
Example application.properties:
spring.application.name=SpringEcom

spring.datasource.url=${DB_URL}
spring.datasource.username=${DB_USERNAME}
spring.datasource.password=${DB_PASSWORD}

spring.jpa.hibernate.ddl-auto=update
spring.datasource.hikari.auto-commit=false

▶️ How to Run the Project
1. Clone the Repository
git clone https://github.com/itsujwal19/Ecommerce-Fullstack.git

Navigate into the project:
cd Ecommerce-Fullstack

2. Configure PostgreSQL
Make sure PostgreSQL is installed and running.
Create the database:
CREATE DATABASE telusko;

Set the required environment variables:
DB_URL=jdbc:postgresql://localhost:5432/telusko
DB_USERNAME=postgres
DB_PASSWORD=your_password

3. Run the Backend
Open a terminal inside the Backend directory:
cd Backend

Run the Spring Boot application:
Windows
mvnw.cmd spring-boot:run

The backend will start on:
http://localhost:8080

4. Run the Frontend
Open another terminal:
cd Frontend

Install the required dependencies:
npm install

Start the Vite development server:
npm run dev

Open the URL provided by Vite in your browser.
🔄 Application Architecture
The application follows a layered architecture.
                React Frontend
                      │
                      │ Axios
                      ▼
             Spring Boot Controller
                      │
                      ▼
                Service Layer
                      │
                      ▼
              Repository Layer
                      │
                      ▼
                  PostgreSQL

Product Flow
React
  ↓
ProductController
  ↓
ProductService
  ↓
ProductRepo
  ↓
PostgreSQL

Order Flow
React
  ↓
OrderController
  ↓
OrderService
  ↓
ProductRepo
  ↓
Update Product Stock
  ↓
OrderRepo
  ↓
PostgreSQL
  ↓
OrderResponse
  ↓
React

📦 Order Processing
When a customer places an order:
1. The frontend sends the order details to the backend.
2. OrderController receives the request.
3. OrderRequest transfers the incoming order data.
4. OrderService processes the order.
5. The requested products are retrieved from PostgreSQL.
6. Product stock is reduced according to the ordered quantity.
7. The total price for each order item is calculated.
8. An Order and its OrderItem records are created.
9. The order is saved in the database.
10. An OrderResponse is returned to the frontend.
🧩 Backend Layers
Controller
Handles HTTP requests and responses.
Examples:
ProductController
OrderController

Service
Contains the application's business logic.
Examples:
ProductService
OrderService

Repository
Handles communication with the database through Spring Data JPA.
Examples:
ProductRepo
OrderRepo

Model
Represents the application's database entities.
Examples:
Product
Order
OrderItem

DTO
Data Transfer Objects are used to transfer data between the frontend and backend.
Examples:
OrderRequest
OrderResponse
OrderItemRequest
OrderItemResponse

🧪 API Testing
The REST APIs can be tested using Postman.
Example:
GET http://localhost:8080/api/products

For placing an order:
POST http://localhost:8080/api/orders/place

🔮 Future Improvements
- 🔐 User authentication and authorization
- 👤 User registration and login
- 🛒 Shopping cart functionality
- 💳 Payment gateway integration
- 🔎 Product search
- 🏷️ Product category filtering
- ⭐ Product reviews and ratings
- 📄 Pagination
- 👨‍💼 Admin dashboard
- 📦 Order status tracking
- 📧 Email notifications
- ☁️ Cloud deployment
- 🐳 Docker support
- 🔒 Improved validation and error handling
👨‍💻 Author
Ujjwal Agarwal
GitHub:
https://github.com/itsujwal19
⭐ If you find this project useful
Feel free to explore the repository and use the project as a reference for learning full-stack development with React and Spring Boot.