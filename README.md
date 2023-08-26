
# BQ Ecommerce Store

developed an immersive online marketplace built on MongoDB, Express.js, React, and Node.js.

This project is designed to create a functional e-commerce platform where users can browse products, add them to their cart, and make purchases. Below, you'll find detailed information about the backend controllers and their associated routes and models that drive the functionality of the project.

## ACKNOWLEDGEMENT

I would like to express my sincere gratitude to my teacher, **Sir Usama**, for his invaluable guidance, support, and expertise throughout the development of this project. His insights and feedback have been instrumental in shaping this application.

I also extend my thanks to **Bano Qabil Institute** for providing the platform and resources that have enabled me to learn and create this project.

## Table of Contents
- Auth Controller (auth-Routes)
- Category Controller (category-Routes)
- Product Controller (product-Routes)
- Models (Category Model) (order Model) (product Model) (user Model)


#### Auth Controller
The auth controller manages user registration, login, password reset, profile updates, and order-related functionalities.

- `registerController`: Registers a new user with provided details.
- `loginController`: Handles user authentication and generates authentication tokens.
- `forgotPasswordController`: Manages the process of resetting the user's password.
- `testController`: A protected route for testing user authentication.
- `updateProfileController`: Allows users to update their profile information.
- `getOrdersController`: Fetches orders placed by a specific user.
- `getAllOrdersController`: Fetches all orders in the system.
- `orderStatusController`: Updates the status of an order.

 #### Routes
 - `POST /register`: Registers a new user with provided details.
- `POST /login`: Handles user authentication and generates authentication tokens.
- `POST /forgot-password`: Manages the process of resetting the user's password.
- `GET /test`: A protected route for testing user authentication (requires admin access).
- `GET /user-auth`: A protected user route for testing user authentication.
- `GET /admin-auth`: A protected admin route for testing admin authentication.
- `PUT /profile`: Allows users to update their profile information.
- `GET /orders`: Fetches orders placed by a specific user.
- `GET /all-orders`: Fetches all orders in the system (requires admin access).
- `PUT /order-status/:orderId`: Updates the status of an order (requires admin access).

#### Category Controller
The category controller manages product categories.
- `createCategoryController`: Creates a new product category.
- `updateCategoryController`: Updates an existing product category.
- `categoryControlller`: Fetches all categories in the system.
- `singleCategoryController`: Fetches a single category by its slug.
- `deleteCategoryCOntroller`: Deletes a category.

#### Routes

- `POST /create-category`: Creates a new product category (requires admin access).
- `PUT /update-category/:id`: Updates an existing product category (requires admin access).
- `GET /get-category`: Fetches all categories in the system.
- `GET /single-category/:slug`: Fetches details of a single category by its slug.
- `DELETE /delete-category/:id`: Deletes a category (requires admin access).

#### Product Controller
The product controller handles product-related functionalities.
- `createProductController`: Creates a new product with details.
- `getProductController`: Fetches a list of products with basic information.
- `getSingleProductController`: Fetches details of a single product.
- `productPhotoController`: Fetches and serves the photo of a product.
- `deleteProductController`: Deletes a product.
- `updateProductController`: Updates an existing product.
- `productFiltersController`: Applies filters to product listing.
- `productCountController`: Fetches the total count of products.
- `productListController`: Fetches products based on pagination.
- `realtedProductController`: Fetches related products based on a category.
- `productCategoryController`: Fetches products by a specific category.
- `braintreeTokenController`: Generates a client token for Braintree payment.
- `brainTreePaymentController`: Handles payment processing using Braintree.

#### Routes

- `POST /create-product`: Creates a new product with details (requires admin access).
- `PUT /update-product/:pid`: Updates an existing product (requires admin access).
- `GET /get-product`: Fetches a list of products with basic information.
- `GET /get-product/:slug`: Fetches details of a single product.
- `GET /product-photo/:pid`: Fetches and serves the photo of a product.
- `DELETE /product/:pid`: Deletes a product (requires admin access).
- `POST /product-filters`: Applies filters to product listing.
- `GET /product-count`: Fetches the total count of products.
- `GET /product-list/:page`: Fetches products based on pagination.
- `GET /related-product/:pid/:cid`: Fetches related products based on a category.
- `GET /product-category/:slug`: Fetches products by a specific category.
- `GET /braintree/token`: Generates a client token for Braintree payment.
- `POST /braintree/payment`: Handles payment processing using Braintree (requires user authentication).

# Project Models

This README provides an overview of the data models used in the E-Commerce project. These models represent the structure of data stored in the MongoDB database.

#### Category Model

The `Category` model represents product categories.

##### Fields

- `name`: The name of the category. (Required, Unique)
- `slug`: A lowercase version of the category name.

#### Order Model

The `Order` model represents orders placed by users.

#### Fields

