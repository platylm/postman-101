# API Product list

Name : Product list

## Set variable response for use next request (product detail)

```javascript
...

pm.test("Product id is existed", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.products[1].id).to.exist;
    pm.environment.set("product_id", jsonData.products[1].id);
});

...
```

# API Order

## Set variable response for use next request (confirm payment)

```javascript
...

pm.test("Order ID should be 8004359122", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.order_id).to.exist;
    pm.environment.set("order_id", jsonData.order_id);
});

...
```

# API Confirm payment

## Set variable request

```json
{
	"order_id": {{order_id}},
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
