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
    "status": "[success|error|info|warning]",
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
        <div class="method put">put</div>
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
        <div class="method get">get</div>
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
        <div class="method get">get</div>
        <div class="path">api/products/{product_id}/units</div>
    </div>
</div>

> Response

```json
[
  {
    "id": 4,
    "product_id": 2,
    "type": "product",
    "preview_url": "https://nexocloud.dev/modules/nsgastro/images/categories/condiments/sugar-packet.jpeg",
    "expiration_date": null,
    "unit_id": 1,
    "barcode": "3962888485645-4",
    "quantity": 0,
    "low_quantity": 0,
    "stock_alert_enabled": 0,
    "sale_price": 0,
    "sale_price_edit": 0,
    "sale_price_without_tax": 0,
    "sale_price_with_tax": 0,
    "sale_price_tax": 0,
    "wholesale_price": 0,
    "wholesale_price_edit": 0,
    "wholesale_price_with_tax": 0,
    "wholesale_price_without_tax": 0,
    "wholesale_price_tax": 0,
    "custom_price": 0,
    "custom_price_edit": 0,
    "custom_price_with_tax": 0,
    "custom_price_without_tax": 0,
    "custom_price_tax": 0,
    "visible": 1,
    "convert_unit_id": null,
    "cogs": 0,
    "uuid": null,
    "created_at": "2025-01-26T23:19:42.000000Z",
    "updated_at": "2025-01-26T23:19:42.000000Z",
    "unit": {
      "id": 1,
      "name": "Piece",
      "identifier": "piece",
      "description": "",
      "author": 8,
      "group_id": 1,
      "value": 1,
      "preview_url": "",
      "base_unit": true,
      "uuid": null,
      "created_at": "2025-01-26T23:19:36.000000Z",
      "updated_at": "2025-01-26T23:19:42.000000Z"
    }
  },
  {
    "id": 5,
    "product_id": 2,
    "type": "product",
    "preview_url": "https://nexocloud.dev/modules/nsgastro/images/categories/condiments/sugar-packet.jpeg",
    "expiration_date": null,
    "unit_id": 2,
    "barcode": "3962888485645-5",
    "quantity": 0,
    "low_quantity": 0,
    "stock_alert_enabled": 0,
    "sale_price": 0,
    "sale_price_edit": 0,
    "sale_price_without_tax": 0,
    "sale_price_with_tax": 0,
    "sale_price_tax": 0,
    "wholesale_price": 0,
    "wholesale_price_edit": 0,
    "wholesale_price_with_tax": 0,
    "wholesale_price_without_tax": 0,
    "wholesale_price_tax": 0,
    "custom_price": 0,
    "custom_price_edit": 0,
    "custom_price_with_tax": 0,
    "custom_price_without_tax": 0,
    "custom_price_tax": 0,
    "visible": 1,
    "convert_unit_id": null,
    "cogs": 0,
    "uuid": null,
    "created_at": "2025-01-26T23:19:42.000000Z",
    "updated_at": "2025-01-26T23:19:42.000000Z",
    "unit": {
      "id": 2,
      "name": "Small Box",
      "identifier": "small-box",
      "description": "",
      "author": 8,
      "group_id": 1,
      "value": 6,
      "preview_url": null,
      "base_unit": true,
      "uuid": null,
      "created_at": "2025-01-26T23:19:36.000000Z",
      "updated_at": "2025-01-26T23:19:36.000000Z"
    }
  },
  {
    "id": 6,
    "product_id": 2,
    "type": "product",
    "preview_url": "https://nexocloud.dev/modules/nsgastro/images/categories/condiments/sugar-packet.jpeg",
    "expiration_date": null,
    "unit_id": 3,
    "barcode": "3962888485645-6",
    "quantity": 0,
    "low_quantity": 0,
    "stock_alert_enabled": 0,
    "sale_price": 0,
    "sale_price_edit": 0,
    "sale_price_without_tax": 0,
    "sale_price_with_tax": 0,
    "sale_price_tax": 0,
    "wholesale_price": 0,
    "wholesale_price_edit": 0,
    "wholesale_price_with_tax": 0,
    "wholesale_price_without_tax": 0,
    "wholesale_price_tax": 0,
    "custom_price": 0,
    "custom_price_edit": 0,
    "custom_price_with_tax": 0,
    "custom_price_without_tax": 0,
    "custom_price_tax": 0,
    "visible": 1,
    "convert_unit_id": null,
    "cogs": 0,
    "uuid": null,
    "created_at": "2025-01-26T23:19:42.000000Z",
    "updated_at": "2025-01-26T23:19:42.000000Z",
    "unit": {
      "id": 3,
      "name": "Box",
      "identifier": "box",
      "description": "",
      "author": 8,
      "group_id": 1,
      "value": 12,
      "preview_url": null,
      "base_unit": true,
      "uuid": null,
      "created_at": "2025-01-26T23:19:36.000000Z",
      "updated_at": "2025-01-26T23:19:36.000000Z"
    }
  }
]
```