- `products`: An array of references to the `Products` model, representing the ordered products.
- `payment`: Details related to the payment.
- `buyer`: Reference to the `users` model, representing the user who placed the order.
- `status`: The order status. Possible values: "Not Process", "Processing", "Shipped", "delivered", "cancel".

#### Product Model

The `Products` model represents individual products available for purchase.

#### Fields

- `name`: The name of the product. (Required)
- `slug`: A unique identifier for the product. (Required)
- `description`: The description of the product. (Required)
- `price`: The price of the product. (Required)
- `category`: Reference to the `Category` model, representing the category of the product. (Required)
- `quantity`: The available quantity of the product. (Required)
- `photo`: The product photo, stored as data and content type.
- `shipping`: A boolean indicating if the product is available for shipping.

#### User Model

The `users` model represents registered users of the platform.

#### Fields

- `name`: The name of the user. (Required)
- `email`: The email address of the user. (Required, Unique)
- `password`: The password of the user. (Required)
- `phone`: The phone number of the user. (Required)
- `address`: The address of the user. (Required)
- `answer`: An answer provided by the user for security purposes. (Required)
- `role`: The user role, where 0 indicates a regular user. (Default: 0)


# BQ E-Commerce store Frontend README
frontend repository of our E-Commerce project! This README will provide an overview of the code structure and usage instructions for the different pages and components in the frontend.

## Table of Contents
- Project Overview
- Getting Started
  - Prerequisites
  - Installation
- Usage
  - Home Page
  - Product Category Page
  - Category Product Page
  - Registration Page
  - Login Page
  - forgot password
  - Cart page
- Admin Panel
  - Components
  - Features
- User Panel
  - Components
  - Features
- Technologies Used
- Contributing

## Project Overview
Our E-Commerce project aims to create an online shopping platform where users can browse products, view product categories, and add items to their cart. The frontend is built using React and interacts with the backend API to fetch and display data.

## Getting Started
### Prerequisites
- Node.js
- npm (Node Package Manager)

### Installation
1. Clone this repository to your local machine.
2. Navigate to the project directory in your terminal.
3. Run the following command to install project dependencies:
   ```bash
   npm install
   ```
4. Start the development server:
   ```bash
   npm start
   ```
5. Open your web browser and navigate to `http://localhost:3000` to view the application.
## Usage
### Home Page
The home page displays a list of products available for purchase. Users can view product details and add products to their cart.

### Product Category Page
The product category page lists different product categories. Users can click on a category to view products related to that category.

### Category Product Page
This page displays products within a specific category. Users can view product details and add products to their cart.

### User Registration Page
The user registration page allows new users to sign up for an account. Users can provide their name, email, password, phone number, address, and answer to a security question. Upon successful registration, users are redirected to the login page.

### User Login Page
The user login page enables registered users to log into their accounts. Users must provide their email and password to authenticate. After successful login, users are redirected to their intended destination or the homepage.

### Forgot Password 
The forgot password page lets users reset their passwords. Users enter their registered email, answer a security question, and provide a new password. This process helps users regain access to their accounts in case they forget their password.

### Cart Page
The cart page displays the items that users have added to their cart. Users can view product details, remove items, and proceed to checkout. If the user is logged in, they can also make a payment using the Braintree payment gateway. The page calculates and displays the total price of the items in the cart.

# Admin Panel
This is an admin panel application for managing categories and products. The application is built using React.js for the frontend and interacts with a backend API for data management.

### Features
- Create, update, and delete categories.
- Create, update, and delete products.
- View and manage user information.

### Components
- `AdminMenu`: A navigation menu for the admin panel.
- `AdminDashboard`: Displays the admin's information.
- `CreateCategory`: Allows creating, updating, and deleting categories.
- `CreateProduct`: Allows creating products.
- `UpdateProduct`: Allows updating and deleting products.

# User Panel

The Ecommerce User Panel is a React.js web application that allows users to manage their profiles, view orders, and update personal information related to their online shopping activities.

## Components

#### UserMenu Component

The `UserMenu` component provides users with a navigation menu that allows easy access to different sections of the user dashboard.

#### Dashboard Component

The `Dashboard` component displays user information, including name, email, and address, within a card layout.

#### Orders Component

The `Orders` component fetches and presents a list of user orders. It provides details such as order status, buyer's name, order date, payment status, and product quantities.

#### Profile Component

The `Profile` component enables users to view and update their profile information, including name, email, password, phone number, and address.

## Features

- Seamless navigation using the `UserMenu` component.
- Clear visualization of user information through the `Dashboard` component.
- Insightful overview of user orders with the `Orders` component.
- Profile management and updates facilitated by the `Profile` component.



## Technologies Used
- React: JavaScript library for building user interfaces.
- React Router: Library for routing and navigation within the application.
- Axios: HTTP client for making API requests.
- react-hot-toast: Library for displaying toast notifications.

## Contributing
We welcome contributions to enhance our E-Commerce project. Feel free to fork the repository, make your improvements, and submit pull requests.



