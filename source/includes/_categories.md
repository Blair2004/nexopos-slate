# Categories

Use these endpoint to interact with the products categories.

## Get Categories

This endpoint will returns a not paginated array of categories. You might use the CRUD approach to get a paginated list of categories.

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
        "preview_url": "https://example.com/modules/nsgastro/images/categories/condiments/creamer-packet.jpeg",
        "displays_on_pos": 1,
        "total_items": 13,
        "description": "Additional condiments that can be added to meals",
        "author": 8,
        "uuid": null,
        "created_at": "2025-02-08T12:55:26.000000Z",
        "updated_at": "2025-02-08T12:55:32.000000Z",
    },
]
```

You might want to retrieve the categories that belongs to a parent category using the query argument `?parent={id}` where `{id}` is the identifier of the parent category.

## Get Single Category

Use this endpoint to retrieve a single category using his ID. Replace `{id}` with the actual ID of the category.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/categories/{id}</div>
    </div>
</div>

> Response

```json
{
    "id": 1,
    "name": "Condiments",
    "parent_id": null,
    "media_id": 0,
    "preview_url": "https://example.com/modules/nsgastro/images/categories/condiments/creamer-packet.jpeg",
    "displays_on_pos": 1,
    "total_items": 13,
    "description": "Additional condiments that can be added to meals",
    "author": 8,
    "uuid": null,
    "created_at": "2025-02-08T12:55:26.000000Z",
    "updated_at": "2025-02-08T12:55:32.000000Z",
}
```

## Get Category Products

Use this endpoint to get all products that are assigned to the category. Replace `{id}` with the actual ID of the category.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/categories/{id}/products</div>
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
        "barcode": "8795063144717",
        "barcode_type": "ean13",
        "sku": "Sb4X001sJ1u8i7K",
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
        "created_at": "2025-02-08T12:55:26.000000Z",
        "updated_at": "2025-02-08T12:55:26.000000Z"
    }
]
```

## Create Category

Use this endpoint to create a product category

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
    "parent_id": "[integer]", // optional
    "description": "[string]",
    "media_id": "[url]"
}
```

> Response

```json
{
    "status": "success",
    "message": "The category has been correctly saved",
    "data": {
        "category": {
            "name": "FooBar",
            "description": "For API purpose.",
            "author": 8,
            "updated_at": "2025-02-13T08:32:23.000000Z",
            "created_at": "2025-02-13T08:32:23.000000Z",
            "id": 11
        }
    }
}
```

## Update Category

Use this to update an existing category using his ID `{id}`.

<div class="endpoint">
    <div>
        <div class="method put">put</div>
        <div class="path">api/categories/{id}</div>
    </div>
</div>

> Request

```json
{
    "name": "[string]",
    "parent_id": "[integer]", // optional
    "description": "[string]",
    "media_id": "[url]"
}
```

> Response

```json
{
    "status": "success",
    "message": "The category has been updated",
    "data": {
        "category": {
            "name": "FooBar",
            "description": "For API purpose.",
            "author": 8,
            "updated_at": "2025-02-13T08:32:23.000000Z",
            "created_at": "2025-02-13T08:32:23.000000Z",
            "id": 11
        }
    }
}
```

## Delete A Category

Use this endpoint to delete a category using his ID. Replace `{id}` with the actual ID of the category. If the category doesn't exist, the proceed might fail with a fail response.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/categories/{id}</div>
    </div>
</div>

> Response

```json
{
    "status": "[success|error]",
    "message": "[string]"
}
```

## Category Exploration

Use this endpoint to explore category as exploring folder in computing. At the root of each category, is no other category exists, the products are displayed. The products of intermediary categories aren't visible. 

If `{id}` is not provided, all parent categories are displayed first. If `{id}` is provided, all it's child categories are listed. If no child categories exists, the products are retrieved.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/categories/pos/{id?}</div>
    </div>
</div>

> Response with Parent Category

```json
{
    "products": [],
    "previousCategory": false,
    "currentCategory": false,
    "categories": [
        {
            "id": 1,
            "name": "Condiments",
            "parent_id": null,
            "media_id": 0,
            "preview_url": "https://example.com/modules/nsgastro/images/categories/condiments/creamer-packet.jpeg",
            "displays_on_pos": 1,
            "total_items": 13,
            "description": "Additional condiments that can be added to meals",
            "author": 8,
            "uuid": null,
            "created_at": "2025-02-08T12:55:26.000000Z",
            "updated_at": "2025-02-08T12:55:32.000000Z",
            "wc_category_id": null
        }
    ]
}
```

> Response with Products

```json
{
  "products": [
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
      "barcode": "8795063144717",
      "barcode_type": "ean13",
      "sku": "Sb4X001sJ1u8i7K",
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
      "created_at": "2025-02-08T12:55:26.000000Z",
      "updated_at": "2025-02-08T12:55:26.000000Z",
      "galleries": [
        {
          "id": 1,
          "name": null,
          "product_id": 1,
          "media_id": null,
          "url": "https://example.com/modules/nsgastro/images/categories/condiments/creamer-packet.jpeg",
          "order": 0,
          "featured": true,
          "author": 8,
          "uuid": null,
          "created_at": "2025-02-08T12:55:26.000000Z",
          "updated_at": "2025-02-08T12:55:26.000000Z"
        }
      ],
      "tax_group": {
        "id": 1,
        "name": "GST",
        "description": null,
        "author": 8,
        "uuid": null,
        "created_at": "2025-02-08T12:55:26.000000Z",
        "updated_at": "2025-02-08T12:55:26.000000Z",
        "taxes": [
          {
            "id": 1,
            "name": "SGST",
            "description": null,
            "rate": 8,
            "tax_group_id": 1,
            "author": 8,
            "uuid": null,
            "created_at": "2025-02-08T12:55:26.000000Z",
            "updated_at": "2025-02-08T12:55:26.000000Z"
          },
          {
            "id": 2,
            "name": "CGST",
            "description": null,
            "rate": 8,
            "tax_group_id": 1,
            "author": 8,
            "uuid": null,
            "created_at": "2025-02-08T12:55:26.000000Z",
            "updated_at": "2025-02-08T12:55:26.000000Z"
          }
        ]
      }
    }
  ],
  "categories": [],
  "previousCategory": null,
  "currentCategory": {
    "id": 1,
    "name": "Condiments",
    "parent_id": null,
    "media_id": 0,
    "preview_url": "https://example.com/modules/nsgastro/images/categories/condiments/creamer-packet.jpeg",
    "displays_on_pos": 1,
    "total_items": 13,
    "description": "Additional condiments that can be added to meals",
    "author": 8,
    "uuid": null,
    "created_at": "2025-02-08T12:55:26.000000Z",
    "updated_at": "2025-02-08T12:55:32.000000Z",
    "sub_categories": []
  }
}
```