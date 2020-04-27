# documentation-curl

### HTTP Methods: Get
---------------------
#### Request to api and gets the curtain query you asked for.

##### Getting resource data: 
/users
```
curl -i -H "Content-Type:application/json" http://api.softhouse.rocks/users
```

#### Response:

##### Shows response code and other information about the request

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

##### Pipe it to jq by removing ```-i``` and add ```| jq``` to the end of the request, for it to show the response in JSON format:

```
curl -H "Content-Type:application/json" http://api.softhouse.rocks/users/1 | jq
```

##### Response JSON format:
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
#### Requests that the server accept the entity enclosed in the request as a new subordinate of the web resource identified by the URI.

##### Creating resource data:
/posts
```
curl -i -X POST -H "Content-Type:application/json" http://api.softhouse.rocks/posts -d '{"title":"Hi, World", "body":"Fresh as morning dew", "userId": "1"}'
```

#### Response:

##### Shows response code and other information about the request
```
HTTP/1.1 201 OK
X-Powered-By: Express
Access-Control-Allow-Origin: *
Content-Type: application/json; charset=utf-8
Content-Length: 112
ETag: W/"70-Xq/1fb0vbdpeGv+Pb/lNzfBf9gM"
Date: Tue, 21 Apr 2020 09:02:09 GMT
Via: 1.1 google

{"_id":"5e9eb69109cee0002106f31a","body":"Fresh as morning dew","title":"Hi, World","userId":1,"id":826,"__v":0}

```

---------------------

##### Pipe it to jq by removing ```-i``` and add ```| jq``` to the end of the request, for it to show the response in JSON format:

```
 curl  -X POST -H "Content-Type:application/json" http://api.softhouse.rocks/posts -d '{"title":"Hi, World", "body":"Fresh as morning dew", "userId": "1"}' | jq

```

##### Response JSON format:
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

### HTTP Methods: PUT
---------------------
#### The PUT method requests that the enclosed entity be stored under the supplied URI. If the URI refers to an already existing resource, it is modified; if the URI does not point to an existing resource, then the server can create the resource with that URI.

##### Creates new resource and replaces the information to the chosen object you decided to create new data on. 

/posts
```
curl -X PUT http://api.softhouse.rocks/posts/1 -H "Content-type:application/json" -d '{"id": 1, "body":"Grant Cardone", "title":"Real Estate Mogule", "userId":1}'
```

#### Response:

##### When you GET and request the new change to the post
```
HTTP/1.1 200 OK
X-Powered-By: Express
Access-Control-Allow-Origin: *
Content-Type: application/json; charset=utf-8
Content-Length: 112
ETag: W/"70-wC7Rot1BiEiBr9pH+me1h6CuKCA"
Date: Mon, 27 Apr 2020 06:47:18 GMT
Via: 1.1 google

{"_id":"5ea143518e9e2e7dc0da6f8a","id":1,"__v":0,"body":"Grant Cardone","title":"Real Estate Mogule","userId":1}

```

---------------------

##### Pipe it to jq by removing ```-i``` and add ```| jq``` to the end of the request, for it to show the response in JSON format:

```
curl -H "Content-Type:application/json" http://api.softhouse.rocks/posts/1 | jq
```

##### Response JSON format:

```json
{
  "_id": "5ea143518e9e2e7dc0da6f8a",
  "id": 1,
  "__v": 0,
  "body": "Grant Cardone",
  "title": "Real Estate Mogule",
  "userId": 1
}
```
--------------

### HTTP Methods: PATCH
---------------------
#### The PATCH method applies partial modifications to a resource.

##### Overwrites and replaces the information of the object you wanted to replace

/posts
```
curl -X PATCH http://api.softhouse.rocks/posts/2 -H "Content-Type:application/json" -d '{"body": "Dean Graziosi", "title":"Inspirator, investor and much more", "userId": 2}'
```

#### Response:

##### When you GET and request the new change to the post
```
HTTP/1.1 200 OK
X-Powered-By: Express
Access-Control-Allow-Origin: *
Content-Type: application/json; charset=utf-8
Content-Length: 128
ETag: W/"80-T1d9JmvmV4Ne6ydajw5r0w0mD3I"
Date: Mon, 27 Apr 2020 09:16:04 GMT
Via: 1.1 google

{"_id":"5e806d9f42fbde006b6b9ed0","userId":2,"id":2,"title":"Inspirator, investor and much more","body":"Dean Graziosi","__v":0

```

---------------------

##### Pipe it to jq by removing ```-i``` and add ```| jq``` to the end of the request, for it to show the response in JSON format:

```
curl -H "Content-Type:application/json" http://api.softhouse.rocks/posts/2 | jq
```

##### Response JSON format:

```json
{
  "_id": "5e806d9f42fbde006b6b9ed0",
  "userId": 2,
  "id": 2,
  "title": "Inspirator, investor and much more",
  "body": "Dean Graziosi",
  "__v": 0
}
```
--------------

### HTTP Methods: DELETE
---------------------
#### The DELETE method deletes the specified resource.

##### Removes the object you chose to delete

/posts
```
curl -X DELETE http://api.softhouse.rocks/posts/3
```

#### Response:

##### When you GET and request the new change to the post
```
HTTP/1.1 200 OK
X-Powered-By: Express
Access-Control-Allow-Origin: *
Content-Length: 0
ETag: W/"0-2jmj7l5rSw0yVb/vlWAYkK/YBwk"
Date: Mon, 27 Apr 2020 09:48:09 GMT
Via: 1.1 google
```
--------------