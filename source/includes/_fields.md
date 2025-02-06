# Fields

The Fields endpoint give you access to a structure of defined fields. The way fields are defined varies from one instance of FieldsService class to another. Fields are defined on the directory `app/Fields`;

## Get Fields

Use this endpoint to get the shape of a fields. You can optionnally provide an identifier that will be used by the FieldsService class. For example, this is used to retrieve the login, registration fields etc. We'll use the login fields as an example.

<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/fields/{resource}/{identifier?}</div>
    </div>
</div>

> Response 

```json
[
  {
    "label": "Username",
    "description": "Provide your username.",
    "validation": "required",
    "name": "username",
    "type": "text"
  },
  {
    "label": "Password",
    "description": "Provide your password.",
    "validation": "required",
    "name": "password",
    "type": "password"
  }
]
```

## Available Fields

Here is a list of available fields and their identifier.

| Name    | Class | Identifier |
| ------- | ----- | ---------- |
| Authentication Fields | App\Fields\AuthLoginFields | ns.login |
| Registration Fields | App\Fields\AuthRegisterFields | ns.register |
| Cash Register Cash In | App\Fields\CashRegisterCashingFields | ns.cash-registers-cashing |
| Cash Register Cash out | App\Fields\CashRegisterCashoutFields | ns.cash-registers-cashout |
| Cash Register Closing | App\Fields\CashRegisterClosingFields | ns.cash-registers-closing |
| Cash Register Opening | App\Fields\CashRegisterOpeningFields | ns.cash-registers-opening |
| Customer Account Fields | App\Fields\CustomerAccountFields | ns.customers-account |
| Direct Transaction | App\Fields\DirectTransactionFields | ns.direct-transaction |
| Entity Transaction | App\Fields\EntityTransactionFields | ns.entity-transaction |
| Layaway Fields | App\Fields\LayawayFields | ns.layaway |
| New Password Fields | App\Fields\NewPasswordFields | ns.new-password |
| Order Payment Fields | App\Fields\OrderPaymentFields | ns.order-payments |
| Password Lost Fields | App\Fields\PasswordLostFields | ns.password-lost |
| POS Order Settings | App\Fields\PosOrderSettingsFields | ns.pos-order-settings |
| Procurement Fields | App\Fields\ProcurementFields | ns.procurement-fields |
| Recurring Transaction Fields | App\Fields\RecurringTransactionFields | ns.recurring-transaction |
| Refund Product Fields | App\Fields\RefundProductFields | ns.refund-product |
| Reset Fields | App\Fields\ResetFields | ns.reset |
| Scheduled Transaction Fields | App\Fields\ScheduledTransactionFields | ns.scheduled-transaction |
| Units Fields | App\Fields\UnitFields | ns.units-fields |
| Units Group Fields | App\Fields\UnitGroupFields | ns.units-group-fields |
