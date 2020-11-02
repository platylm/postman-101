# API Product list

> Method : GET

`localhost:8000/api/v1/product`

### Body

```json
{
    "total": 2,
    "products": [
        {
            "id": 1,
            "product_name": "Balance Training Bicycle",
            "product_price": 119.95,
            "product_image": "/Balance_Training_Bicycle.png"
        },
        {
            "id": 2,
            "product_name": "43 Piece dinner Set",
            "product_price": 12.95,
            "product_image": "/43_Piece_dinner_Set.png"
        }
    ]
}
```

# API Product detail id 1

> Method : GET

`localhost:8000/api/v1/product/1`

### Body

```json
{
    "id": 1,
    "product_name": "Balance Training Bicycle",
    "product_price": 119.95,
    "product_image": "/Balance_Training_Bicycle.png",
    "quantity": 5,
    "product_brand": "SportsFun"
}
```

# API Product detail id 2

> Method : GET

`localhost:8000/api/v1/product/2`

### Body

```json
{
    "id": 2,
    "product_name": "43 Piece dinner Set",
    "product_price": 12.95,
    "product_image": "/43_Piece_dinner_Set.png",
    "quantity": 10,
    "product_brand": "CoolKidz"
}
```

# API Order

> Method : POST

`localhost:8000/api/v1/order`

### Body Request

```json
{
	"cart":[
		{
			"product_id": 2,
			"quantity": 1
		}
	],
	"shipping_method": "Kerry",
	"shipping_address": "405/37 ถ.มหิดล",
	"shipping_sub_district": "ท่าศาลา",
	"shipping_district": "เมือง",
	"shipping_province": "เชียงใหม่",
	"shipping_zip_code": "50000",
	"recipient_name": "ณัฐญา ชุติบุตร",
	"recipient_phone_number": "0970809292"
}
```

### Body Response

```json
{
    "order_id": 8004359104,
    "total_price": 14.95
}
```

# API Confirm payment

> Method : POST

`localhost:8000/api/v1/confirmPayment`

### Body Request
```json
{
	"order_id": 8004359104,
	"payment_type": "credit",
	"type": "visa",
	"card_number": "4719700591590995",
	"cvv": "752",
	"expired_month": 7,
	"expired_year": 20,
	"card_name": "Karnwat Wongudom",
	"total_price": 14.95
}
```

### Body Response
```json
{
    "notify_message": "วันเวลาที่ชำระเงิน 1/3/2020 13:30:00 หมายเลขคำสั่งซื้อ 8004359104 คุณสามารถติดตามสินค้าผ่านช่องทาง Kerry หมายเลข 1785261900"
}
```

# API Mock time (set date)

> Method : GET

`localhost:8000/mockTime/01032020T13:30:00`

### Body Response

```json
{
    "fixTime": "2020-03-01T13:30:00Z",
    "status": "ok"
}
```