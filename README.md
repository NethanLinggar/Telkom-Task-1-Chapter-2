##**Telkom Task 1 Chapter 2**

```bash
# You can start the project with below commands
go mod tidy
docker-compose up -d
go run main.go
```

- **Sign Up Function API Call (POST REQUEST)**

  http://localhost:8000/users/signup

```json
{
  "first_name": "Nethan",
  "last_name": "Linggar",
  "email": "nethan.linggar@gmail.com",
  "password": "NethanLinggar",
  "phone": "+628131234567"
}
```

Response:
```"Successfully Signed Up!!"```

- **Login Function API Call (POST REQUEST)**

  http://localhost:8000/users/login

```json
{
  "email": "nethan.linggar@gmail.com",
  "password": "NethanLinggar"
}
```

Response:

```json
{
  "_id": "645e367dd677ff15da0cf8b7",
  "first_name": "Nethan",
  "last_name": "Linggar",
  "password": "$2a$14$.bqYlkXRec.QoHyFwpfYruBZi0IpoothV4Ky5019IB/VFzC.Eh7Zu",
  "email": "nethan.linggar@gmail.com",
  "phone": "+628131234567",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJFbWFpbCI6Im5ldGhhbi5saW5nZ2FyQGdtYWlsLmNvbSIsIkZpcnN0X05hbWUiOiJOZXRoYW4iLCJMYXN0X05hbWUiOiJMaW5nZ2FyIiwiVWlkIjoiNjQ1ZTM2N2RkNjc3ZmYxNWRhMGNmOGI3IiwiZXhwIjoxNjgzOTgyMzMzfQ.xWdU973dGRbUDp-IoNKM-b38Et6Qr710gX3Bn0E9d2c",
  "Refresh_Token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJFbWFpbCI6IiIsIkZpcnN0X05hbWUiOiIiLCJMYXN0X05hbWUiOiIiLCJVaWQiOiIiLCJleHAiOjE2ODQ1MDA3MzN9.EdYojTkx--BOagSymCiRwhGaFLeqmeUTGKkK1g7jOPg",
  "created_at": "2023-05-12T12:52:13Z",
  "updtaed_at": "2023-05-12T12:52:13Z",
  "user_id": "645e367dd677ff15da0cf8b7",
  "usercart": [],
  "address": [],
  "orders": []
}
```

- **Admin Add Product Function (POST REQUEST)**

  http://localhost:8000/admin/addproduct

```json
{
  "product_name": "Alienware x15",
  "price": 2500,
  "rating": 10,
  "image": "alienware.jpg"
}
```

Response:
```"Successfully added our Product Admin!!"```

- **View All The Products in DB (GET REQUEST)**

  http://localhost:8000/users/productview

Response:

```json
[
  {
    "Product_ID": "6153ff8edef2c3c0a02ae39a",
    "product_name": "Alienware X15",
    "price": 1500,
    "rating": 10,
    "image": "alienware.jpg"
  },
  {
    "Product_ID": "616152679f29be942bd9df8f",
    "product_name": "Ginger Ale",
    "price": 900,
    "rating": 5,
    "image": "gin.jpg"
  },
  {
    "Product_ID": "616152ee9f29be942bd9df90",
    "product_name": "iPhone 13",
    "price": 1700,
    "rating": 4,
    "image": "ipho.jpg"
  },
  {
    "Product_ID": "616152fa9f29be942bd9df91",
    "product_name": "Whiskey",
    "price": 100,
    "rating": 7,
    "image": "whis.jpg"
  },
  {
    "Product_ID": "616153039f29be942bd9df92",
    "product_name": "Acer Predator",
    "price": 3000,
    "rating": 10,
    "image": "acer.jpg"
  }
]
```

- **Search Product by Regex Function (GET REQUEST)**

http://localhost:8000/users/search?name=Al

Response:

```json
[
  {
    "Product_ID": "616152fa9f29be942bd9df91",
    "product_name": "Alienware X15",
    "price": 1500,
    "rating": 10,
    "image": "1.jpg"
  },
  {
    "Product_ID": "616153039f29be942bd9df92",
    "product_name": "Ginger Ale",
    "price": 300,
    "rating": 10,
    "image": "1.jpg"
  }
]
```

- **Adding the Products to the Cart (GET REQUEST)**

  http://localhost:8000/addtocart?id=xxx&product_idxxx&userID=xxxxxxuser_idxxxxxx

- **Removing Item From the Cart (GET REQUEST)**

  http://localhost:8000/addtocart?id=xxxxxxx&userID=xxxxxxxxxxxx

- **Listing the item in the users cart (GET REQUEST) and total price**

  http://localhost:8000/listcart?id=xxxxxxuser_idxxxxxxxxxx

- **Addding the Address (POST REQUEST)**

  http://localhost:8000/addadress?id=user_id**\*\***\***\*\***

  The Address array is limited to two values home and work address more than two address is not acceptable.

```json
{
  "house_name": "white house",
  "street_name": "white street",
  "city_name": "washington",
  "pin_code": "332423432"
}
```

- **Editing the Home Address(PUT REQUEST)**

  http://localhost:8000/edithomeaddress?id=xxxxxxxxxxuser_idxxxxxxxxxxxxxxx

- **Editing the Work Address(PUT REQUEST)**

  http://localhost:8000/editworkaddress?id=xxxxxxxxxxuser_idxxxxxxxxxxxxxxx

- **Delete Addresses(GET REQUEST)**

  http://localhost:8000/deleteaddresses?id=xxxxxxxxxuser_idxxxxxxxxxxxxx

  delete both addresses

- **Cart Checkout Function and placing the order(GET REQUEST)**

  After placing the order, the items are deleted from the cart.

  http://localhost:8000?id=xxuser_idxxx

- **Instantly Buying the Products(GET REQUEST)**
  
  http://localhost:8000?userid=xxuser_idxxx&pid=xxxxproduct_idxxxx
