# FastAPI Assignment 3

---

## How to Run

Install dependencies:

pip install fastapi uvicorn

Run the server:

uvicorn main:app --reload

Open Swagger UI:

http://127.0.0.1:8000/docs

---

## Initial Products

1. Wireless Mouse — ₹499 — Electronics — In Stock  
2. Notebook — ₹99 — Stationery — In Stock  
3. USB Hub — ₹799 — Electronics — Out of Stock  
4. Pen Set — ₹49 — Stationery — In Stock  

---

## Implemented Endpoints

### 1. Add Product
POST /products  

Adds a new product to the catalogue.  
Duplicate names return **400 Bad Request**.

---

### 2. Update Product
PUT /products/{product_id}

Updates price or stock status using query parameters.

Example:
PUT /products/3?in_stock=true  
PUT /products/3?price=699

---

### 3. Delete Product
DELETE /products/{product_id}

Removes a product from the catalogue.  
If product does not exist → **404 Not Found**.

---

### 4. Inventory Audit
GET /products/audit

Returns a summary including:
- total_products
- in_stock_count
- out_of_stock_names
- total_stock_value (price × 10 units)
- most_expensive product

---

### 5. Category Discount
PUT /products/discount

Applies a percentage discount to all products in a category.

Example:
PUT /products/discount?category=Electronics&discount_percent=10

---



