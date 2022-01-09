<br/>
<br/>
<p align="middle" >
  <img width="200px;" src="./asset/cart.png"/>
</p>
<h2 align="middle">장바구니 API</h2>
<p align="middle">Clean Code React 장바구니 미션 API</p>

## 🌏 baseUrl

```
https://clean-code-shopping-cart.herokuapp.com/
```

## 🎁 상품

### 상품 목록 조회

| method | uri     |
| ------ | ------- |
| GET    | product |

```json
{
  "response": [
    {
      "productId": 1,
      "price": 10000,
      "name": "치킨",
      "imageUrl": "http://example.com/chicken.jpg"
    },
    {
      "productId": 2,
      "price": 20000,
      "name": "피자",
      "imageUrl": "http://example.com/pizza.jpg"
    }
  ]
}
```

### 상품 추가

| method | uri     |
| ------ | ------- |
| POST   | product |

```json
{
  "requestBody": {
    "price": 10000,
    "name": "치킨",
    "imageUrl": "http://example.com/chicken.jpg"
  }
}
```

### 상품 단일 조회

| method | uri                 |
| ------ | ------------------- |
| GET    | product/{productId} |

```json
{
  "response": {
    "productId": 1,
    "price": 10000,
    "name": "치킨",
    "imageUrl": "http://example.com/chicken.jpg"
  }
}
```

### 상품 단일 삭제

| method | uri                 |
| ------ | ------------------- |
| DELETE | product/{productId} |

```json
{
  "response": {}
}
```

## 🛒 장바구니

### 장바구니 아이템 목록 조회

| method | uri   |
| ------ | ----- |
| GET    | /cart |

```json
{
  "response": [
    {
      "productId": 1,
      "price": 10000,
      "name": "치킨",
      "imageUrl": "http://example.com/chicken.jpg"
    },
    {
      "productId": 2,
      "price": 20000,
      "name": "피자",
      "imageUrl": "http://example.com/pizza.jpg"
    }
  ]
}
```

### 장바구니 아이템 추가

| method | uri   |
| ------ | ----- |
| POST   | /cart |

```json
{
  "requestBody": {
    "productId": 1
  }
}
```

### 장바구니 아이템 단일 삭제

| method | uri             |
| ------ | --------------- |
| DELETE | /cart/{cart_id} |

```json
{
  "response": {}
}
```

## 🗒 주문

### 주문 추가(주문하기)

| method | uri    |
| ------ | ------ |
| POST   | /order |

```json
{
  "requestBody": [
    {
      "cart_id": 1,
      "quantity": 5
    },
    {
      "cart_id": 2,
      "quantity": 3
    }
  ]
}
```

### 주문 목록(내역) 조회

| method | uri    |
| ------ | ------ |
| GET    | /order |

```json

{
  "response": [
    {
      "order_id": 1,
      "order_details": [
        {
          "productId": 1,
          "price": 10000,
          "name": "치킨",
          "imageUrl": "http://example.com/chicken.jpg",
          "quantity": 5
        },
        {
          "productId": 2,
          "price": 20000,
          "name": "피자",
          "imageUrl": "http://example.com/pizza.jpg",
          "quantity": 3
        }
      ]
    },
    {
      "order_id": 2,
      "order_details": [
        {
          "productId": 1,
          "price": 10000,
          "name": "치킨",
          "imageUrl": "http://example.com/chicken.jpg",
          "quantity": 5
        },
        {
          "productId": 2,
          "price": 20000,
          "name": "피자",
          "imageUrl": "http://example.com/pizza.jpg",
          "quantity": 3
        }
      ]
    }
  ]
```

### 주문 단일 조회

| method | uri               |
| ------ | ----------------- |
| GET    | /order/{order_id} |

```json
{
  "response": {
    "order_id": 1,
    "order_details": [
      {
        "productId": 1,
        "price": 10000,
        "name": "치킨",
        "imageUrl": "http://example.com/chicken.jpg",
        "quantity": 5
      }
    ]
  }
}
```

## ⚖️ License

[MIT licensed](LICENSE)
