# Request

# API Order

```json
{
	"cart":[
		{
			"product_id": {{product_id}},
			"quantity": {{product_quantity}}
		}
	],
	"shipping_method": "{{shipping_method}}",
	"shipping_address": "{{shipping_address}}",
	"shipping_sub_district": "{{shipping_sub_district}}",
	"shipping_district": "{{shipping_district}}",
	"shipping_province": "{{shipping_province}}",
	"shipping_zip_code": "{{shipping_zip_code}}",
	"recipient_name": "{{recipient_name}}",
	"recipient_phone_number": "{{recipient_phone_number}}"
}
```

# API Confirm payment

```json
{
	"order_id": {{order_id}},
	"payment_type": "{{payment_type}}",
	"type": "{{type}}",
	"card_number": "{{card_number}}",
	"cvv": "{{cvv}}",
	"expired_month": {{expired_month}},
	"expired_year": {{expired_year}},
	"card_name": "{{card_name}}",
	"total_price": {{total_price}}
}
```

# Response

# API Product list

```javascript
...

pm.test("Total should be 2", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.total).to.eql(data["assert"]["total"]);
});

pm.test("Product name should be 43 Piece dinner Set", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.products[1].product_name).to.eql(data["assert"]["product_name"]);
});

pm.test("Product price should be 12.95", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.products[1].product_price).to.eql(data["assert"]["product_price"]);
});

pm.test("Product image should be path /43_Piece_dinner_Set.png", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.products[1].product_image).to.eql(data["assert"]["product_image"]);
});
```

# API Product detail

```javascript
...

pm.test("Product name should be 43 Piece dinner Set", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.product_name).to.eql(data["assert"]["product_name"]);
});

pm.test("Product price should be 12.95", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.product_price).to.eql(data["assert"]["product_price"]);
});

pm.test("Quantity should be 10", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.quantity).to.eql(data["assert"]["quantity"]);
});

pm.test("Product band should be CoolKidz", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.product_brand).to.eql(data["assert"]["product_brand"]);
});
```

# API Order

```javascript
...

pm.test("Total prince should be 14.95", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.total_price).to.eql(data["assert"]["total_price"]);
});
```

# API Confirm payment

```javascript
...

pm.test("Notifify message should be ", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.notify_message).to.eql(data["assert"]["notify_message"]);
});
```
