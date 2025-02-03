# Crud

CRUD which stands for "Create Read Update Delete" is an acronym mostly used to define a feature that allows interacting with data. NexoPOS comes with a built-in CRUD feature that is widely used through the following API.

For further instruction how how to interact with the Crud API, [refer to the documentation](https://my.nexopos.com/en/documentation/crud-api/how-to-create-a-crud-component).


<aside class="notice">
On this part of the documentation, `{namespace}` refer the identifier of a CRUD instance. You'll then use the identifier of the CRUd you would like to retrieve entreis. For this documentation, we'll use the identifier `ns.products` which is for the `App\Crud\ProductCrud` component.
</aside>

## Get Table Entries

Use this endpoint to retreive the configuration of a table. By table we mean that UI component that is used to displays a list of entries.

<div class="endpoint">
    <div>
        <div class="method post">post</div>
        <div class="path">api/crud/{namespace}</div>
    </div>
</div>

> Response

```json
{
  "current_page": 1,
  "data": [
    {
      "id": 95,
      "name": "Spaghetti Carbonara",
      "tax_type": "inclusive",
      "tax_group_id": 1,
      "tax_value": 0,
      "product_type": "product",
      "type": "<strong class=\"text-info-tertiary \">Dematerialized Product</strong>",
      "accurate_tracking": 0,
      "auto_cogs": 0,
      "status": "Available",
      "stock_management": "Enabled",
      "barcode": "8408756723372",
      "barcode_type": "ean13",
      "sku": "im5sDd0r2tIhrR6",
      "description": "Created via tests",
      "thumbnail_id": null,
      "category_id": 9,
      "parent_id": 0,
      "unit_group": 1,
      "on_expiration": "prevent_sales",
      "expires": 0,
      "searchable": 1,
      "author": 8,
      "uuid": null,
      "created_at": "2025-02-02 09:33:08",
      "updated_at": "2025-02-02 09:43:07",
      "user_username": "admin",
      "category_name": "Pastas",
      "parent_name": null,
      "taxes_groups_id": 1,
      "taxes_groups_name": "GST",
      "taxes_groups_description": null,
      "taxes_groups_author": 8,
      "taxes_groups_uuid": null,
      "taxes_groups_created_at": "2025-02-02 09:32:48",
      "taxes_groups_updated_at": "2025-02-02 09:32:48",
      "$checked": false,
      "$toggled": false,
      "$id": 95,
      "rawType": "dematerialized",
      "rawStockManagement": "enabled",
      "$actions": {
        "edit": {
          "label": "<i class=\"mr-2 las la-edit\"></i> Edit",
          "identifier": "edit",
          "url": "https://example.com/dashboard/products/edit/95",
          "confirm": null,
          "type": "GOTO",
          "permissions": []
        },
        "ns.quantities": {
          "label": "<i class=\"mr-2 las la-eye\"></i> Preview",
          "identifier": "ns.quantities",
          "url": "https://example.com/dashboard/products/edit/95",
          "confirm": null,
          "type": "POPUP",
          "permissions": []
        },
        "units": {
          "label": "<i class=\"mr-2 las la-balance-scale-left\"></i> See Quantities",
          "identifier": "units",
          "url": "https://example.com/dashboard/products/95/units",
          "confirm": null,
          "type": "GOTO",
          "permissions": []
        },
        "history": {
          "label": "<i class=\"mr-2 las la-history\"></i> See History",
          "identifier": "history",
          "url": "https://example.com/dashboard/products/95/history",
          "confirm": null,
          "type": "GOTO",
          "permissions": []
        },
        "delete": {
          "label": "<i class=\"mr-2 las la-trash\"></i> Delete",
          "identifier": "delete",
          "url": "https://example.com/api/crud/ns.products/95",
          "confirm": {
            "message": "Would you like to delete this ?"
          },
          "type": "DELETE",
          "permissions": []
        }
      }
    }
  ],
  "first_page_url": "https://example.com/api/crud/ns.products?page=1",
  "from": 1,
  "last_page": 8,
  "last_page_url": "https://example.com/api/crud/ns.products?page=8",
  "links": [
    {
      "url": null,
      "label": "&laquo; Previous",
      "active": false
    },
    {
      "url": "https://example.com/api/crud/ns.products?page=1",
      "label": "1",
      "active": true
    },
    {
      "url": "https://example.com/api/crud/ns.products?page=2",
      "label": "2",
      "active": false
    },
    {
      "url": "https://example.com/api/crud/ns.products?page=3",
      "label": "3",
      "active": false
    },
    {
      "url": "https://example.com/api/crud/ns.products?page=4",
      "label": "4",
      "active": false
    },
    {
      "url": "https://example.com/api/crud/ns.products?page=5",
      "label": "5",
      "active": false
    },
    {
      "url": "https://example.com/api/crud/ns.products?page=6",
      "label": "6",
      "active": false
    },
    {
      "url": "https://example.com/api/crud/ns.products?page=7",
      "label": "7",
      "active": false
    },
    {
      "url": "https://example.com/api/crud/ns.products?page=8",
      "label": "8",
      "active": false
    },
    {
      "url": "https://example.com/api/crud/ns.products?page=2",
      "label": "Next &raquo;",
      "active": false
    }
  ],
  "next_page_url": "https://example.com/api/crud/ns.products?page=2",
  "path": "https://example.com/api/crud/ns.products",
  "per_page": 20,
  "prev_page_url": null,
  "to": 20,
  "total": 146
}
```

## Get Table Columns

Use this endpoint to retrieve the list of available columns.


<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/crud/{namespace}/columns</div>
    </div>
</div>

> Response

```json
{
  "name": {
    "label": "Name",
    "$direction": "",
    "$sort": false
  },
  "type": {
    "label": "Type",
    "$direction": "",
    "width": "150px",
    "$sort": false
  },
  "sku": {
    "label": "Sku",
    "$direction": "",
    "$sort": false
  },
  "category_name": {
    "label": "Category",
    "width": "150px",
    "$direction": "",
    "$sort": false
  },
  "status": {
    "label": "Status",
    "$direction": "",
    "$sort": false
  },
  "user_username": {
    "label": "Author",
    "$direction": "",
    "$sort": false
  },
  "created_at": {
    "label": "Date",
    "width": "150px",
    "$direction": "",
    "$sort": false
  }
}
```

## Get Table Configuration

This will retreive the current table configuration of a crud component.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/crud/{namespace}/config</div>
    </div>
</div>

> Response

```json
{
  "columns": {
    "name": {
      "label": "Name",
      "$direction": "",
      "$sort": false
    },
    "gastro_item_type": {
      "label": "Item Type",
      "$direction": "",
      "width": "120px",
      "$sort": false
    },
    "type": {
      "label": "Type",
      "$direction": "",
      "width": "150px",
      "$sort": false
    },
    "sku": {
      "label": "Sku",
      "$direction": "",
      "$sort": false
    },
    "category_name": {
      "label": "Category",
      "width": "150px",
      "$direction": "",
      "$sort": false
    },
    "status": {
      "label": "Status",
      "$direction": "",
      "$sort": false
    },
    "user_username": {
      "label": "Author",
      "$direction": "",
      "$sort": false
    },
    "created_at": {
      "label": "Date",
      "width": "150px",
      "$direction": "",
      "$sort": false
    }
  },
  "queryFilters": [],
  "labels": {
    "list_title": "Products List",
    "list_description": "Display all products.",
    "no_entry": "No products has been registered",
    "create_new": "Add a new product",
    "create_title": "Create a new product",
    "create_description": "Register a new product and save it.",
    "edit_title": "Edit product",
    "edit_description": "Modify  Product.",
    "back_to_list": "Return to Products"
  },
  "links": {
    "list": "https://example.com/dashboard/products",
    "create": "https://example.com/dashboard/products/create"
  },
  "bulkActions": [
    {
      "label": "Delete Selected Groups",
      "identifier": "delete_selected",
      "confirm": "Would you like to delete selected entries ?",
      "url": "https://example.com/api/crud/ns.products/bulk-actions"
    }
  ],
  "prependOptions": true,
  "showOptions": true,
  "showCheckboxes": true,
  "headerButtons": [],
  "namespace": "ns.products"
}
```


## Get Form Configuration

Use this endpoint to retrieve the shape of the form. When `{id}` is provided, the model defined on the CRUD will be loaded and it's property loaded on each fields. 
The way data are loaded is defined on the method `getForm()` of each CRUD instance.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/crud/{namespace}/form-config/{id?}</div>
    </div>
</div>

> Response

```json
{
  "form": {
    "main": {
      "label": "Name",
      "name": "name",
      "value": "",
      "description": "Provide a name to the resource.",
      "validation": "required"
    },
    "tabs": {
      "general": {
        "label": "General",
        "fields": [
          {
            "type": "media",
            "label": "Preview",
            "name": "preview_url",
            "description": "Provide a preview url to the category.",
            "value": ""
          },
          {
            "type": "switch",
            "label": "Displays On POS",
            "name": "displays_on_pos",
            "description": "If clicked to no, all products assigned to this category or all sub categories, won't appear at the POS.",
            "options": [],
            "validation": "required",
            "value": 1
          },
          {
            "type": "select",
            "options": [],
            "name": "parent_id",
            "label": "Parent",
            "description": "If this category should be a child category of an existing category",
            "value": ""
          },
          {
            "type": "ckeditor",
            "name": "description",
            "label": "Description",
            "value": ""
          }
        ]
      }
    }
  },
  "labels": {
    "list_title": "Category Products List",
    "list_description": "Display all category products.",
    "no_entry": "No category products has been registered",
    "create_new": "Add a new category product",
    "create_title": "Create a new category product",
    "create_description": "Register a new category product and save it.",
    "edit_title": "Edit category product",
    "edit_description": "Modify  Category Product.",
    "back_to_list": "Return to Category Products"
  },
  "links": {
    "list": "https://example.com/dashboard/products/categories",
    "create": "https://example.com/dashboard/products/categories/create",
    "edit": "https://example.com/dashboard/products/categories/edit",
    "post": "https://example.com/api/crud/ns.products-categories",
    "put": "https://example.com/api/crud/ns.products-categories/{id}"
  },
  "submitMethod": "post",
  "namespace": "ns.products",
  "optionAttributes": {
    "label": "name",
    "value": "id"
  },
  "queryParams": [],
  "title": "Create a new category product",
  "description": "Register a new category product and save it.",
  "src": "https://example.com/api/crud/ns.products-categories/form-config",
  "returnUrl": "https://example.com/dashboard/products/categories",
  "submitUrl": "https://example.com/api/crud/ns.products-categories"
}
```

## Create Entry

The structure of a POST request varies from my CRUD component to another. Generally speaking, as CRUD component are composed of tabs, we're sending a multi-hierarchical object. For more details on the structure of a refer to the "Get From Configuration".

<div class="endpoint">
    <div>
        <div class="method post">post</div>
        <div class="path">api/crud/{namespace}</div>
    </div>
</div>

> Response

```json
{
    "name": "[string]",
    "general": {
        "field_1": "[mixed]",
        "field_2": "[mixed]"
    }
}
```

<aside class="notice">
Note that, either `name`, `field_1` and `field_2` are all attributes of the model in use on the CRUD instance. There is no hierarchy between those fields.
</aside>

The entry `general` that keeps `field_1` and `field_2`, is not persistent on the database and is only used for grouping fields. It can therefore be anything you want.

## Update Entry

Use this endpoint to update a CRUD entry. The only difference with the "Create Entry", is the required `{id}` parameter that is provided. Make sure to replace both `{namespace}` and `{id}` with their respective values.

<div class="endpoint">
    <div>
        <div class="method put">put</div>
        <div class="path">api/crud/{namespace}/{id}</div>
    </div>
</div>

<aside class="notice">
Note that, either `name`, `field_1` and `field_2` are all attributes of the model in use on the CRUD instance. There is no hierarchy between those fields.
</aside>

> Request

```json
{
    "name": "[string]",
    "general": {
        "field_1": "[mixed]",
        "field_2": "[mixed]"
    }
}
```

## Export Entries

Use this endpoint to extract as a CSV document all the entries of a CRUD component.

<aside class="notice">
The exported entries are not paginated. In case of a huge list of entries, you might consider increasing the execution time of PHP.
</aside>

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/crud/{namespace}/export</div>
    </div>
</div>

## Available Components

Here is a list of the component that are currently available on the CRUD API. Those files are located on the directory `app/Crud`.

| Name    | Class |
| -------- | ------- |
| Coupons  | App\Models\CouponCrud    |
| Coupon Usage | App\Models\CouponOrderHistoryCrud     |
| Customer Wallet    | App\Models\CustomerAccountCrud    |
| Customer Coupons    | App\Models\CustomerCouponCrud    |
| Customer Coupon Usage    | App\Models\CustomerCouponHistoryCrud    |
| Customers    | App\Models\CustomerCrud    |
| Customers Group    | App\Models\CustomerGroupCrud    |
| Customer's Orders    | App\Models\CustomerOrderCrud    |
| Customers Rewards    | App\Models\CustomerRewardCrud    |
| Products History   | App\Models\GlobalProductHistoryCrud    |
| Hold Orders    | App\Models\HoldOrderCrud    |
| Orders Instalments    | App\Models\OrderInstalmentCrud   |
| Partially Paid Orders    | App\Models\PartiallyPaidOrderCrud    |
| Payment Types    | App\Models\PaymentTypeCrud    |
| Procurements    | App\Models\ProcurementCrud    |
| Procurements Products    | App\Models\ProcurementProductCrud   |
| Products Categories    | App\Models\ProductCategoryCrud    |
| Products    | App\Models\ProductCrud  |
| Products History    | App\Models\ProductHistoryCrud    |
| Products Unit Quantities    | App\Models\ProductUnitQuantitiesCrud   |
| Providers    | App\Models\ProviderCrud    |
| Providers Procurements    | App\Models\ProviderProcurementsCrud    |
| Provider Products    | App\Models\ProviderProductsCrud  |
| Registers    | App\Models\RegisterCrud |
| Registers History    | App\Models\RegisterHistoryCrud |
| Rewards System    | App\Models\RewardSystemCrud |
| Roles    | App\Models\RolesCrud |
| Taxes    | App\Models\TaxCrud |
| Tax Groups    | App\Models\TaxesGroupCrud  |
| Transaction Accounts    | App\Models\TransactionAccountCrud |
| Transactions    | App\Models\TransactionCrud  |
| Transactions History    | App\Models\TransactionHistoryCrud |
| Units    | App\Models\UnitCrud |
| Units Groups    | App\Models\UnitGroupCrud |
| Unpaid Orders | UnpaidOrderCrud |
| Users    | App\Models\UserCrud |