## Product Unit Quantity
You'll use this endpoint to retreive a single product unit quantity. You'll replace "{product_id}" and "{unit_id}" by their relevant values.


<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/products/{product_id}/units/{unit_id}/quantity</div>
    </div>
</div>

> Response

```json
{
  "id": 4,
  "product_id": 2,
  "type": "product",
  "preview_url": "https://nexocloud.dev/modules/nsgastro/images/categories/condiments/sugar-packet.jpeg",
  "expiration_date": null,
  "unit_id": 1,
  "barcode": "3962888485645-4",
  "quantity": 0,
  "low_quantity": 0,
  "stock_alert_enabled": 0,
  "sale_price": 0,
  "sale_price_edit": 0,
  "sale_price_without_tax": 0,
  "sale_price_with_tax": 0,
  "sale_price_tax": 0,
  "wholesale_price": 0,
  "wholesale_price_edit": 0,
  "wholesale_price_with_tax": 0,
  "wholesale_price_without_tax": 0,
  "wholesale_price_tax": 0,
  "custom_price": 0,
  "custom_price_edit": 0,
  "custom_price_with_tax": 0,
  "custom_price_without_tax": 0,
  "custom_price_tax": 0,
  "visible": 1,
  "convert_unit_id": null,
  "cogs": 0,
  "uuid": null,
  "created_at": "2025-01-26T23:19:42.000000Z",
  "updated_at": "2025-01-26T23:19:42.000000Z",
}
```

## Product Procurements
Use this endpoint to retreive all purchases that was made for a specific product.


<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/products/{product_id}/procurements</div>
    </div>
</div>

> Response

```json
[
  {
    "id": 7,
    "name": "Basil leaves",
    "gross_purchase_price": 1.23,
    "net_purchase_price": 1.23,
    "procurement_id": 4,
    "product_id": 124,
    "purchase_price": 1.23,
    "quantity": 5,
    "available_quantity": 5,
    "tax_group_id": 0,
    "barcode": "RFYAd3rApW-007-007",
    "expiration_date": null,
    "tax_type": "inclusive",
    "tax_value": 0,
    "total_purchase_price": 6.15,
    "unit_id": 7,
    "convert_unit_id": null,
    "author": 8,
    "uuid": null,
    "created_at": "2025-01-29T12:54:06.000000Z",
    "updated_at": "2025-01-29T12:54:06.000000Z",
    "procurement": {
      "name": "00004"
    }
  }
]
```

## Product: Barcode Search
Use this to have perform a strict retreival of product having as barcode the provided term. This endpoint is used on the POS to get product using a Barcode reader. You'll replace "{barcode}" with the barcode you would like to use as search term.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/products/search/using-barcode/{barcode}</div>
    </div>
</div>

> Response

