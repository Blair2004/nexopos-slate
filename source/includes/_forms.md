# Forms

Unlike [fields](#fields), forms provide a more complex structure of fields. This usually consist of a tabbed form. This is currently used by the settings.

## Get Form

Use this endpoint to retrieve the shape of a declared form. You'll replace `{resource}` by the identifier of the Form and `{identifier?}` (optional) to provide more context to the Form. Note that the context might be needed or not by the Form, you should refer to the Form or it's declared documentation to understand how to use it.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/forms/{resource}/{identifier?}</div>
    </div>
</div>

> Response

We'll use `ns.user-profile` to retrieve the form in use on the user profile section.

```json
{
  "tabs": {
    "attribute": {
      "label": "General",
      "fields": [
        {
          "label": "Theme",
          "name": "theme",
          "value": "dark",
          "type": "select",
          "options": [
            {
              "label": "Dark",
              "value": "dark"
            },
            {
              "label": "Light",
              "value": "light"
            }
          ],
          "description": "Define what is the theme that applies to the dashboard."
        },
        {
          "label": "Avatar",
          "name": "avatar_link",
          "value": "",
          "type": "media",
          "data": {
            "user_id": 8,
            "type": "url"
          },
          "description": "Define the image that should be used as an avatar."
        },
        {
          "label": "Language",
          "name": "language",
          "value": "en",
          "type": "select",
          "options": [
            {
              "label": "English",
              "value": "en"
            },
            {
              "label": "Deutsch",
              "value": "de"
            },
            {
              "label": "Français",
              "value": "fr"
            },
            {
              "label": "Espanol",
              "value": "es"
            },
            {
              "label": "Italian",
              "value": "it"
            },
            {
              "label": "Arabic",
              "value": "ar"
            },
            {
              "label": "Portuguese",
              "value": "pt"
            },
            {
              "label": "Türkçe",
              "value": "tr"
            },
            {
              "label": "ភាសាខ្មែរ",
              "value": "km"
            },
            {
              "label": "Vietnamese",
              "value": "vi"
            },
            {
              "label": "Shqiptare",
              "value": "sq"
            }
          ],
          "description": "Choose the language for the current account."
        }
      ]
    },
    "shipping": {
      "label": "Shipping",
      "fields": [
        {
          "type": "text",
          "name": "first_name",
          "value": "",
          "label": "First Name",
          "description": "Provide the billing first name."
        },
        {
          "type": "text",
          "name": "last_name",
          "value": "",
          "label": "Last Name",
          "description": "Provide the billing last name."
        },
        {
          "type": "text",
          "name": "phone",
          "value": "",
          "label": "Phone",
          "description": "Billing phone number."
        },
        {
          "type": "text",
          "name": "address_1",
          "value": "",
          "label": "Address 1",
          "description": "Billing First Address."
        },
        {
          "type": "text",
          "name": "address_2",
          "value": "",
          "label": "Address 2",
          "description": "Billing Second Address."
        },
        {
          "type": "text",
          "name": "country",
          "value": "",
          "label": "Country",
          "description": "Billing Country."
        },
        {
          "type": "text",
          "name": "city",
          "value": "",
          "label": "City",
          "description": "City"
        },
        {
          "type": "text",
          "name": "pobox",
          "value": "",
          "label": "PO.Box",
          "description": "Postal Address"
        },
        {
          "type": "text",
          "name": "company",
          "value": "",
          "label": "Company",
          "description": "Company"
        },
        {
          "type": "text",
          "name": "email",
          "value": "",
          "label": "Email",
          "description": "Email"
        }
      ]
    },
    "billing": {
      "label": "Biling",
      "fields": [
        {
          "type": "text",
          "name": "first_name",
          "value": "",
          "label": "First Name",
          "description": "Provide the billing first name."
        },
        {
          "type": "text",
          "name": "last_name",
          "value": "",
          "label": "Last Name",
          "description": "Provide the billing last name."
        },
        {
          "type": "text",
          "name": "phone",
          "value": "",
          "label": "Phone",
          "description": "Billing phone number."
        },
        {
          "type": "text",
          "name": "address_1",
          "value": "",
          "label": "Address 1",
          "description": "Billing First Address."
        },
        {
          "type": "text",
          "name": "address_2",
          "value": "",
          "label": "Address 2",
          "description": "Billing Second Address."
        },
        {
          "type": "text",
          "name": "country",
          "value": "",
          "label": "Country",
          "description": "Billing Country."
        },
        {
          "type": "text",
          "name": "city",
          "value": "",
          "label": "City",
          "description": "City"
        },
        {
          "type": "text",
          "name": "pobox",
          "value": "",
          "label": "PO.Box",
          "description": "Postal Address"
        },
        {
          "type": "text",
          "name": "company",
          "value": "",
          "label": "Company",
          "description": "Company"
        },
        {
          "type": "text",
          "name": "email",
          "value": "",
          "label": "Email",
          "description": "Email"
        }
      ]
    },
    "security": {
      "label": "Security",
      "fields": [
        {
          "label": "Old Password",
          "name": "old_password",
          "type": "password",
          "description": "Provide the old password."
        },
        {
          "label": "Password",
          "name": "password",
          "type": "password",
          "description": "Change your password with a better stronger password.",
          "validation": "sometimes|min:6"
        },
        {
          "label": "Password Confirmation",
          "name": "password_confirm",
          "type": "password",
          "description": "Change your password with a better stronger password.",
          "validation": "same:security.password"
        }
      ]
    },
    "token": {
      "label": "API Token",
      "component": "nsToken",
      "fields": []
    }
  }
}
```

## Available Forms

Here is a list of available form and their identifier.

| Name    | Class | Identifier |
| ------- | ----- | ---------- |
| Order Address | App\Forms\POSAddressForm | ns.pos-addresses |
| Procurement Form | App\Forms\ProcurementForm | ns.procurement |
| User Profile | App\Forms\UserProfileForm | ns.user-profile |