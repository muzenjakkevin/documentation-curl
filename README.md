# documentation-curl

### HTTP Methods: Get

#### Getting resource data - users/1: 

```
curl -i -H "Content-Type:application/json" http://api.softhouse.rocks/users/1
```

#### Response:
```
HTTP/2 200 
x-powered-by: Express
access-control-allow-origin: *
content-type: application/json; charset=utf-8
content-length: 253
etag: W/"fd-9bEzwjdoX4y6CD1Ks/cPEoofFw4"
date: Tue, 21 Apr 2020 08:17:44 GMT
via: 1.1 google
alt-svc: clear
```

#### Pipes to jq

```
curl -H "Content-Type:application/json" http://api.softhouse.rocks/users/1 | jq
```

#### Response:

```
 {
  "address": {
    "geo": {
      "lat": -37.3159,
      "lng": 81.1496
    },
    "street": "Kulas Light",
    "suite": "Apt. 556",
    "city": "Gwenborough",
    "zipcode": "92998-3874"
  },
  "_id": "5e806d9f42fbde006b6b9ec5",
  "id": 1,
  "name": "Leanne Graham",
  "username": "Bret",
  "email": "Sincere@april.biz",
  "__v": 0
}
```

#### Getting resource data - posts/1:

```
curl -i  -H "Content-Type:application/json" https://api.softhouse.rocks/posts/1
```

#### Response:

```
HTTP/2 200 
x-powered-by: Express
access-control-allow-origin: *
content-type: application/json; charset=utf-8
content-length: 316
etag: W/"13c-iqD6A3ivz4dRZ1d/uIZLXBts6BU"
date: Tue, 21 Apr 2020 08:35:16 GMT
via: 1.1 google
alt-svc: clear

{"_id":"5e806d9f42fbde006b6b9ecf","userId":1,"id":1,"title":"sunt aut facere repellat provident occaecati excepturi optio reprehenderit","body":"quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto","__v":0}
```

#### Pipes to jq:

```
curl -H "Content-Type:application/json" https://api.softhouse.rocks/posts/1 | jq
```

#### Response from jq:

```
{
  "_id": "5e806d9f42fbde006b6b9ecf",
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto",
  "__v": 0
}

```
