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

