# documentation-curl

### HTTP Methods: Get
---------------------
#### Getting resource data: 

##### Request to api and gets the curtain query you asked for.

/users
```
curl -i -H "Content-Type:application/json" http://api.softhouse.rocks/users
```

#### Response:

##### Shows response code and other information

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

---------------------

#### Pipe it to jq by removing ```-i``` and add ```| jq``` to the end of the request, for it to show the response in JSON format:

```
curl -H "Content-Type:application/json" http://api.softhouse.rocks/users/1 | jq
```

#### Response JSON format:

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

### HTTP Methods: Post
---------------------
#### Creating resource data: 

```
curl -i -X POST -H "Content-Type:application/json" http://api.softhouse.rocks/posts -d '{"title":"Hi, World", "body":"Fresh as morning dew", "userId": "1"}'
```

#### Response:
```
X-Powered-By: Express
Access-Control-Allow-Origin: *
Content-Type: application/json; charset=utf-8
Content-Length: 112
ETag: W/"70-Xq/1fb0vbdpeGv+Pb/lNzfBf9gM"
Date: Tue, 21 Apr 2020 09:02:09 GMT
Via: 1.1 google

{"_id":"5e9eb69109cee0002106f31a","body":"Fresh as morning dew","title":"Hi, World","userId":1,"id":826,"__v":0}

```

#### Pipes to jq:

```
 curl  -X POST -H "Content-Type:application/json" http://api.softhouse.rocks/posts -d '{"title":"Hi, World", "body":"Fresh as morning dew", "userId": "1"}' | jq

```

#### Response:

```json
{
 "_id": "5e9eb74d09cee0002106f31c",
  "body": "Fresh as morning dew",
  "title": "Hi, World",
  "userId": 1,
  "id": 828,
  "__v": 0
}
```
--------------