```json
{
  "type": "product",
  "product": {
    "id": 2,
    "name": "Sugar Packet",
    "tax_type": "inclusive",
    "tax_group_id": 1,
    "tax_value": 0,
    "product_type": "product",
    "type": "dematerialized",
    "accurate_tracking": false,
    "auto_cogs": false,
    "status": "available",
    "stock_management": "disabled",
    "barcode": "3962888485645",
    "barcode_type": "ean13",
    "sku": "q3sKTj7sdfGD3Qt",
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
    "unit_quantities": [
      {
        "id": 4,
        "product_id": 2,
        "type": "product",
        "preview_url": "https://nexocloud.dev/modules/nsgastro/images/categories/condiments/sugar-packet.jpeg",
        "expiration_date": null,
        "unit_id": 1,
        "barcode": "3962888485645-4",
        "quantity": 0,
        "low_quantity": 0,
        "stock_alert_enabled": 0,
        "sale_price": 0,
        "sale_price_edit": 0,
        "sale_price_without_tax": 0,
        "sale_price_with_tax": 0,
        "sale_price_tax": 0,
        "wholesale_price": 0,
        "wholesale_price_edit": 0,
        "wholesale_price_with_tax": 0,
        "wholesale_price_without_tax": 0,
        "wholesale_price_tax": 0,
        "custom_price": 0,
        "custom_price_edit": 0,
        "custom_price_with_tax": 0,
        "custom_price_without_tax": 0,
        "custom_price_tax": 0,
        "visible": 1,
        "convert_unit_id": null,
        "cogs": 0,
        "uuid": null,
        "created_at": "2025-01-26T23:19:42.000000Z",
        "updated_at": "2025-01-26T23:19:42.000000Z",
        "unit": {
          "id": 1,
          "name": "Piece",
          "identifier": "piece",
          "description": "",
          "author": 8,
          "group_id": 1,
          "value": 1,
          "preview_url": "",
          "base_unit": true,
          "uuid": null,
          "created_at": "2025-01-26T23:19:36.000000Z",
          "updated_at": "2025-01-26T23:19:42.000000Z"
        }
      },
      {
        "id": 5,
        "product_id": 2,
        "type": "product",
        "preview_url": "https://nexocloud.dev/modules/nsgastro/images/categories/condiments/sugar-packet.jpeg",
        "expiration_date": null,
        "unit_id": 2,
        "barcode": "3962888485645-5",
        "quantity": 0,
        "low_quantity": 0,
        "stock_alert_enabled": 0,
        "sale_price": 0,
        "sale_price_edit": 0,
        "sale_price_without_tax": 0,
        "sale_price_with_tax": 0,
        "sale_price_tax": 0,
        "wholesale_price": 0,
        "wholesale_price_edit": 0,
        "wholesale_price_with_tax": 0,
        "wholesale_price_without_tax": 0,
        "wholesale_price_tax": 0,
        "custom_price": 0,
        "custom_price_edit": 0,
        "custom_price_with_tax": 0,
        "custom_price_without_tax": 0,
        "custom_price_tax": 0,
        "visible": 1,
        "convert_unit_id": null,
        "cogs": 0,
        "uuid": null,
        "created_at": "2025-01-26T23:19:42.000000Z",
        "updated_at": "2025-01-26T23:19:42.000000Z",
        "unit": {
          "id": 2,
          "name": "Small Box",
          "identifier": "small-box",
          "description": "",
          "author": 8,
          "group_id": 1,
          "value": 6,
          "preview_url": null,
          "base_unit": true,
          "uuid": null,
          "created_at": "2025-01-26T23:19:36.000000Z",
          "updated_at": "2025-01-26T23:19:36.000000Z"
        }
      },
      {
        "id": 6,
        "product_id": 2,
        "type": "product",
        "preview_url": "https://nexocloud.dev/modules/nsgastro/images/categories/condiments/sugar-packet.jpeg",
        "expiration_date": null,
        "unit_id": 3,
        "barcode": "3962888485645-6",
        "quantity": 0,
        "low_quantity": 0,
        "stock_alert_enabled": 0,
        "sale_price": 0,
        "sale_price_edit": 0,
        "sale_price_without_tax": 0,
        "sale_price_with_tax": 0,
        "sale_price_tax": 0,
        "wholesale_price": 0,
        "wholesale_price_edit": 0,
        "wholesale_price_with_tax": 0,
        "wholesale_price_without_tax": 0,
        "wholesale_price_tax": 0,
        "custom_price": 0,
        "custom_price_edit": 0,
        "custom_price_with_tax": 0,
        "custom_price_without_tax": 0,
        "custom_price_tax": 0,
        "visible": 1,
        "convert_unit_id": null,
        "cogs": 0,
        "uuid": null,
        "created_at": "2025-01-26T23:19:42.000000Z",
        "updated_at": "2025-01-26T23:19:42.000000Z",
        "unit": {
          "id": 3,
          "name": "Box",
          "identifier": "box",
          "description": "",
          "author": 8,
          "group_id": 1,
          "value": 12,
          "preview_url": null,
          "base_unit": true,
          "uuid": null,
          "created_at": "2025-01-26T23:19:36.000000Z",
          "updated_at": "2025-01-26T23:19:36.000000Z"
        }
      }
    ],
    "tax_group": {
      "id": 1,
      "name": "GST",
      "description": null,
      "author": 8,
      "uuid": null,
      "created_at": "2025-01-26T23:19:42.000000Z",
      "updated_at": "2025-01-26T23:19:42.000000Z",
      "taxes": [
        {
          "id": 1,
          "name": "SGST",
          "description": null,
          "rate": 8,
          "tax_group_id": 1,
          "author": 8,
          "uuid": null,
          "created_at": "2025-01-26T23:19:42.000000Z",
          "updated_at": "2025-01-26T23:19:42.000000Z"
        },
        {
          "id": 2,
          "name": "CGST",
          "description": null,
          "rate": 8,
          "tax_group_id": 1,
          "author": 8,
          "uuid": null,
          "created_at": "2025-01-26T23:19:42.000000Z",
          "updated_at": "2025-01-26T23:19:42.000000Z"
        }
      ]
    }
  }
}
```

## Product: Search Using Term
Use this endpoint to search product using a term. As a response you'll have an array of possible product matching the term provided. You might also use additional argument to circumscribe more your search using the entry "arguments" which is optional.

<div class="endpoint">
    <div>
        <div class="method post">post</div>
        <div class="path">api/products/search</div>
    </div>
</div>

> Request

```json
{
    "search": "iPhone 16",
    "arguments": {
        "updated_at": {
            "comparison": "like",
            "value": "2024-12-12"
        }
    }
}
```

## Delete Unit Quantity
Use this to delete a unit quantity attached to a product. This implies all the inventory assigned to that product using the selected unit, will also be deleted (and can't be retreived). You'll replace "{unit_quantity_id}" with the id you would like to delete.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/products/units/quantity/{unit_quantity_id}</div>
    </div>
</div>

> Response

```json
{
    "status": "[success|error]",
    "message": "[string]"
}
```

## Delete All Products
Use this to remove all products created so far. Depending on your products, you might need to increase the PHP Execution time as this will not only clear products but all related tables.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/products</div>
    </div>
</div>

> Response

```json
{
    "status": "[success|error]",
    "message": "[string]"
}
```