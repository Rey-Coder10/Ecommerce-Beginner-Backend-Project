# 🛒 E-Commerce Web App — Spring Boot + React

A full-stack e-commerce application built with **Spring Boot** (REST API backend) and **React** (frontend), supporting complete product management (CRUD), image upload/retrieval, category filtering, keyword search, and a shopping cart with persistent storage.

---

## ✨ Features

- 📦 **Product Management** — Add, update, delete, and view products
- 🖼️ **Image Upload & Retrieval** — Product images stored and served as binary data via REST API
- 🔍 **Search** — Keyword search across product name, description, brand, and category
- 🗂️ **Category Filtering** — Browse products by category
- 🛍️ **Shopping Cart** — Add/remove items, quantity management, persisted using `localStorage`
- 🌗 **Theme Toggle** — Light/dark theme support (persisted in `localStorage`)
- ⚡ **Instant UI Updates** — React Context API used for global state management (cart & product data)

---

## 🛠️ Tech Stack

**Backend**
- Java 21
- Spring Boot 3.3.3
- Spring Data JPA (Hibernate)
- H2 In-Memory Database
- Lombok
- Maven
- Springdoc OpenAPI (Swagger UI)

**Frontend**
- React 18
- Vite
- React Router DOM
- Axios
- Bootstrap 5 + React Bootstrap
- React Icons

---

## 🏗️ Architecture

```
Client (React + Vite)  <---->  REST API (Spring Boot)  <---->  H2 Database
     Axios / Bootstrap           Controller → Service → Repo        (In-Memory)
```

The frontend communicates with the backend exclusively through REST endpoints under `/api`. Product images are stored as `byte[]` (BLOB) in the database and served through a dedicated image endpoint.

---

## 📁 Project Structure

```
SpringBoot-Reactjs-Ecommerce/
├── Ecommerce-Backend/
│   └── src/main/java/com/project/snippet/
│       ├── controller/     # REST controllers
│       ├── service/        # Business logic
│       ├── repo/           # Spring Data JPA repositories
│       └── model/          # Entity classes
│   └── src/main/resources/
│       ├── application.properties
│       └── data1.sql       # Sample seed data
│
└── Ecommerce-Frontend/
    └── src/
        ├── components/     # React components (Home, Cart, Product, Navbar, etc.)
        ├── Context/         # Global state via React Context API
        └── axios.jsx        # Axios instance/config
```

---

## 📡 API Endpoints

| Method | Endpoint                          | Description                         |
|--------|-----------------------------------|-------------------------------------|
| GET    | `/api/products`                   | Get all products                    |
| GET    | `/api/product/{id}`               | Get a single product by ID          |
| POST   | `/api/product`                    | Add a new product (with image)      |
| PUT    | `/api/product/{id}`               | Update an existing product          |
| DELETE | `/api/product/{id}`               | Delete a product                    |
| GET    | `/api/product/{productId}/image`  | Get product image                   |
| GET    | `/api/products/search?keyword=`   | Search products by keyword          |



## 🚀 Getting Started

### Prerequisites
- Java 21+
- Node.js 18+
- Maven

### Backend Setup
```bash
cd Ecommerce-Backend
./mvnw spring-boot:run
```
Backend runs at `http://localhost:8080`

### Frontend Setup
```bash
cd Ecommerce-Frontend
npm install
npm run dev
```
Frontend runs at `http://localhost:5173` (default Vite port)

> The app uses an in-memory H2 database, so sample data resets on every restart. Seed data is loaded from `data1.sql`.

## 📘 API Documentation (Swagger)

Interactive API documentation is available via Swagger UI, powered by `springdoc-openapi`.

Once the backend is running, access it at:
http://localhost:8080/swagger-ui.html

This provides a complete list of all REST endpoints, request/response schemas, and a built-in "Try it out" feature to test APIs directly from the browser.

---

## 📚 What This Project Demonstrates

- Building RESTful APIs with Spring Boot and Spring Data JPA
- Handling file uploads and binary data storage/retrieval
- Connecting a React frontend to a Spring Boot backend via Axios
- State management using React Context API
- CRUD operations across a full-stack application


