# User

The user endpoint give an overview of the logged user. With this you'll be able to retreive the logged user email, id and more (The password is encrypted).

<div class="endpoint">
    <div>
        <div class="method get">GET</div>
        <div class="path">api/user</div>
    </div>
</div>

> Response

```json
{
  "id": 8,
  "username": "admin",
  "active": true,
  "author": 8,
  "email": "contact@nexopos.com",
  "group_id": null,
  "first_name": null,
  "last_name": null,
  "gender": null,
  "phone": null,
  "pobox": null,
  "activation_expiration": null,
  "total_sales_count": 45,
  "total_sales": 4805.85,
  "birth_date": null,
  "purchases_amount": 0,
  "owed_amount": 0,
  "credit_limit_amount": 0,
  "account_amount": 0,
  "activation_token": null,
  "created_at": "2025-01-13T22:52:01.000000Z",
  "updated_at": "2025-01-27T09:42:33.000000Z",
  "origin_store_id": null,
  "wc_customer_id": null
}
```