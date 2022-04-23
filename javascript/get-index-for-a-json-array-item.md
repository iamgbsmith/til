# Get Index For A JSON Array Item

__Category: JavaScript__

Assuming a JSON array:

```json
[
    {
        "id": "b2ebf8bd-9124-4144-98f5-d1bbd8e9c258",
        "name": "Steve Page",
        "email": "steve.page@microspan.com"
    },
    {
        "id": "58ecde56-672d-4812-8935-acaae501bee1",
        "name": "Sharon Herbert",
        "email": "sharon.herbert@microspan.com"
    },
    {
        "id": "eb2a097e-59c3-4458-ac91-1af076c7a4d4",
        "name": "Bob Jackson",
        "email": "bob.jackson@microspan.com"
    },
]
```

You can get the array index for an item as follows:

```javascript
const index = employees.findIndex(employee => employee.email === "bob.jackson@microspan.com");
```
