# FASTAPI Assignment 4

## Overview
This assignment implements a simple Shopping Cart system using FastAPI where users can add items, view the cart, remove items, and checkout.

## Features
- Add items to cart
- Update quantity of existing items
- View cart with total price
- Remove items from cart
- Checkout and create orders
- Error handling for out-of-stock and empty cart

## Endpoints

### Add Item
POST /cart/add?product_id=1&quantity=2

### View Cart
GET /cart

### Remove Item
DELETE /cart/{product_id}

Example:
DELETE /cart/2

### Checkout
POST /cart/checkout

Body Example:
{
  "customer_name": "Customer",
  "delivery_address": "Sample delivery address"
}

### View Orders
GET /orders

## Error Cases

Out of Stock:
POST /cart/add?product_id=3
Response:
{ "detail": "USB Hub is out of stock" }

Invalid Product:
POST /cart/add?product_id=99
Status: 404 Not Found

Empty Cart Checkout:
POST /cart/checkout
Response:
{ "detail": "CART_EMPTY" }

