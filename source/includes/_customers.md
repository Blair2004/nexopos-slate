# Customers

## Create Customer

Use this endpoint to create a customer.

<div class="endpoint">
    <div>
        <div class="method post">post</div>
        <div class="path">api/customers</div>
    </div>
</div>

> Request

```json
{
  "general" : {
    "first_name": "[string]",
    "last_name": "[string]",
    "email": "[string]",
    "phone": "[string]",
    "address_1": "[string]",
    "address_2": "[string]",
    "country": "[string]",
    "city": "[string]",
    "pobox": "[string]",
    "company": "[string]",
    "uuid": "[string]",
    "author": "[number]"
  },
  "address": {
    "billing": {
      "first_name": "[string]",
      "last_name": "[string]",
      "email": "[string]",
      "phone": "[string]",
      "address_1": "[string]",
      "address_2": "[string]",
      "country": "[string]",
      "city": "[string]",
      "pobox": "[string]",
      "company": "[string]",
      "uuid": "[string]",
    },
    "shipping": {
      "first_name": "[string]",
      "last_name": "[string]",
      "email": "[string]",
      "phone": "[string]",
      "address_1": "[string]",
      "address_2": "[string]",
      "country": "[string]",
      "city": "[string]",
      "pobox": "[string]",
      "company": "[string]",
      "uuid": "[string]",
    }
  }
}
```

> Response 

```json
{
  "status": "[success|error]",
  "message": "[string]"
}
```


## Update Customer

Use this endpoint to update the customer. You'll replace `{customer_id}` with the ID of the customer you would like to update.

<div class="endpoint">
    <div>
        <div class="method put">put</div>
        <div class="path">api/customers/{customer_id}</div>
    </div>
</div>

> Request

```json
{
  "general" : {
    "first_name": "[string]",
    "last_name": "[string]",
    "email": "[string]",
    "phone": "[string]",
    "address_1": "[string]",
    "address_2": "[string]",
    "country": "[string]",
    "city": "[string]",
    "pobox": "[string]",
    "company": "[string]",
    "uuid": "[string]",
    "author": "[number]"
  },
  "address": {
    "billing": {
      "first_name": "[string]",
      "last_name": "[string]",
      "email": "[string]",
      "phone": "[string]",
      "address_1": "[string]",
      "address_2": "[string]",
      "country": "[string]",
      "city": "[string]",
      "pobox": "[string]",
      "company": "[string]",
      "uuid": "[string]",
    },
    "shipping": {
      "first_name": "[string]",
      "last_name": "[string]",
      "email": "[string]",
      "phone": "[string]",
      "address_1": "[string]",
      "address_2": "[string]",
      "country": "[string]",
      "city": "[string]",
      "pobox": "[string]",
      "company": "[string]",
      "uuid": "[string]",
    }
  }
}
```

> Response

