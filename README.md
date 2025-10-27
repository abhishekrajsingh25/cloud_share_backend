# ☁️ Cloud Share Application

A full-stack **Cloud Storage and File Sharing** web application built using **Spring Boot**, **React**, **Tailwind CSS**, and **MongoDB**.  
The app uses **Clerk** for authentication and **Razorpay** for purchasing credits.  
Users can upload files using credits, generate shareable download links, and send them securely to anyone.

---

## ✨ Features

### ✅ Core Functionalities

- Upload and store files in the cloud using credits  
- Generate and share secure download links  
- Manage uploaded files in a personal dashboard  
- Purchase upload credits through **Razorpay**  
- Fully responsive UI built with **Tailwind CSS**

### 🔐 Authentication & Security

- Authentication handled by **Clerk**  
- Secure backend validation via **Clerk Webhooks**  
- Token-based file access for shared links  
- File size limits and validation on upload

### 💳 Payment & Credit System

- **Razorpay** integrated for purchasing credits  
- Each upload deducts credits from user balance  
- Real-time credit tracking in the user dashboard

---

## 🛠 Tech Stack

### 💅️ Frontend

- **React.js**  
- **Vite** for fast builds  
- **Axios** for API communication  
- **Clerk** for authentication  
- **Tailwind CSS** for responsive styling  
- **React Router** for routing

### ⚙️ Backend

- **Spring Boot**  
- **MongoDB Atlas**  
- **Clerk SDK** for authentication validation  
- **Razorpay Java SDK** for payments  
- **Spring Web** and **Spring Data MongoDB**  
- **Multipart File Handling** for uploads

---

## ⚙️ Setup Instructions

### 🔧 Prerequisites

- Node.js & npm  
- Java 17+  
- Maven  
- MongoDB Atlas account  
- Clerk account (for authentication)  
- Razorpay account (for payments)

---

### 📦 Installation Steps

#### 1. Clone the Repository

```bash
git clone https://github.com/abhishekrajsingh25/Cloud-Share.git
cd Cloud-Share
```

---

#### 2. Backend Setup

```bash
git clone https://github.com/abhishekrajsingh25/cloud_share_backend.git
cd cloud_share_backend
```

Create or edit `src/main/resources/application.properties` with the following content:

```properties
# Application Info
spring.application.name=cloudshare

# MongoDB
spring.data.mongodb.uri=${MONGODB_URI}
spring.data.mongodb.auto-index-creation=true

# Server
server.servlet.context-path=/api

# Clerk Configuration
clerk.issuer=${CLERK_ISSUER_URL}
clerk.jwks-url=${CLERK_JWKS_URL}
clerk.webhook.secret=${CLERK_WEBHOOK_SECRET}

# Razorpay Configuration
razorpay.key.id=${RAZORPAY_KEY_ID}
razorpay.key.secret=${RAZORPAY_KEY_SECRET}

# File Upload Configuration
spring.servlet.multipart.max-file-size=5MB
spring.servlet.multipart.max-request-size=25MB

# Security
spring.autoconfigure.exclude=org.springframework.boot.autoconfigure.security.servlet.UserDetailsServiceAutoConfiguration
```

Run the backend server:

```bash
./mvnw spring-boot:run
```

---

#### 3. Frontend Setup

```bash
cd ../frontend
npm install
```

Create a `.env` file in the root of the frontend folder:

```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_BACKEND_URL=http://localhost:8080/api
VITE_RAZORPAY_KEY=your_razorpay_public_key
```

Start the frontend:

```bash
npm run dev
```

---

### 🔄 App URLs

* Frontend: [http://localhost:5173](http://localhost:5173)
* Backend: [http://localhost:8080](http://localhost:8080)

---


## 🤝 Contributing

We welcome contributions from developers of all experience levels.

Steps to contribute:

1. Fork the repository
2. Create a new branch (`feature/your-feature-name`)
3. Make your changes
4. Commit and push to your fork
5. Open a Pull Request

---

## 📸 Demo

> Backend Code: Click <a href="https://github.com/abhishekrajsingh25/cloud_share_backend" >Here</a>

---

Thank you for checking out the project! 🙌
Feel free to ⭐ the repo if you find it helpful.
