# Orders

## Retrieve Orders

<div class="endpoint">
    <div>
        <div class="method get">GET</div>
        <div class="path">api/orders</div>
    </div>
</div>

```json
[]
```

This endpoing will list all products available. However, it won't include any other related table (for the sake of performance).

## Create Order

<div class="endpoint">
    <div>
        <div class="method post">POST</div>
        <div class="path">api/orders</div>
    </div>
</div>

This will create a paid order. The following payload is an example to create a paid Order. Some of the values provided are required to match what currently exists on the application. For example, you can only use:

- A User group that exists
- A payment method that exists
- A customer who exists
- A valid product type

> Request

```json
{
  "discount_type": null,
  "title": "",
  "discount": 0,
  "discount_percentage": 0,
  "subtotal": 86.45,
  "total": 86.45,
  "coupons": [],
  "total_coupons": 0,
  "tendered": 86.45,
  "note": "",
  "note_visibility": "hidden",
  "tax_group_id": null,
  "tax_type": false,
  "taxes": [],
  "tax_group": {},
  "payment_status": "paid",
  "customer_id": 193,
  "change": 0,
  "total_products": 1,
  "shipping": 0,
  "tax_value": 0,
  "products_tax_value": 0,
  "shipping_rate": 0,
  "customer": {
    "id": "[int]",
    "username": "tressa80",
    "active": 1,
    "author": 156,
    "email": "herman.garret@wisoky.com",
    "password": "$2y$10$FE1x.423LcCK0lkm1sfWYu/hzZd/pnpQDNPeGeF08Obq9sHskyvG6",
    "group_id": 10,
    "first_name": "Constantin",
    "last_name": "Weissnat",
    "gender": "",
    "phone": "726.869.5653",
    "pobox": "71961-8857",
    "activation_expiration": null,
    "total_sales_count": 0,
    "total_sales": 0,
    "birth_date": null,
    "purchases_amount": 0,
    "owed_amount": 0,
    "credit_limit_amount": 0,
    "account_amount": 0,
    "activation_token": null,
    "remember_token": null,
    "created_at": "2025-07-21T23:21:04.000000Z",
    "updated_at": "2025-07-21T23:21:04.000000Z",
    "origin_store_id": null,
    "billing": null,
    "shipping": null,
    "group": {
      "id": 10,
      "name": "[string]",
      "description": null,
      "reward_system_id": null,
      "minimal_credit_payment": 2,
    },
    "selected": true
  },
  "type": {
    "identifier": "[string]",
    "label": "[styring]",
    "icon": "[string]",
    "selected": true
  },
  "products": [
    {
      "product_id": 1,
      "name": "[string]",
      "discount_type": "[percentage|flat]",
      "discount": "float",
      "discount_percentage": "float",
      "product_type": "product",
      "rate": "float",
      "quantity": "float",
      "tax_group_id": "integer",
      "tax_type": "[inclusive|exclusive]",
      "tax_value": "float",
      "unit_id": "integer",
      "unit_price": "float",
      "price_with_tax": "float",
      "price_without_tax": "float",
      "unit_name": "Piece",
      "total_price": "float",
      "total_price_without_tax": "float",
      "total_price_with_tax": "float",
      "mode": "normal",
      "unit_quantity_id": "integer",
      "total_tax_value": "float"
    }
  ],
  "instalments": [],
  "payments": [
    {
      "value": "float",
      "identifier": "[identifier]",
      "selected": false,
      "label": "[string]",
      "readonly": false
    }
  ],
  "addresses": {
    "billing": {}
  },
}
```

> Response

