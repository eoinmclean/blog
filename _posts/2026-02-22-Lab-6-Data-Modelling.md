---
layout: post
title: "Lab 6 Data Modeling"
date: 2026-02-22
author: "Eoin Mclean"
---
## Assumptions
- Each item is made by exactly one manufacturer.
- Customers register with name, address, and phone number.
- A customer can create multiple orders.
- Orders have a status: DRAFT or FINALIZED, and finalized orders cannot be edited.
- An order contains multiple line items.
- Substitution preference and special instructions are stored per line item.
- Pickup vs delivery is stored on the order.
- The fulfillment date and time are chosen when the order is finalized.

## User Stories

1) **Customer Registration**
- **As a customer**, I want to register with my name, address, and phone number so I can place orders.
- **Size:** 3
- **Depends on:** none

2) **Owner Creates/Manages Items**
- **As the store owner**, I want to create and update items with name, price, description, quantity available, and manufacturer so customers can shop.
- **Size:** 5
- **Depends on:** Story 3

3) **Owner Manages Manufacturers**
- **As the store owner**, I want to add/edit manufacturers so each item can be associated with a manufacturer.
- **Size:** 2
- **Depends on:** none

4) **Customer Starts an Order**
- **As a customer**, I want to start an order and choose pickup or delivery so I can build a cart.
- **Size:** 3
- **Depends on:** Story 1

5) **Customer Adds Items to an Order**
- **As a customer**, I want to add items with quantity desired, special instructions, and substitution preference so the store fulfills the order correctly.
- **Size:** 5
- **Depends on:** Story 2 and Story 4

6) **Customer Finalizes Order with Date/Time**
- **As a customer**, I want to finalize my order and choose a date/time so it gets scheduled and cannot be edited afterwards.
- **Size:** 5
- **Depends on:** Story 5

## ER Diagram (LucidChart)

![ER Diagram]( /blog/assets/lab6/erd.png )

## Redgate Schema

![Redgate Schema]( /blog/assets/lab6/sqllite.png)

## Reflection

To build this model, I identified the core entities described in the scenario: Customer, Manufacturer, Item, Order, and OrderItem. Customers place orders, manufacturers produce items, and orders contain multiple items. Because orders and items have a many-to-many relationship, I introduced the OrderItem table to store quantity, substitution preference, and special instructions for each item in an order.

The ER diagram represents the logical structure of the system, focusing on entities, attributes, and cardinality. It shows one-to-many relationships between Customer and Order, Manufacturer and Item, and Order and OrderItem. The SQL schema represents the physical implementation of this design in a database. Each entity becomes a table with defined data types, primary keys, and foreign keys that enforce referential integrity.

Overall, I am satisfied with the data representation because it accurately models the ordering process and maintains clear relational structure. One complication in implementation would be managing inventory updates when multiple customers place orders simultaneously. Another challenge would be enforcing that finalized orders cannot be modified, which would require additional application logic or database constraints. Despite these considerations, the schema provides a solid foundation for an online grocery ordering system.