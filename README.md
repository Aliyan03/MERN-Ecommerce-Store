
# BQ Ecommerce Store

developed an immersive online marketplace built on MongoDB, Express.js, React, and Node.js.

This project is designed to create a functional e-commerce platform where users can browse products, add them to their cart, and make purchases. Below, you'll find detailed information about the backend controllers and their associated routes and models that drive the functionality of the project.


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


