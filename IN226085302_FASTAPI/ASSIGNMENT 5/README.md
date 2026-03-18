# FASTAPI Assignment 5

## 1. Search Endpoint

GET /products/search?keyword=mouse  
→ Wireless Mouse, total_found: 1  

GET /products/search?keyword=MOUSE  
→ Same result (case-insensitive)

GET /products/search?keyword=e  
→ Wireless Mouse, Notebook, Pen Set (3 results)

GET /products/search?keyword=laptop  
→ "No products found for: laptop"


## 2. Sort Products

GET /products/sort?sort_by=price&order=asc  
→ Pen Set (₹49)

GET /products/sort?sort_by=price&order=desc  
→ USB Hub (₹799)

GET /products/sort?sort_by=name&order=asc  
→ Notebook → Pen Set → USB Hub → Wireless Mouse

GET /products/sort?sort_by=category  
→ Error: sort_by must be 'price' or 'name'

GET /products/sort  
→ Defaults: sort_by=price, order=asc


## 3. Pagination

GET /products/page?page=1&limit=2  
→ Wireless Mouse, Notebook (total_pages: 2)

GET /products/page?page=2&limit=2  
→ USB Hub, Pen Set

GET /products/page?page=3&limit=2  
→ []

GET /products/page?page=1&limit=1  
→ Wireless Mouse (total_pages: 4)

GET /products/page  
→ Defaults: page=1, limit=2


## 4. Search Orders

GET /orders/search?customer_name=rahul  
→ Returns all orders containing "rahul" (case-insensitive)


## 5. Sort by Category then Price

GET /products/sort-by-category  

Electronics  
→ Wireless Mouse ₹499  
→ USB Hub ₹799  

Stationery  
→ Pen Set ₹49  
→ Notebook ₹99  


## 6. Browse (Search + Sort + Pagination)

GET /products/browse  
→ All products sorted by price asc

GET /products/browse?keyword=e&sort_by=price&order=asc&page=1&limit=2  
→ Filtered + sorted + paginated

GET /products/browse?sort_by=name&order=desc&page=1&limit=2  
→ Sorted Z→A + paginated


## ⭐ Bonus

GET /orders/page?page=1&limit=3  
→ First 3 orders

GET /orders/page?page=2&limit=3  
→ Next orders
