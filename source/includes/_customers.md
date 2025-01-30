# Customers

## Retreive Customers

This endpoint will retreive all registered customers. The output is not paginated, you might therefore consider using the CRUD approach.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/customers</div>
    </div>
</div>

> Response

```json
[
  {
    "id": 1792,
    "username": "dooley.linnea",
    "active": 1,
    "author": 1723,
    "email": "xxx@xxx.com",
    "password": "$2y$10$3q81nABSmQzwiGaWUBD6Y.UHguEtBJ2PGH/l4Sy5FPW9FfPV5Lx0a",
    "group_id": 9,
    "first_name": "Rita",
    "last_name": "Batz",
    "gender": "male",
    "phone": "+1.000.000.000",
    "pobox": "00000",
    "activation_expiration": null,
    "total_sales_count": 0,
    "total_sales": 0,
    "birth_date": null,
    "purchases_amount": 216.00000464,
    "owed_amount": 0,
    "credit_limit_amount": 0,
    "account_amount": 0,
    "activation_token": null,
    "remember_token": null,
    "created_at": "2025-01-26T23:19:41.000000Z",
    "updated_at": "2025-01-30T10:55:11.000000Z",
    "origin_store_id": null,
    "wc_customer_id": null,
    "billing": null,
    "shipping": null
  }
]
```

## Retreive Single Customer

Use this endpoint to details for a specific customer. You'll make sure to replace `{customer_id}` with the ID of the customer for which you would like to get information.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/customers/{customer_id}</div>
    </div>
</div>

> Response

```json
{
  "id": 1792,
  "username": "dooley.linnea",
  "active": 1,
  "author": 1723,
  "email": "nmetz@funk.com",
  "password": "$2y$10$3q81nABSmQzwiGaWUBD6Y.UHguEtBJ2PGH/l4Sy5FPW9FfPV5Lx0a",
  "group_id": 9,
  "first_name": "Rita",
  "last_name": "Batz",
  "gender": "male",
  "phone": "+1.660.362.3086",
  "pobox": "32287",
  "activation_expiration": null,
  "total_sales_count": 0,
  "total_sales": 0,
  "birth_date": null,
  "purchases_amount": 216.00000464,
  "owed_amount": 0,
  "credit_limit_amount": 0,
  "account_amount": 0,
  "activation_token": null,
  "remember_token": null,
  "created_at": "2025-01-26T23:19:41.000000Z",
  "updated_at": "2025-01-30T10:55:11.000000Z",
  "origin_store_id": null,
  "wc_customer_id": null,
  "group": {
    "id": 9,
    "name": "Virtual optimal throughput",
    "description": null,
    "reward_system_id": null,
    "minimal_credit_payment": 27,
    "author": 9,
    "uuid": null,
    "created_at": "2025-01-26T23:19:40.000000Z",
    "updated_at": "2025-01-26T23:19:40.000000Z"
  },
  "billing": null,
  "shipping": null
}
```

## Recently Active Customers

This endpoint will give a list of the customers that has recently been active.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/customers/recently-active</div>
    </div>
</div>

> Response

```json
[
  {
    "id": 1796,
    "username": "hudson.keshawn",
    "active": 1,
    "author": 1722,
    "email": "karli39@yahoo.com",
    "password": "$2y$10$xJTDtiBtOtsMWU8MqnHa6eaRjZRisOgxXWkujnpSlFoIynvONjyba",
    "group_id": 9,
    "first_name": "Adrienne",
    "last_name": "Gerhold",
    "gender": "male",
    "phone": "+1.734.246.6288",
    "pobox": "31266",
    "activation_expiration": null,
    "total_sales_count": 0,
    "total_sales": 0,
    "birth_date": null,
    "purchases_amount": 880.00003056,
    "owed_amount": 0,
    "credit_limit_amount": 0,
    "account_amount": 0,
    "activation_token": null,
    "remember_token": null,
    "created_at": "2025-01-26T23:19:41.000000Z",
    "updated_at": "2025-01-30T11:14:43.000000Z",
    "origin_store_id": null,
    "wc_customer_id": null,
    "billing": null,
    "shipping": null,
    "group": {
      "id": 9,
      "name": "Virtual optimal throughput",
      "description": null,
      "reward_system_id": null,
      "minimal_credit_payment": 27,
      "author": 9,
      "uuid": null,
      "created_at": "2025-01-26T23:19:40.000000Z",
      "updated_at": "2025-01-26T23:19:40.000000Z"
    }
  }
]
```

## Customer Latest Orders

Use this endpoint to retreive latest orders placed by a specific customer.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/customers/{customer_id}/orders</div>
    </div>
</div>

> Response

```json
[
  {
    "id": 20,
    "description": null,
    "code": "250130-016",
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
    "total_without_tax": 100,
    "subtotal": 100,
    "total_with_tax": 100,
    "total_coupons": 0,
    "total_cogs": 0,
    "total": 100,
    "tax_value": 0,
    "products_tax_value": 13.793104,
    "total_tax_value": 0,
    "tax_group_id": 1,
    "tax_type": "exclusive",
    "tendered": 100,
    "change": 0,
    "final_payment_date": null,
    "total_instalments": 0,
    "customer_id": 1796,
    "note": null,
    "note_visibility": "hidden",
    "author": 8,
    "uuid": null,
    "register_id": null,
    "voidance_reason": null,
    "created_at": "2025-01-30 11:14:41",
    "updated_at": "2025-01-30 11:14:41",
    "human_status": "Paid",
    "human_delivery_status": "Not Available"
  },
]
```