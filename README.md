# Supermart Database

## Overview
This repository contains the Entity-Relationship Diagram (ERD) and accompanying database schema documentation for the Supermart system. The ERD outlines the relationships and attributes of various entities such as Customers, Invoices, Products, Discounts, and Payments within the system.

## Database Schema
The schema is designed to manage a retail environment where customers can purchase products, and their transactions are recorded through invoices, along with associated discounts, taxes, and payments.

## Entities and Attributes
1. Categories
category_id (INT): Unique identifier for each category.
category_name (VARCHAR(100)): Name of the category.

2. Customer_Invoices
customer_invoice_id (INT): Unique identifier for customer invoices.
customer_id (INT): Refers to a specific customer.
invoice_id (INT): Refers to a specific invoice.

3. Customers
customer_id (INT): Unique identifier for each customer.
customer_name (VARCHAR(100)): Name of the customer.
contact_info (VARCHAR(100)): Customer's contact details.
address (TEXT): Address of the customer.

4. Discounts
discount_id (INT): Unique identifier for each discount.
discount_name (VARCHAR(100)): Name of the discount.
discount_rate (DECIMAL(5,2)): Discount rate.
discount_type (VARCHAR(50)): Type of discount (e.g., percentage, fixed).

5. Invoice_Discounts
invoice_discount_id (INT): Unique identifier for invoice discounts.
invoice_id (INT): Refers to a specific invoice.
discount_id (INT): Refers to a specific discount.
discount_amount (DECIMAL(10,2)): Amount discounted on the invoice.

6. Invoice_Items
invoice_item_id (INT): Unique identifier for each invoice item.
invoice_id (INT): Refers to a specific invoice.
item_id (INT): Refers to a specific product.

7. Invoice_Payments
invoice_payment_id (INT): Unique identifier for invoice payments.
invoice_id (INT): Refers to a specific invoice.
payment_method_id (INT): Refers to the payment method used.
payment_amount (DECIMAL(10,2)): Total amount paid.
payment_date (DATE): Date of payment.

8. Invoices
invoice_id (INT): Unique identifier for each invoice.
invoice_date (DATE): Date when the invoice was generated.
party (VARCHAR(100)): The party involved in the invoice.
net_amount (DECIMAL(10,2)): Net amount of the invoice.
username (VARCHAR(50)): Username of the person generating the invoice.
time (TIME): Time of invoice generation.

9. Payment_Methods
payment_method_id (INT): Unique identifier for each payment method.
method_name (VARCHAR(50)): Name of the payment method.

10. Product_Discounts
product_discount_id (INT): Unique identifier for product discounts.
product_id (INT): Refers to a specific product.
discount_id (INT): Refers to a specific discount.

11. Product_Taxes
product_tax_id (INT): Unique identifier for product taxes.
product_id (INT): Refers to a specific product.
tax_id (INT): Refers to a specific tax.

12. Products
product_id (INT): Unique identifier for each product.
product_name (VARCHAR(255)): Name of the product.
category_id (INT): Refers to the category the product belongs to.
mrp (DECIMAL(10,2)): Maximum retail price of the product.
cost_price (DECIMAL(10,2)): Cost price of the product.

13. Savings
invoice_id (INT): Refers to a specific invoice.
total_savings (DECIMAL(10,2)): Total savings on the invoice.

14. Taxes
tax_id (INT): Unique identifier for each tax.
tax_name (VARCHAR(100)): Name of the tax.
tax_rate (DECIMAL(5,2)): Tax rate.
