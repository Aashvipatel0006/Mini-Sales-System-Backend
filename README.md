This is the backend service for the Mini Sales Order System.
It handles products, orders, stock validation, and inventory updates using Node.js, Express, and MongoDB.

* Tech Stack

Node.js

Express.js

MongoDB

Mongoose

dotenv

* API Endpoints
* Create Product

POST /api/products

{
  "name": "Laptop",
  "price": 50000,
  "stock": 10
}

* Get All Products

GET /api/products

Response:

[
  {
    "_id": "abc123",
    "name": "Laptop",
    "price": 50000,
    "stock": 10
  }
]

* Create Order

POST /api/orders

{
  "customerName": "John",
  "productId": "abc123",
  "quantity": 2
}

* Business Logic

Checks if stock is available

Rejects order if quantity > stock

Reduces stock after successful order

* Error Handling

Returns proper JSON error messages

{
  "message": "Insufficient stock"
}

* Installation & Run
npm install
npm run dev

* Environment Variables

Create a .env file:

PORT=5000
MONGO_URI=mongodb://localhost:27017/sales-order-db

backend/
├─ config/db.js
├─ models/
│  ├─ Product.js
│  └─ Order.js
├─ controllers/
│  ├─ productController.js
│  └─ orderController.js
├─ routes/
│  ├─ productRoutes.js
│  └─ orderRoutes.js
├─ index.js
└─ package.json
