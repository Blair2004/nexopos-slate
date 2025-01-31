# Customers Groups

## Create Group

Use this endpoint to create customers group.

<div class="endpoint">
    <div>
        <div class="method post">post</div>
        <div class="path">api/customers-groups</div>
    </div>
</div>

> Request

```json
{
    "name": "[string]",
    "reward_system_id": "[number]",
    "description": "[string]"
}
```

> Response

```json
{
    "status": "[success|error]",
    "message": "[string]"
}
```

## List Groups

Use this endpoint to list available customers groups. Note that here, we'll pull all customers groups, regardless of if they are assigned or not.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/customers-groups</div>
    </div>
</div>

> Response

```json
[
    {
        "id": 1,
        "name": "Reduced motivating methodology",
        "description": null,
        "reward_system_id": null,
        "minimal_credit_payment": 35,
        "author": 9,
        "uuid": null,
        "created_at": "2025-01-26T23:19:36.000000Z",
        "updated_at": "2025-01-26T23:19:36.000000Z"
    }
]
```

## Update Group

Use this endpoint to update a specific customer group. Make sure to replace `{group_id}` with the ID of the group you would like to update.

<div class="endpoint">
    <div>
        <div class="method put">put</div>
        <div class="path">api/customers-groups/{group_id}</div>
    </div>
</div>

> Request

```json
{
    "name": "[string]",
    "reward_system_id": "[number]",
    "description": "[string]"
}
```

> Response

```json
{
    "status": "[success|error]",
    "message": "[string]"
}
```

## Delete Customer Group

Use this endpoint to delete a specific customer group. Note this request might fail if the customer group is still attached to customers. Make sure to replace `{group_id}` with the ID of the customer group you would like to delete.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/customers-groups/{group_id}</div>
    </div>
</div>

> Response

```json
{
    "status": "[success|error]",
    "message": "[string]"
}
```

## Customer Group's Customers

Use this endpoint to list all cutomers that are assigned to a specific customer group. Replace `{group_id}` with the ID of the group for which you would like to retrieve the customers.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/customers-groups/{group_id}/customers</div>
    </div>
</div>

> Response

```json
[
  {
    "id": 1710,
    "username": "alysson.ferry",
    "active": 1,
    "author": 8,
    "email": "ndouglas@hotmail.com",
    "password": "$2y$10$UF1x4/8xOUUcrefMF.aINOQAPCkcujDfy/dubBXWClgtKoOBnWBDe",
    "group_id": 1,
    "first_name": "Ben",
    "last_name": "Schmitt",
    "gender": "",
    "phone": "+1-484-334-4839",
    "pobox": "40440",
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
    "created_at": "2025-01-26T23:19:36.000000Z",
    "updated_at": "2025-01-26T23:19:36.000000Z",
    "origin_store_id": null,
    "wc_customer_id": null
  }
]   
```

## Transfers Customers

Use this endpoint to move customers from one group to another group. Where `from` is the source group id and `to` is the destination group id. You can specific the IDs (in an array) that are targeted with `ids` or use a wilcard "*" to transfers all customers.

<div class="endpoint">
    <div>
        <div class="method post">post</div>
        <div class="path">api/customers-groups/transfer-customers</div>
    </div>
</div>

> Request

```json
{
    "from": "[number]",
    "to": "[number]",
    "ids": [ 1, 2, 3 ]
}
```

> Response

```json
{
    "status": "[success|error]",
    "message": "[string]"
}
```