# Products

## Retreiving Products

<div class="endpoint">
    <div>
        <div class="method get">GET</div>
        <div class="path">api/products</div>
    </div>
</div>

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
    "updated_at": "2025-01-26T23:19:42.000000Z",
  }
]
```

This endpoing will list all products available. However, it won't include any other related table (for the sake of performance).

## Create Product

<div class="endpoint">
    <div>
        <div class="method post">POST</div>
        <div class="path">api/products</div>
    </div>
</div>

Will create a product using the provided data structure.

> Request

```json
{
    "name": "[name]",
    "variations": [
        {
            "identification": {
                "category_id": 1,
                "barcode": "[barcode]",
                "sku": "[string]",
                "barcode_type": "[ean8|ean13|codabar|code128|code39|code11|upca|upce]",
                "type": "materialized",
                "status": "[available|unavailable]",
                "author": "[id]",
                "stock_management": "[enable|disabled]"
            },
            "units": {
                "unit_group_id": "[number]",
                "accurate_tracking": "[boolean]",
                "auto_cogs": "[boolean]",
                "selling_group": [
                    {
                        "unit_id": 1,
                        "sale_price": "[number]",
                        "wholesale_price": "[number]",
                        "cogs": "[number]",
                        "stock_alert": "[boolean]",
                        "convert_unit": "[unit_id]",
                        "visible": "[boolean]",
                        "low_quantity": "[number]",
                        "preview_url": "[url]"
                    }
                ]
            },
            "expiry": {
                "on_expiration": "[allow_sales|prevent_sales]",
                "expires": "[boolean]"
            },
            "taxes": {
                "tax_group_id": "[number]",
                "tax_type": "[inclusive|exclusive]"
            },
            "images": [
                {
                    "featured": "[boolean]",
                    "url": "[url]"
                }
            ],
        }
    ]
}
```

> Response

```json
{
    "status": "[success|failure|info|warning]",
    "message": "[string]",
    "data": {
        "product": {
            // created product
        },
        "editUrl": "[url]"
    }
}
```

## Retreive Product
This wil retreive a product using it's ID. You'll make sure to replace "{product_id}" with the actual product ID.

<div class="endpoint">
    <div>
        <div class="method get">GET</div>
        <div class="path">api/products/{product_id}</div>
    </div>
</div>

> Response

```json
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
  "updated_at": "2025-01-26T23:19:42.000000Z",
}
```

## Update Product

<div class="endpoint">
    <div>
        <div class="method post">POST</div>
        <div class="path">api/products/{product_id}</div>
    </div>
</div>

> Request

```json
{
    "name": "[name]",
    "variations": [
        {
            "identification": {
                "category_id": 1,
                "barcode": "[barcode]",
                "sku": "[string]",
                "barcode_type": "[ean8|ean13|codabar|code128|code39|code11|upca|upce]",
                "type": "materialized",
                "status": "[available|unavailable]",
                "author": "[id]",
                "stock_management": "[enable|disabled]"
            },
            "units": {
                "unit_group_id": "[number]",
                "accurate_tracking": "[boolean]",
                "auto_cogs": "[boolean]",
                "selling_group": [
                    {
                        "unit_id": 1,
                        "sale_price": "[number]",
                        "wholesale_price": "[number]",
                        "cogs": "[number]",
                        "stock_alert": "[boolean]",
                        "convert_unit": "[unit_id]",
                        "visible": "[boolean]",
                        "low_quantity": "[number]",
                        "preview_url": "[url]"
                    }
                ]
            },
            "expiry": {
                "on_expiration": "[allow_sales|prevent_sales]",
                "expires": "[boolean]"
            },
            "taxes": {
                "tax_group_id": "[number]",
                "tax_type": "[inclusive|exclusive]"
            },
            "images": [
                {
                    "featured": "[boolean]",
                    "url": "[url]"
                }
            ],
        }
    ]
}
```

> Response

```json
{
    "status": "[success|failure|info|warning]",
    "message": "[string]",
    "data": {
        "product": {
            // updated product
        },
        "editUrl": "[url]"
    }
}
```

You'll use this endpoint to update an existing product. You'll replace "{product_id}" by the actual id of the product you would like to update.

## Delete Product

You'll use this to delete a product with all it's related tables. This endpoint is proctected by a permission check. You might also get an error if the product is [currently used](https://my.nexopos.com/en/documentation/module-development/models-dependency).

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/products/{product_id}</div>
    </div>
</div>

> Response

```json
{
    "status": "[success|error]",
    "message": "[string]"
}
```

## Get Product Variations

While this feature is not yet fully used on NexoPOS as a single variation is enforced for now, you can use it in the future to retreive products variations.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/products/{product_id}/variations</div>
    </div>
</div>

```json
[]
```

## Reset Product
Use this to erase the product inventory. This will be used to have a fresh start with the product. Requires to have the privilege for editing products.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/products/{product_id}/reset</div>
    </div>
</div>

```json
{
  "status": "success",
  "message": "The product has been reset.",
  "data": {
    "product": {
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
      "updated_at": "2025-01-26T23:19:42.000000Z",
    }
  }
}
```

## Product Units
Used to retreive all units attached to a products.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/products/{product_id}/variations</div>
    </div>
</div>