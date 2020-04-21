# documentation-curl

### HTTP Methods: Get
---------------------
#### Getting resource data: 

```
curl -i -H "Content-Type:application/json" http://api.softhouse.rocks/users/1
```

#### Response:
```
HTTP/1.1 200 OK
X-Powered-By: Express
Access-Control-Allow-Origin: *
Content-Type: application/json; charset=utf-8
Content-Length: 253
ETag: W/"fd-9bEzwjdoX4y6CD1Ks/cPEoofFw4"
Date: Tue, 21 Apr 2020 08:44:40 GMT
Via: 1.1 google

{"address":{"geo":{"lat":-37.3159,"lng":81.1496},"street":"Kulas Light","suite":"Apt. 556","city":"Gwenborough","zipcode":"92998-3874"},"_id":"5e806d9f42fbde006b6b9ec5","id":1,"name":"Leanne Graham","username":"Bret","email":"Sincere@april.biz","__v":0
```

#### Pipes to jq:

```
curl -H "Content-Type:application/json" http://api.softhouse.rocks/users/1 | jq
```

#### Response:

```json
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
---------------------