# Notifications

Use this route to handle the notification of the logged user.

## Get Notifications

Use this endpoint to retrieve all notifications available for the logged user.


<div class="endpoint">
    <div>
        <div class="method get">get</div>
        <div class="path">api/notifications</div>
    </div>
</div>

> Response

```json
[
    {
        "id": 53,
        "user_id": 8,
        "identifier": "nspa-no-jobs",
        "title": "Kitchen Print Failure",
        "description": "No valid print jobs can be generated for the order 250210-001. Make sure the category of the products included are assigned to existing kitchen and that valid printers are assigned\"",
        "url": "#",
        "source": "system",
        "dismissable": 1,
        "created_at": "2025-02-10 11:58:12",
        "updated_at": "2025-02-10 11:58:12"
    }
]
```

## Delete Notification

Use this endpoint to delete a notification using it's ID. You'll replace {id} with the ID that match the notification you want to delete.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/notifications/{id}</div>
    </div>
</div>

> Response

```json
{
  "status": "success",
  "message": "The notification has been successfully deleted"
}
```

## Delete All Notifications

Use this endpoint to delete all notifications that was created for the logged user.

<div class="endpoint">
    <div>
        <div class="method delete">delete</div>
        <div class="path">api/notifications/all</div>
    </div>
</div>

> Response

```json
{
  "status": "success",
  "message": "All the notifications have been cleared"
}
```