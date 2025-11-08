# Express.js RESTful API Assignment

This assignment focuses on building a RESTful API using Express.js, implementing proper routing, middleware, and error handling.

## Assignment Overview

You will:
1. Set up an Express.js server
2. Create RESTful API routes for a product resource
3. Implement custom middleware for logging, authentication, and validation
4. Add comprehensive error handling
5. Develop advanced features like filtering, pagination, and search

## Getting Started

1. Accept the GitHub Classroom assignment invitation
2. Clone your personal repository that was created by GitHub Classroom
3. Install dependencies:
   ```
   npm install
   ```
4. Run the server:
   ```
   npm start
   ```

## Files Included

- `Week2-Assignment.md`: Detailed assignment instructions
- `server.js`: Starter Express.js server file
- `.env.example`: Example environment variables file

## Requirements

- Node.js (v18 or higher)
- npm or yarn
- Postman, Insomnia, or curl for API testing

## API Documentation

### Authentication

All API endpoints require authentication. Include an Authorization header with your token:

```http
Authorization: 1234
```

If the token is missing or invalid, you'll receive a 401 Unauthorized response.

### API Endpoints

#### Get All Products
```http
GET /api/products
```

**Response** (200 OK)
```json
[
  {
    "id": "1",
    "name": "Laptop",
    "description": "High-performance laptop with 16GB RAM",
    "price": 1200,
    "category": "electronics",
    "inStock": true
  },
  {
    "id": "2",
    "name": "Smartphone",
    "description": "Latest model with 128GB storage",
    "price": 800,
    "category": "electronics",
    "inStock": true
  }
]
```

#### Get Single Product
```http
GET /api/products/:id
```

**Response** (200 OK)
```json
{
  "id": "1",
  "name": "Laptop",
  "description": "High-performance laptop with 16GB RAM",
  "price": 1200,
  "category": "electronics",
  "inStock": true
}
```

#### Create Product
```http
POST /api/products
```

**Request Body**
```json
{
  "name": "Headphones",
  "description": "Wireless noise-canceling headphones",
  "price": 199,
  "category": "electronics",
  "inStock": true
}
```

**Response** (201 Created)
```json
{
  "id": "4",
  "name": "Headphones",
  "description": "Wireless noise-canceling headphones",
  "price": 199,
  "category": "electronics",
  "inStock": true
}
```

#### Update Product
```http
PUT /api/products/:id
```

**Request Body**
```json
{
  "price": 179,
  "inStock": false
}
```

**Response** (200 OK)
```json
{
  "id": "4",
  "name": "Headphones",
  "description": "Wireless noise-canceling headphones",
  "price": 179,
  "category": "electronics",
  "inStock": false
}
```

#### Delete Product
```http
DELETE /api/products/:id
```

**Response** (200 OK)
```json
{
  "message": "Product deleted successfully"
}
```

### Error Responses

#### 400 Bad Request
Returned when required fields are missing in the request body.
```json
{
  "message": "All product fields are required"
}
```

#### 401 Unauthorized
Returned when the authentication token is missing or invalid.
```json
{
  "message": "Unauthorized"
}
```

#### 404 Not Found
Returned when the requested product doesn't exist.
```json
{
  "message": "Product not found"
}
```

#### 500 Internal Server Error
Returned when an unexpected error occurs on the server.
```json
{
  "message": "Internal server error!"
}
```

## Submission

Your work will be automatically submitted when you push to your GitHub Classroom repository. Make sure to:

1. Complete all the required API endpoints
2. Implement the middleware and error handling
3. Document your API in the README.md
4. Include examples of requests and responses

## Resources

- [Express.js Documentation](https://expressjs.com/)
- [RESTful API Design Best Practices](https://restfulapi.net/)
- [HTTP Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) 