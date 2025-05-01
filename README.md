# 🍱 Meal Box Server

Meal Box Server is a Node.js-based backend for a meal customization and ordering platform. It enables users to register, choose dietary preferences, customize meals, and place orders. Admins can manage meals, monitor orders, and view user activity.

## 🔐 Environment Variables

Rename `.env.example` to `.env` and add your environment variables.

```env
PORT=5555
DATABASE_URL=mongodb+srv://<username>:<password>@cluster0.mongodb.net/meal-box-db
BCRYPT_SALT_ROUNDS=10
NODE_ENV=development
RESET_PASS_UI_LINK=https://your-app.com/reset-password
CLOUD_NAME=your_cloud_name
API_KEY=your_api_key
API_SECRET=your_api_secret
SUPER_ADMIN_PASSWORD=super_admin_pass
JWT_ACCESS_SECRET_TIME=1d
JWT_ACCESS_SECRET=your_jwt_access_secret
JWT_REFRESH_SECRET=your_jwt_refresh_secret
```

## 📦 Tech Stack

Backend: Node.js, Express.js

Database: MongoDB (via Mongoose)

Authentication: JWT (access & refresh tokens), Bcrypt

Cloud Storage: Cloudinary

Validation: Zod

Error Handling: Centralized middleware

## 📌 API Endpoints

### Authentication

```
POST /api/v1/auth/login – Log in user and receive JWT token in HTTP-only cookie

POST /api/v1/auth/register – Register a new user
```

### Users

```
GET /api/v1/users/get-my-data – Get logged-in user’s profile (requires JWT)

PATCH /api/v1/users/update-profile – Update user profile (requires JWT)
```

### Meals

```

GET /api/v1/meals/ – Get all meals

GET /api/v1/meals/:id – Get single meal by ID

GET /api/v1/meals/my-preferences-meals – Get meals based on user preferences (requires JWT)

POST /api/v1/meals/create-meal – Create a new meal (admin only, requires JWT)

PATCH /api/v1/meals/update-meal/:id – Update meal (admin only, requires JWT)

DELETE /api/v1/meals/:id – Delete meal (admin only, requires JWT)
```

### Meal Preferences

```
GET /api/v1/meal-preferences/ – Get all meal preferences (requires JWT)

GET /api/v1/meal-preferences/:id – Get single meal preference (requires JWT)

POST /api/v1/meal-preferences/create-meal-preference – Create a meal preference (user only, requires JWT)

PATCH /api/v1/meal-preferences/update-meal-preference/:id – Update a meal preference (user only, requires JWT)

DELETE /api/v1/meal-preferences/:id – Delete meal preference (user only, requires JWT)
```

### Dietary Preferences

```
GET /api/v1/preferences/ – Get all dietary preferences (admin only, requires JWT)

GET /api/v1/preferences/my-dietary-preferences – Get logged-in user’s dietary preferences (requires JWT)

POST /api/v1/preferences/create-dietary-preference – Create dietary preference (user only, requires JWT)

PATCH /api/v1/preferences/update-dietary-preference – Update dietary preference (user only, requires JWT)

```

### Orders

```

POST /api/v1/orders/create-order – Place a new meal order (user only, requires JWT)

PUT /api/v1/orders/update-order-status – Update order status (admin only, requires JWT)

GET /api/v1/orders/verify – Verify meal order (user only, requires JWT)

GET /api/v1/orders/ – Get all orders (admin only, requires JWT)

GET /api/v1/orders/my-orders – Get logged-in user’s orders (requires JWT)

DELETE /api/v1/orders/:orderId – Cancel an order (user only, requires JWT)
```

## 🧱 Middlewares

auth: Role-based authentication

validateRequest: Zod schema validation

globalErrorHandler: Handles all thrown errors

notFound: Catches undefined routes

## 🚀 Getting Started

```
## Clone the repository

git clone https://github.com/your-username/meal-box-server.git

## Install dependencies

npm install

## Set up environment variables

## Run the server

npm run dev
```

## 🛠️ Scripts

```
npm run dev       # Start development server
npm run build     # Compile TypeScript
npm run start     # Run compiled JS

```

## Team Leader:

Name : MD Sojib Hossain

Email : sojibhossain.cse@gmail.com

## Team Members:

Name: Md Sajedul Islam

name: Md Asif Shahariar