```json
{
    "status": "success",
    "message": "The order has been placed.",
    "data": {
        "order": {
            "created_at": "2025-07-22 00:21:27",
            "customer_id": 193,
            "shipping": 0,
            "subtotal": 86.45,
            "discount_type": null,
            "discount_percentage": 0,
            "discount": 0,
            "total": 86.45,
            "type": "takeaway",
            "final_payment_date": null,
            "total_instalments": 0,
            "register_id": null,
            "note": null,
            "note_visibility": "hidden",
            "updated_at": "2025-07-22 00:21:27",
            "tax_group_id": null,
            "tax_type": false,
            "total_coupons": 0,
            "payment_status": "paid",
            "delivery_status": "not-available",
            "process_status": "not-available",
            "support_instalments": true,
            "author": 2,
            "title": null,
            "tax_value": 0,
            "products_tax_value": 11.924137931,
            "code": "250722-001",
            "tendered": 86.45,
            "total_with_tax": 86.45,
            "total_cogs": 0,
            "change": 0,
            "total_without_tax": 86.45,
            "id": 1,
            "products": [
                {
                    "id": 1,
                    "name": "Twin Comforter Sets",
                    "unit_name": "Piece",
                    "mode": "normal",
                    "product_type": "product",
                    "product_id": 1,
                    "order_id": 1,
                    "unit_id": 1,
                    "unit_quantity_id": 1,
                    "product_category_id": 1,
                    "procurement_product_id": null,
                    "tax_group_id": 1,
                    "tax_type": "inclusive",
                    "uuid": null,
                    "status": "sold",
                    "return_observations": null,
                    "return_condition": null,
                    "discount_type": "percentage",
                    "discount": 0,
                    "quantity": 1,
                    "discount_percentage": 0,
                    "unit_price": 86.45,
                    "price_with_tax": 86.45,
                    "price_without_tax": 74.5259,
                    "wholesale_tax_value": 0,
                    "sale_tax_value": 0,
                    "tax_value": 11.9241,
                    "rate": 0,
                    "total_price": 86.45,
                    "total_price_with_tax": 86.45,
                    "total_price_without_tax": 74.5259,
                    "total_purchase_price": 0,
                    "created_at": "2025-07-21T23:21:28.000000Z",
                    "updated_at": "2025-07-21T23:21:28.000000Z"
                }
            ],
            "payments": [
                {
                    "id": 1,
                    "order_id": 1,
                    "value": 86.45,
                    "author": 2,
                    "identifier": "cash-payment",
                    "uuid": null,
                    "created_at": "2025-07-21T23:21:28.000000Z",
                    "updated_at": "2025-07-21T23:21:28.000000Z"
                }
            ],
            "coupons": [],
            "instalments": [],
            "addresses": [
                {
                    "type": "shipping",
                    "author": 2,
                    "order_id": 1,
                    "updated_at": "2025-07-21T23:21:28.000000Z",
                    "created_at": "2025-07-21T23:21:28.000000Z",
                    "id": 1
                },
                {
                    "type": "billing",
                    "author": 2,
                    "order_id": 1,
                    "updated_at": "2025-07-21T23:21:28.000000Z",
                    "created_at": "2025-07-21T23:21:28.000000Z",
                    "id": 2
                }
            ]
        }
    }
}
```

## Create Unpaid Order

<div class="endpoint">
    <div>
        <div class="method get">POST</div>
        <div class="path">api/orders</div>
    </div>
</div>

The structure to submit an unpaid order is quite similar to the paid order. However, we'll make sure to omit providing a payment. Note that this might throw an error if unpaid order is disabled on the settings. You'll make sure to display a proper message (using the message returned by the server), for further instance to the user.

Here is an example.

```json
{
  "discount_type": null,
  "title": "",
  "discount": 0,
  "discount_percentage": 0,
  "subtotal": 86.45,
  "total": 86.45,
  "coupons": [],
  "total_coupons": 0,
  "tendered": 0,
  "note": "",
  "note_visibility": "hidden",
  "tax_group_id": null,
  "tax_type": false,
  "taxes": [],
  "tax_group": {},
  "payment_status": "unpaid",
  "customer_id": 193,
  "change": 0,
  "total_products": 1,
  "shipping": 0,
  "tax_value": 0,
  "products_tax_value": 0,
  "shipping_rate": 0,
  "customer": {
    "id": "[int]",
    "username": "tressa80",
    "active": 1,
    "author": 156,
    "email": "herman.garret@wisoky.com",
    "password": "$2y$10$FE1x.423LcCK0lkm1sfWYu/hzZd/pnpQDNPeGeF08Obq9sHskyvG6",
    "group_id": 10,
    "first_name": "Constantin",
    "last_name": "Weissnat",
    "gender": "",
    "phone": "726.869.5653",
    "pobox": "71961-8857",
    "activation_expiration": null,
    "total_sales_count": 0,
    "total_sales": 0,
    "birth_date": null,
    "purchases_amount": 0,
    "owed_amount": 0,
    "credit_limit_amount": 0,
    "account_amount": 0,
    "activation_token": null,
    "remember_token": null,
    "created_at": "2025-07-21T23:21:04.000000Z",
    "updated_at": "2025-07-21T23:21:04.000000Z",
    "origin_store_id": null,
    "billing": null,
    "shipping": null,
    "group": {
      "id": 10,
      "name": "[string]",
      "description": null,
      "reward_system_id": null,
      "minimal_credit_payment": 2,
    },
    "selected": true
  },
  "type": {
    "identifier": "[string]",
    "label": "[styring]",
    "icon": "[string]",
    "selected": true
  },
  "products": [
    {
      "product_id": 1,
      "name": "[string]",
      "discount_type": "[percentage|flat]",
      "discount": "float",
      "discount_percentage": "float",
      "product_type": "product",
      "rate": "float",
      "quantity": "float",
      "tax_group_id": "integer",
      "tax_type": "[inclusive|exclusive]",
      "tax_value": "float",
      "unit_id": "integer",
      "unit_price": "float",
      "price_with_tax": "float",
      "price_without_tax": "float",
      "unit_name": "Piece",
      "total_price": "float",
      "total_price_without_tax": "float",
      "total_price_with_tax": "float",
      "mode": "normal",
      "unit_quantity_id": "integer",
      "total_tax_value": "float"
    }
  ],
  "instalments": [],
  "payments": [],
  "addresses": {
    "billing": {}
  },
}
```

> Response