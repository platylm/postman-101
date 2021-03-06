# API Product list

Name : Product list

Product should have 43 Piece dinner Set in store

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Total should be 2", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.total).to.eql(2);
});

pm.test("Product name should be 43 Piece dinner Set", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.products[1].product_name).to.eql("43 Piece dinner Set");
});

pm.test("Product price should be 12.95", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.products[1].product_price).to.eql(12.95);
});

pm.test("Product image should be path /43_Piece_dinner_Set.png", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.products[1].product_image).to.eql("/43_Piece_dinner_Set.png");
});
```

# API Product detail

Name : Product detail id 2

See detail product 43 Piece dinner Set

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Product name should be 43 Piece dinner Set", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.product_name).to.eql("43 Piece dinner Set");
});

pm.test("Product price should be 12.95", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.product_price).to.eql(12.95);
});

pm.test("Quantity should be 10", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.quantity).to.eql(10);
});

pm.test("Product band should be CoolKidz", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.product_brand).to.eql("CoolKidz");
});
```

# API Order

Name : Add to cart and checkout

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Order ID should be 8004359122", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.order_id).to.eql(8004359122);
});

pm.test("Total prince should be 14.95", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.total_price).to.eql(14.95);
});
```

# API Confirm payment

Name : Confirm payment and get notification message

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Notifify message should be ", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.notify_message).to.eql("วันเวลาที่ชำระเงิน 1/3/2020 13:30:00 หมายเลขคำสั่งซื้อ 8004359122 คุณสามารถติดตามสินค้าผ่านช่องทาง Kerry หมายเลข 1785261900");
});
```
