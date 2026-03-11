# Product API (FastAPI)

## Endpoints

### Q1 – Filter Products
`GET /products/filter?min_price=&max_price=`

- `/products/filter?min_price=400` → Wireless Mouse, USB Hub  
- `/products/filter?min_price=100&max_price=600` → Wireless Mouse

---

### Q2 – Product Price
`GET /products/{product_id}/price`

Returns only **name and price**.  

Invalid ID → **Product not found**

---

### Q3 – Feedback
`POST /feedback`

- rating must be **1–5**
- comment **optional**
- rating=6 → **422 validation error**

---

### Q4 – Product Summary
`GET /products/summary`

Returns:
- total_products
- average_price
- total_stock
- most_expensive
- cheapest

---

### Q5 – Bulk Orders
`POST /orders/bulk`

- In-stock items → **confirmed**
- Out-of-stock → **failed**
- Response includes **grand_total**

---

### ⭐ Bonus
Orders start as **pending**

`PATCH /confirm` → status becomes **confirmed**
