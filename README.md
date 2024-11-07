# Car Dealership Database Schema

This repository defines the database schema for a car dealership management system. The schema includes tables to manage car models, variants, clients, employees, invoices, reviews, and services. Below is an overview of the tables and relationships in the schema.

## Database Schema

- **Schema Name**: `car_dealership`

## ER Diagram

The ER diagram illustrates the main entities in the database and their relationships:
1. **Car Model** - Represents car models and their specifications (e.g., engine type, transmission, fuel efficiency).
2. **Cars** - Represents individual cars in stock, linked to specific models.
3. **Client** - Represents customers who can purchase cars, submit reviews, and request services.
4. **Employee** - Represents employees responsible for sales and services.
5. **Review System** - Allows clients to review car models.
6. **Purchase and Selling Invoices** - Tracks the invoices for car purchases (by clients) and sales (to clients).
7. **Service Invoice** - Tracks details of services provided to cars.

## Tables Overview

### 1. `model_details`
   - Contains details about car models.
   - **Primary Key**: `model_name`

### 2. `variant_details`
   - Contains details about car variants, such as engine type and fuel efficiency.
   - **Primary Key**: `model_id`
   - **Foreign Key**: Links to `model_details`

### 3. `customer` (also referred to as `Client`)
   - Stores client information including contact details.
   - **Primary Key**: `cust_id`

### 4. `employee`
   - Contains information about employees, including their designation and contact details.
   - **Primary Key**: `emp_id`

### 5. `seller`
   - Stores details of sellers, including contact information.
   - **Primary Key**: `seller_id`

### 6. `cars`
   - Represents individual cars with attributes like color and model ID.
   - **Primary Key**: `car_id`
   - **Foreign Key**: Links to `variant_details`

### 7. `service`
   - Tracks service details for each car.
   - **Primary Key**: `service_id`
   - **Foreign Keys**: Links to `cars` and `employee`

### 8. `used_cars`
   - Represents pre-owned cars and includes mileage and seller details.
   - **Primary Key**: Combination of `car_id` and `km_driven`
   - **Foreign Keys**: Links to `cars` and `seller`

### 9. `stock_updates`
   - Tracks stock levels for each car variant.
   - **Primary Key**: `model_id`
   - **Foreign Key**: Links to `variant_details`

### 10. `pre_owned_car_invoice`
   - Tracks sales invoices for pre-owned cars.
   - **Primary Key**: `inv_id`
   - **Foreign Keys**: Links to `seller` and `cars`

### 11. `sales_invoice`
   - Tracks invoices for new car sales.
   - **Primary Key**: `inv_id`
   - **Foreign Keys**: Links to `cars`, `customer`, and `employee`

### 12. `review_system`
   - Allows customers to submit reviews for car models.
   - **Primary Key**: Combination of `model_id` and `cust_id`
   - **Foreign Keys**: Links to `variant_details` and `customer`


