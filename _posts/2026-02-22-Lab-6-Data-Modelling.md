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

