# Medias

The medias endpoint helps interacting with the media library.

## Upload Media

You'll use this endpoint to upload a media file to the library.

<div class="endpoint">
    <div>
        <div class="method post">post</div>
        <div class="path">api/medias</div>
    </div>
</div>

<aside class="notice">You're restricted to upload only supported mimes. With the use of the filter `ns.mimes.types` you can add more mimes.</aside>

> Request

```json
{
    "file": "[binary]"
}
```

> Response

```json
{
    "status": "[error|success]",
    "message": "[string]"
}
```

## List Medias

Use this endpoint to get a paginated list of medias. You can navigate through page by adding the query `?page=x`, where "x" is the page you would like to load.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/medias</div>
    </div>
</div>


> Response

```json
{
  "current_page": 1,
  "data": [
    {
      "id": 1,
      "name": "capture-decran-2024-12-13-152535",
      "extension": "png",
      "slug": "2025/02/capture-decran-2024-12-13-152535",
      "user_id": 8,
      "created_at": "2025-02-06 11:40:55",
      "updated_at": "2025-02-06 11:40:55",
      "sizes": {
        "original": "https://example.com/storage/2025/02/capture-decran-2024-12-13-152535.png",
        "thumb": "https://example.com/storage/2025/02/capture-decran-2024-12-13-152535-thumb.png"
      },
      "user": {
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
        "total_sales_count": 68,
        "total_sales": 7207.9,
        "birth_date": null,
        "purchases_amount": 0,
        "owed_amount": 0,
        "credit_limit_amount": 0,
        "account_amount": 0,
        "activation_token": null,
        "created_at": "2025-01-13T22:52:01.000000Z",
        "updated_at": "2025-02-03T20:32:58.000000Z",
        "origin_store_id": null,
        "wc_customer_id": null
      }
    }
  ],
  "first_page_url": "https://example.com/api/medias?page=1",
  "from": 1,
  "last_page": 1,
  "last_page_url": "https://example.com/api/medias?page=1",
  "links": [
    {
      "url": null,
      "label": "&laquo; Previous",
      "active": false
    },
    {
      "url": "https://example.com/api/medias?page=1",
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
  "path": "https://example.com/api/medias",
  "per_page": 20,
  "prev_page_url": null,
  "to": 1,
  "total": 1
}
```

## Update Media

This update allow updating the name of a media. It can't be used to replace the previously uploaded image. Make sure to replace `{id}` with the actual media ID.

<div class="endpoint">
    <div>
        <div class="method put">put</div>
        <div class="path">api/medias/{id}</div>
    </div>
</div>


> Request

```json
{
    "name": "[string]"
}
```

> Response

```json
{
    "status": "[error|success]",
    "message": "[string]"
}
```

## Delete Media

Use this endpoint to delete an existing media. You'll replace `{id}` with the ID of the media you would like to delete.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/medias/{id}</div>
    </div>
</div>

> Response

```json
{
    "status": "[error|success]",
    "message": "[string]"
}
```

## Bulk Delete Medias

Use this endpoint to bulk-delete your medias. This requires `ids` to be provided and to be an array of media's ID.

<div class="endpoint">
    <div>
        <div class="method post">post</div>
        <div class="path">api/medias/bulk-delete</div>
    </div>
</div>

> Request

```json
{
    "ids": []
}
```

> Response

```json
{
    "status": "[error|success]",
    "message": "[string]"
}
```