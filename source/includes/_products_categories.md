# Products Categories

## Create Category

Use this endpoint to create a new product category.

<div class="endpoint">
    <div>
        <div class="method post">post</div>
        <div class="path">api/categories</div>
    </div>
</div>

> Request

```json
{
    "name": "[string]",
    "parent_id": "[number]",
    "displays_on_pos": "[boolean]",
    "description": "[string]",
    "media_id": "[number]"
}
```

> Response

```json
{
    "status": "[success|error]",
    "message": "[string]",
    "data": {
        "category": {
            "id": 1,
            "name": "Condiments",
            "parent_id": null,
            "media_id": 0,
            "preview_url": "https://exmaple.com/image.jpg",
            "displays_on_pos": 1,
            "total_items": 13,
            "description": "Additional condiments that can be added to meals",
            "author": 8,
            "uuid": null,
            "created_at": "2025-01-26T23:19:42.000000Z",
            "updated_at": "2025-01-26T23:19:45.000000Z"
        }
    }
}
```

## Single Category

Use this endpoint to retrieve a single category. You'll replace `{category_id}` by the actual category you would like to get.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/categories/{category_id}</div>
    </div>
</div>

> Response

```json
{
    "id": 1,
    "name": "Condiments",
    "parent_id": null,
    "media_id": 0,
    "preview_url": "https://exmaple.com/image.jpg",
    "displays_on_pos": 1,
    "total_items": 13,
    "description": "Additional condiments that can be added to meals",
    "author": 8,
    "uuid": null,
    "created_at": "2025-01-26T23:19:42.000000Z",
    "updated_at": "2025-01-26T23:19:45.000000Z"
}
```

## Get Categories

Use this endpoint to retrieve all defined product categories.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/categories</div>
    </div>
</div>

> Response

```json
[
  {
    "id": 1,
    "name": "Condiments",
    "parent_id": null,
    "media_id": 0,
    "preview_url": "https://exmaple.com/image.jpg",
    "displays_on_pos": 1,
    "total_items": 13,
    "description": "Additional condiments that can be added to meals",
    "author": 8,
    "uuid": null,
    "created_at": "2025-01-26T23:19:42.000000Z",
    "updated_at": "2025-01-26T23:19:45.000000Z"
  }
]
```

## Update Category

Use this endpoint to update an existing category using `{category_id}`, that needs to be replaced with the actual ID of the category you would like to udpate.

<div class="endpoint">
    <div>
        <div class="method put">put</div>
        <div class="path">api/categories/{category_id}</div>
    </div>
</div>

> Request

```json
{
    "name": "[string]",
    "parent_id": "[number]",
    "displays_on_pos": "[boolean]",
    "description": "[string]",
    "media_id": "[number]"
}
```

> Response

```json
{
    "status": "[success|error]",
    "message": "[string]",
    "data": {
        "category": {
            "id": 1,
            "name": "Condiments",
            "parent_id": null,
            "media_id": 0,
            "preview_url": "https://exmaple.com/image.jpg",
            "displays_on_pos": 1,
            "total_items": 13,
            "description": "Additional condiments that can be added to meals",
            "author": 8,
            "uuid": null,
            "created_at": "2025-01-26T23:19:42.000000Z",
            "updated_at": "2025-01-26T23:19:45.000000Z"
        }
    }
}
```

## Delete Category

Use this endpoint to delete an existing category. Note that you might encounter an error if the category is still assigned to product. You'll replace `{category_id}` with the ID of the category you would like to delete.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/categories/{category_id}</div>
    </div>
</div>

> Response

```json
{
    "status": "[success|error]",
    "message": "[string]"
}
```

## Category's Products

Use this endpoint to retreive all the product that are assigned to a category. You'll replace `{category_id}` by the ID of the category you would like to get the products.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/categories/{category_id}/products</div>
    </div>
</div>

> Response

```json
[
  {
    "id": 1,
    "name": "Creamer Packet",
    "tax_type": "inclusive",
    "tax_group_id": 1,
    "tax_value": 0,
    "product_type": "product",
    "type": "dematerialized",
    "accurate_tracking": false,
    "auto_cogs": false,
    "status": "available",
    "stock_management": "disabled",
    "barcode": "2897183678939",
    "barcode_type": "ean13",
    "sku": "nwPUboV8ML3oVUW",
    "description": "Created via tests",
    "thumbnail_id": null,
    "category_id": 1,
    "parent_id": 0,
    "unit_group": 1,
    "on_expiration": "prevent_sales",
    "expires": 0,
    "searchable": 1,
    "author": 8,
    "uuid": null,
    "created_at": "2025-01-26T23:19:42.000000Z",
    "updated_at": "2025-01-26T23:19:42.000000Z"
  }
]
```