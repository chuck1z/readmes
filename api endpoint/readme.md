# Api Documentation

## Fruits Endpoint

- base url : `https://<cloudrun_service_name>.a.run.app/`
- base image url : `https://storage.googleapis.com/<bucket_name>/`

### Fruits Of The Day

- Path : `/fruits/fotd`
- Method : `GET`
- Response :

```json
{
  "error": false,
  "message": "Fruits of The Day fetched successfully",
  "data": {
    "fruits_id": "f0001",
    "name": "apple",
    "image": "apple.png",
    "short_desc": "lorem ipsum dolor sit amet..."
  }
}
```

### Fruits Tips

- Path : `/fruits/tips`
- Method : `GET`
- Response :

```json
{
  "error": false,
  "message": "Tips fetched successfully",
  "data": [
    {
      "tips_id": "tf0001",
      "title": "apple nice fruits",
      "image": "tips-apple.png",
      "short_desc": "lorem ipsum dolor sit amet..."
    },
    {
      "tips_id": "tf0002",
      "title": "orange good fruits",
      "image": "tips-orange.png",
      "short_desc": "lorem ipsum dolor sit amet..."
    }
  ]
}
```

### Fruits Tips detail

- Path : `/fruits/tips/<tips-id>`
- Method : `GET`
- Response :

```json
{
  "error": false,
  "message": "Tips detail fetched successfully",
  "data": {
    "tips_id": "tf0001",
    "title": "apple nice fruits",
    "image": "tips-apple.png",
    "short_desc": "lorem ipsum dolor sit amet...",
    "date_posted": "2022-01-08T06:34:18.598Z",
    "full_desc": "orem ipsum dolor sit amet, orem ipsum dolor sit amet,orem ipsum dolor sit amet,orem ipsum dolor sit amet"
  }
}
```

### Fruits detail

- Path : `/fruits/<fruits-id>/detail`
- Method : `GET`
- Response :

```json
{
  "error": false,
  "message": "Tips detail fetched successfully",
  "data": {
    "id": "f00021",
    "name": "Orange",
    "binom": "Citrus Sinensis",
    "nutrition": {
      "carbs": "11g",
      "protein": "0.9g",
      "calories": "45",
      "fat": "0.1g"
    },
    "image": "orange.png",
    "vitamin": ["Vit C", "Vit D", "Vit B6"],
    "about": "",
    "tips": [
      "Make sure the tip of the fruit is either pale white or yellowish brown. Avoid oranges with dark-looking tip",
      "Make sure the skin looks clear or have minimal blemishes"
    ]
  }
}
```

## Auth Endpoint

- base url : `https://<cloudrun_service_name>.a.run.app/`
- base image url : `https://storage.googleapis.com/<bucket_name>/`

### Register

- Path : `/signup`
- Method : `POST`
- Response :

```json
ini perlu diganti
{
  "error": false,
  "email": "someone@mail.com",
  "data": {
    "fruits_id": "f0001",
    "name": "apple",
    "image": "apple.png",
    "short_desc": "lorem ipsum dolor sit amet..."
  }
}
```