```json
{
  "status": "[success|error]",
  "message": "[string]"
}
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


## Delete Customer

Use this endpoint to delete a specific customer. Note that this might fail if the customer is still attached to orders or any other resources that enforce data integrity. Make sure to replace `{customer_id}` with the ID of the customer you would like to delete.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/customers/{customer_id}</div>
    </div>
</div>

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

> Response 

```json
{
  "status": "[success|error]",
  "message": "[string]"
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

## Customer's Address

Use this endpoint to retreive the billing and shipping address for a specific customers.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/customers/{customer_id}/addresses</div>
    </div>
</div>

> Response

```json
[
  {
    "id": 3,
    "customer_id": 1796,
    "type": "shipping",
    "email": "contact@nexopos.com",
    "first_name": "Blair",
    "last_name": null,
    "phone": null,
    "address_1": "Yaoundé, Fougerolle",
    "address_2": null,
    "country": "Cameroon",
    "city": "Yaoundé",
    "pobox": null,
    "company": null,
    "uuid": null,
    "author": 8,
    "created_at": "2025-01-31T19:46:51.000000Z",
    "updated_at": "2025-01-31T19:46:51.000000Z"
  },
  {
    "id": 4,
    "customer_id": 1796,
    "type": "billing",
    "email": "contact@nexopos.com",
    "first_name": "Blair",
    "last_name": null,
    "phone": null,
    "address_1": "Yaoundé, Fougerolle",
    "address_2": null,
    "country": "Cameroon",
    "city": "Yaoundé",
    "pobox": null,
    "company": null,
    "uuid": null,
    "author": 8,
    "created_at": "2025-01-31T19:46:51.000000Z",
    "updated_at": "2025-01-31T19:46:51.000000Z"
  }
]
```

## Customer's Group

Use this endpoint to retrieve the customer group to which a specific customer is attached. Make sure to replace `{customer_id}` with the customer ID you would like to retrieve the group.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/customers/{customer_id}/group</div>
    </div>
</div>

> Response

```json
{
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
```

## Customer's Coupons

Use this endpoint to retrieve the coupons that has been generated for a specific customer. Replace the `{customer_id}` with the ID of the customer for which you would like to retrieve the coupons.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/customers/{customer_id}/coupons</div>
    </div>
</div>

> Response

```json
[
  {
    "id": 1,
    "name": "Sample Coupon",
    "usage": 0,
    "limit_usage": 0,
    "active": true,
    "code": "578408-310141",
    "coupon_id": 1,
    "customer_id": 1796,
    "author": 8,
    "created_at": "2025-01-31T20:48:00.000000Z",
    "updated_at": "2025-01-31T20:48:00.000000Z",
    "coupon": {
      "id": 1,
      "name": "A",
      "code": "578408",
      "type": "percentage_discount",
      "discount_value": 10,
      "valid_until": "2025-01-31 20:34:04",
      "minimum_cart_value": 0,
      "maximum_cart_value": 0,
      "valid_hours_start": "2025-01-31 20:34:04",
      "valid_hours_end": "2025-01-31 20:34:04",
      "limit_usage": 0,
      "groups_id": null,
      "customers_id": null,
      "author": 8,
      "created_at": "2025-01-31T20:34:19.000000Z",
      "updated_at": "2025-01-31T20:34:19.000000Z"
    }
  }
]
```

## Customer's Reward System

Use this endpoint to retreive all the reward system the customer is assigned to. Note that reward system must first be assigned to the customers group.
You'll replace `{customer_id}` with the ID of the customer for which you woud like to get the rewards. The response is a CRUD Type reponse, which is paginated.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/customers/{customer_id}/rewards</div>
    </div>
</div>

> Response

```json
{
  "current_page": 1,
  "data": [
    {
      "id": 1,
      "customer_id": 1796,
      "reward_id": 1,
      "reward_name": "Basic",
      "points": 0,
      "target": 10,
      "created_at": "2025-01-31T20:46:48.000000Z",
      "updated_at": "2025-01-31T20:48:00.000000Z"
    }
  ],
  "first_page_url": "https://example.com/api/customers/1796/rewards?page=1",
  "from": 1,
  "last_page": 1,
  "last_page_url": "https://example.com/api/customers/1796/rewards?page=1",
  "links": [
    {
      "url": null,
      "label": "&laquo; Previous",
      "active": false
    },
    {
      "url": "https://example.com/api/customers/1796/rewards?page=1",
      "label": "1",
      "active": true
    },
    {
      "url": null,
      "label": "Next &raquo;",
      "active": false
    }
  ],
  "next_page_url": null,
  "path": "https://example.com/api/customers/1796/rewards",
  "per_page": 20,
  "prev_page_url": null,
  "to": 1,
  "total": 1
}
```

## Customer's Account History

Use this endpoint to retrieve an history of all the transactions that has occured on the customer wallet account. Replace `{customer_id}` with the ID of the customer for which you would like to retreive the account history.
Note that the response is a CRUD Type response, this means it's paginated.

<div class="endpoint">
    <div>
        <div class="method post">post</div>
        <div class="path">api/customers/{customer_id}/rewards</div>
    </div>
</div>

> Response

```json
{
  "current_page": 1,
  "data": [
    {
      "id": 1,
      "customer_id": 1796,
      "order_id": null,
      "previous_amount": 0,
      "amount": 1000,
      "next_amount": 1000,
      "operation": "add",
      "author": 8,
      "description": null,
      "created_at": "2025-01-31T20:54:19.000000Z",
      "updated_at": "2025-01-31T20:54:19.000000Z"
    }
  ],
  "first_page_url": "https://nexocloud.dev/api/customers/1796/account-history?page=1",
  "from": 1,
  "last_page": 1,
  "last_page_url": "https://nexocloud.dev/api/customers/1796/account-history?page=1",
  "links": [
    {
      "url": null,
      "label": "&laquo; Previous",
      "active": false
    },
    {
      "url": "https://nexocloud.dev/api/customers/1796/account-history?page=1",
      "label": "1",
      "active": true
    },
    {
      "url": null,
      "label": "Next &raquo;",
      "active": false
    }
  ],
  "next_page_url": null,
  "path": "https://nexocloud.dev/api/customers/1796/account-history",
  "per_page": 20,
  "prev_page_url": null,
  "to": 1,
  "total": 1
}
```

## Create Account History

Use this endpoint to create a new wallet entry for a specific customer. Make sure to replace `{customer_id}` with the ID of the customer you would like to create a new wallet entry.

<div class="endpoint">
    <div>
        <div class="method post">post</div>
        <div class="path">api/customers/{customer_id}/crud/account-history</div>
    </div>
</div>

> Request

```json
{
  "general": {
    "operation": "[add|remove]",
    "amount": "[number]",
    "description": "[string]"
  }
}
```

