# Orders

## Retrieve Orders

To retreive all orders, the endpoint will be used without the identifier of the order. The result will then be an Array of orders. When an identifier is provided, a single entry of the array will be provided if that exists.

<div class="endpoint">
    <div>
        <div class="method get">GET</div>
        <div class="path">api/orders/{id?}</div>
    </div>
</div>

```json
[
  {
      "id": 1,
      "description": null,
      "code": "250722-001",
      "title": null,
      "type": "takeaway",
      "payment_status": "paid",
      "process_status": "not-available",
      "delivery_status": "not-available",
      "discount": 0,
      "discount_type": null,
      "support_instalments": true,
      "discount_percentage": 0,
      "shipping": 0,
      "shipping_rate": 0,
      "shipping_type": null,
      "total_without_tax": 86.45,
      "subtotal": 86.45,
      "total_with_tax": 86.45,
      "total_coupons": 0,
      "total_cogs": 0,
      "total": 86.45,
      "tax_value": 0,
      "products_tax_value": 11.924137931,
      "tax_group_id": null,
      "tax_type": "0",
      "tendered": 86.45,
      "change": 0,
      "final_payment_date": null,
      "total_instalments": 0,
      "customer_id": 193,
      "note": null,
      "note_visibility": "hidden",
      "author": 2,
      "uuid": null,
      "register_id": null,
      "voidance_reason": null,
      "driver_id": null,
      "created_at": "2025-07-22 00:21:27",
      "updated_at": "2025-07-22 00:21:27",
      "customer": {
          "id": 193,
          "username": "tressa80",
          "active": 1,
          "author": 156,
          "email": "user@example.com",
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
          "origin_store_id": null
      }
  }
]
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
    "email": "user@example.com",
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

## Update Order

<div class="endpoint">
    <div>
        <div class="method post">PUT</div>
        <div class="path">api/orders/{id}</div>
    </div>
</div>

When an identifier is provided to this endpoint, it can be used to retrieve an order and to update it. However, the request might fails for some reasons:

- The order cannot be found
- The user is not allowed to edit orders
- The order has already been paid

For each situations, a clear message will be returned by the server with the HTTP error 403. 

Hold can be modified. The payload for updating an order is similar to the payload used to create an order.

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
    "email": "user@example.com",
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

## Retrieve Full Order

<div class="endpoint">
    <div>
        <div class="method post">GET</div>
        <div class="path">api/orders/{id}</div>
    </div>
</div>

If the endpoint "api/orders/{id}/{attribute?}" allows to retrieve a specific order, this endpoint will retreive an order with all it's linked attributes. By default, NexoPOS assumes "{id}" is a number ("id"). However when providing "{attribute}", you can change it to be the order code with "code". 

> Response

```json
{
    "id": 1,
    "description": null,
    "code": "250722-001",
    "title": null,
    "type": "takeaway",
    "payment_status": "paid",
    "process_status": "not-available",
    "delivery_status": "not-available",
    "discount": 0,
    "discount_type": null,
    "support_instalments": true,
    "discount_percentage": 0,
    "shipping": 0,
    "shipping_rate": 0,
    "shipping_type": null,
    "total_without_tax": 86.45,
    "subtotal": 86.45,
    "total_with_tax": 86.45,
    "total_coupons": 0,
    "total_cogs": 0,
    "total": 86.45,
    "tax_value": 0,
    "products_tax_value": 11.924137931,
    "tax_group_id": null,
    "tax_type": "0",
    "tendered": 86.45,
    "change": 0,
    "final_payment_date": null,
    "total_instalments": 0,
    "customer_id": 193,
    "note": null,
    "note_visibility": "hidden",
    "author": 2,
    "uuid": null,
    "register_id": null,
    "voidance_reason": null,
    "driver_id": null,
    "created_at": "2025-07-22 00:21:27",
    "updated_at": "2025-07-22 00:21:27",
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
    "shipping_address": {
        "id": 1,
        "order_id": 1,
        "type": "shipping",
        "first_name": null,
        "last_name": null,
        "phone": null,
        "address_1": null,
        "email": null,
        "address_2": null,
        "country": null,
        "city": null,
        "pobox": null,
        "company": null,
        "author": 2,
        "uuid": null,
        "created_at": "2025-07-21T23:21:28.000000Z",
        "updated_at": "2025-07-21T23:21:28.000000Z"
    },
    "billing_address": {
        "id": 2,
        "order_id": 1,
        "type": "billing",
        "first_name": null,
        "last_name": null,
        "phone": null,
        "address_1": null,
        "email": null,
        "address_2": null,
        "country": null,
        "city": null,
        "pobox": null,
        "company": null,
        "author": 2,
        "uuid": null,
        "created_at": "2025-07-21T23:21:28.000000Z",
        "updated_at": "2025-07-21T23:21:28.000000Z"
    },
    "taxes": [],
    "instalments": [],
    "coupons": [],
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
            "updated_at": "2025-07-21T23:21:28.000000Z",
            "product": {
                "id": 1,
                "name": "Twin Comforter Sets",
                "tax_type": "inclusive",
                "tax_group_id": 1,
                "tax_value": 0,
                "product_type": "product",
                "type": "dematerialized",
                "accurate_tracking": false,
                "auto_cogs": false,
                "status": "available",
                "stock_management": "enabled",
                "barcode": "yNiawSx0",
                "barcode_type": "code128",
                "sku": "yNiawSx0",
                "description": "generated",
                "thumbnail_id": null,
                "category_id": 1,
                "parent_id": 0,
                "unit_group": 1,
                "on_expiration": "prevent_sales",
                "expires": 0,
                "searchable": 1,
                "author": 2,
                "uuid": null,
                "created_at": "2025-07-21T23:21:04.000000Z",
                "updated_at": "2025-07-21T23:21:04.000000Z",
                "tax_group": {
                    "id": 1,
                    "name": "GST",
                    "description": null,
                    "author": 2,
                    "uuid": null,
                    "created_at": "2025-07-21T23:21:04.000000Z",
                    "updated_at": "2025-07-21T23:21:04.000000Z",
                    "taxes": [
                        {
                            "id": 1,
                            "name": "SGST",
                            "description": null,
                            "rate": 8,
                            "tax_group_id": 1,
                            "author": 2,
                            "uuid": null,
                            "created_at": "2025-07-21T23:21:04.000000Z",
                            "updated_at": "2025-07-21T23:21:04.000000Z"
                        },
                        {
                            "id": 2,
                            "name": "CGST",
                            "description": null,
                            "rate": 8,
                            "tax_group_id": 1,
                            "author": 2,
                            "uuid": null,
                            "created_at": "2025-07-21T23:21:04.000000Z",
                            "updated_at": "2025-07-21T23:21:04.000000Z"
                        }
                    ]
                },
                "unit_quantities": [
                    {
                        "id": 1,
                        "product_id": 1,
                        "type": "product",
                        "preview_url": "https//website.com/images/products/twin-comforter-sets.jpg",
                        "expiration_date": null,
                        "unit_id": 1,
                        "barcode": "yNiawSx0-1",
                        "quantity": 780,
                        "low_quantity": 0,
                        "stock_alert_enabled": 0,
                        "sale_price": 86.45,
                        "sale_price_edit": 86.45,
                        "sale_price_without_tax": 74.5259,
                        "sale_price_with_tax": 86.45,
                        "sale_price_tax": 11.9241,
                        "wholesale_price": 74.5259,
                        "wholesale_price_edit": 86.45,
                        "wholesale_price_with_tax": 86.45,
                        "wholesale_price_without_tax": 74.5259,
                        "wholesale_price_tax": 11.9241,
                        "custom_price": 0,
                        "custom_price_edit": 0,
                        "custom_price_with_tax": 0,
                        "custom_price_without_tax": 0,
                        "custom_price_tax": 0,
                        "visible": 1,
                        "convert_unit_id": null,
                        "cogs": 0,
                        "uuid": null,
                        "created_at": "2025-07-21T23:21:04.000000Z",
                        "updated_at": "2025-07-21T23:21:28.000000Z"
                    },
                    {
                        "id": 2,
                        "product_id": 1,
                        "type": "product",
                        "preview_url": "https//website.com/images/products/twin-comforter-sets.jpg",
                        "expiration_date": null,
                        "unit_id": 2,
                        "barcode": "yNiawSx0-2",
                        "quantity": 883,
                        "low_quantity": 0,
                        "stock_alert_enabled": 0,
                        "sale_price": 518.7,
                        "sale_price_edit": 518.7,
                        "sale_price_without_tax": 447.155,
                        "sale_price_with_tax": 518.7,
                        "sale_price_tax": 71.5448,
                        "wholesale_price": 447.155,
                        "wholesale_price_edit": 518.7,
                        "wholesale_price_with_tax": 518.7,
                        "wholesale_price_without_tax": 447.155,
                        "wholesale_price_tax": 71.5448,
                        "custom_price": 0,
                        "custom_price_edit": 0,
                        "custom_price_with_tax": 0,
                        "custom_price_without_tax": 0,
                        "custom_price_tax": 0,
                        "visible": 1,
                        "convert_unit_id": null,
                        "cogs": 0,
                        "uuid": null,
                        "created_at": "2025-07-21T23:21:04.000000Z",
                        "updated_at": "2025-07-21T23:21:15.000000Z"
                    },
                    {
                        "id": 3,
                        "product_id": 1,
                        "type": "product",
                        "preview_url": "https//website.com/products/twin-comforter-sets.jpg",
                        "expiration_date": null,
                        "unit_id": 3,
                        "barcode": "yNiawSx0-3",
                        "quantity": 871,
                        "low_quantity": 0,
                        "stock_alert_enabled": 0,
                        "sale_price": 1037.4,
                        "sale_price_edit": 1037.4,
                        "sale_price_without_tax": 894.31,
                        "sale_price_with_tax": 1037.4,
                        "sale_price_tax": 143.09,
                        "wholesale_price": 894.31,
                        "wholesale_price_edit": 1037.4,
                        "wholesale_price_with_tax": 1037.4,
                        "wholesale_price_without_tax": 894.31,
                        "wholesale_price_tax": 143.09,
                        "custom_price": 0,
                        "custom_price_edit": 0,
                        "custom_price_with_tax": 0,
                        "custom_price_without_tax": 0,
                        "custom_price_tax": 0,
                        "visible": 1,
                        "convert_unit_id": null,
                        "cogs": 0,
                        "uuid": null,
                        "created_at": "2025-07-21T23:21:04.000000Z",
                        "updated_at": "2025-07-21T23:21:15.000000Z"
                    }
                ]
            },
            "unit": {
                "id": 1,
                "name": "Piece",
                "identifier": "piece",
                "description": "",
                "author": 2,
                "group_id": 1,
                "value": 1,
                "preview_url": null,
                "base_unit": true,
                "uuid": null,
                "created_at": "2025-07-21T23:20:57.000000Z",
                "updated_at": "2025-07-21T23:20:57.000000Z"
            }
        }
    ],
    "customer": {
        "id": 193,
        "username": "tressa80",
        "active": 1,
        "author": 156,
        "email": "user@example.com",
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
        "shipping": null
    }
}
```

## About Payment Status

<div class="endpoint">
    <div>
        <div class="method get">POST</div>
        <div class="path">api/orders</div>
    </div>
</div>

While submitting an order, depending on the current payment status, NexoPOS will determine the order type. If an order has a payment that covers the order total, the order
will be marked as "PAID", if it doesn't completely "Paritally Paid" (if settings allows it) if not paid it can either be "Unpaid" or "Hold". The difference between a "Hold" order and an "Unpaid", the first doesn't perform any change on the inventory, while the latest does.

### Support Payment Status
Here is the list of supported payment status.

- paid
- unpaid
- partially_paid
- hold
- refunded
- partially_refunded
- voided

When an order has no payment, NexoPOS allows providing a custom payment status ("hold" or "unpaid"). For other payment status such as "partially_paid", "refunded" they can only be set after an account that updates the status automatically.

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
    "email": "user@example.com",
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

```json
```

## Get Supported Payments

<div class="endpoint">
    <div>
        <div class="method get">GET</div>
        <div class="path">api/orders/payments</div>
    </div>
</div>

This provide a list of payments that are available on the system.

> Response

```json
[
    {
        "label": "Select Payment",
        "name": "identifier",
        "validation": "required",
        "options": [
            {
                "id": 1,
                "label": "Cash",
                "identifier": "cash-payment",
                "priority": 0,
                "description": null,
                "author": 2,
                "active": 1,
                "readonly": 1,
                "created_at": "2025-07-21T23:20:57.000000Z",
                "updated_at": "2025-07-21T23:20:57.000000Z",
                "value": "cash-payment"
            },
            {
                "id": 2,
                "label": "Bank Payment",
                "identifier": "bank-payment",
                "priority": 0,
                "description": null,
                "author": 2,
                "active": 1,
                "readonly": 1,
                "created_at": "2025-07-21T23:20:57.000000Z",
                "updated_at": "2025-07-21T23:20:57.000000Z",
                "value": "bank-payment"
            },
            {
                "id": 3,
                "label": "Customer Account",
                "identifier": "account-payment",
                "priority": 0,
                "description": null,
                "author": 2,
                "active": 1,
                "readonly": 1,
                "created_at": "2025-07-21T23:20:57.000000Z",
                "updated_at": "2025-07-21T23:20:57.000000Z",
                "value": "account-payment"
            }
        ],
        "value": "",
        "description": "choose the payment type.",
        "disabled": false,
        "type": "select",
        "component": "",
        "props": [],
        "refresh": false,
        "errors": [],
        "show": null
    }
]
```
## Order Processing Status

<div class="endpoint">
    <div>
        <div class="method get">POST</div>
        <div class="path">api/orders/{id}/processing</div>
    </div>
</div>

To perform a processing change on a specific order. This requires the order to be created first as it identifier is used. The supported status are: 

- pending
- ongoing
- ready
- failed

> Request

```json
{
  "process_status": "[status]"
}
```

> Resposne

```json
{
  "status": "[success|error]",
  "message": "[string]"
}
```