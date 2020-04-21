# documentation-curl

### HTTP Methods: GeT

#### Getting resource data: 

```
curl -H "Content-Type:application/json" http://api.softhouse.rocks/users/1 | jq >
```

#### Answers
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

#### Gets:

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
