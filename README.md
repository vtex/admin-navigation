# Admin Navigation

This app defines the extension interface for other apps to add themselves to the admin menu.

### How to add your app to the admin navigation

1. Create an `admin/admin.json` file containing your `routes` and `navigation`. All admin apps must have the prefix `/admin/app/` to all their routes.

```
{
  "routes": {
    "admin.example": {
      "component": "ExampleAdmin",
      "path": "/admin/app/example"
    }
  },
  "navigation": {
      "icon": "inventory-shipping-ic",
      "id": "9",
      "subItems": [
        {
          "labelId": "appframe.navigation.pickupPoints",
          "path": "/admin/example"
        }
      ],
      "titleId": "appframe.navigation.inventoryAndShipping",
      "group": "delivery"
    } 
}
```

2. Add the `admin` builder to your manifest:

```
(...)
    "builders": {
        "admin": "1.x"
    },
(...)
```

3. To view your app directly, navigate to `/admin/app/example`. To view it in the context of the admin container, navigate to `/admin/example`. Your app will run inside an iframe pointing to the former URL.

### Admin Example

Check out https://github.com/vtex-apps/admin-example for a complete admin example.

