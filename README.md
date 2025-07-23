## Zenith Product API
A robust and scalable RESTful API for managing product inventory at Zenith, a growing e-commerce company. Built using Node.js, Express, and MongoDB (via Mongoose), this API supports full CRUD functionality along with advanced filtering, sorting, and pagination.

## Features
Create, read, update, and delete products

Advanced querying with:

Category filter

Price range (minPrice, maxPrice)

Sorting by price or date

Pagination support

MongoDB Atlas integration

Simple, modular structure for scalability

## Technologies Used
Node.js

Express

MongoDB Atlas

Mongoose

dotenv

nodemon (dev only)

## Project Structure
zenith-product-api/
│
├── config/
│   └── connection.js       # MongoDB connection logic
│
├── models/
│   └── Product.js          # Mongoose schema for products
│
├── routes/
│   └── productRoutes.js    # All API routes
│
├── .env                    # Environment variables
├── .gitignore
├── server.js               # Main server entry point
├── package.json

## Setup Instructions

### 1.Clone the repository

git clone https://github.com/your-username/zenith-product-api.git
cd zenith-product-api

### 2.Install dependencies

npm install

### 3.Configure environment variables

Create a .env file in the root:
PORT=5000
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/zenith?retryWrites=true&w=majority
Replace <username> and <password> with your MongoDB Atlas credentials.

### 4.Run the server

For production:
npm start
For development with live reload:
npm run dev

## API Endpoints
Base URL
http://localhost:5000/api/products

Create a Product
POST /api/products

Body
{
  "name": "UltraBoost Sneakers",
  "description": "High performance running shoes",
  "price": 129.99,
  "category": "footwear",
  "tags": ["adidas", "running"]
}

Get a Single Product
GET /api/products/:id

Update a Product
PUT /api/products/:id
Body
{
  "price": 119.99,
  "inStock": false
}

Delete a Product
DELETE /api/products/:id

Get All Products with Query Support
GET /api/products

Query Parameters
Param	Description
category	Filter by category
minPrice	Minimum price
maxPrice	Maximum price
sortBy	e.g. price_asc, price_desc
page	Page number (default: 1)
limit	Number per page (default: 10)

Example
GET /api/products?category=shoes&minPrice=50&maxPrice=200&sortBy=price_desc&page=2&limit=5

## Notes
Ensure your MongoDB Atlas cluster is running and your IP is whitelisted

Errors return with proper status codes (400, 404, 500) and messages
