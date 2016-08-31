###Get problem/answer image content

####Request
```
GET /problem/{code}
```

**Parameters**
* code : problemCode or ansCode

####Reply
no image matching the request code: `404`  
Success: `Content-Type: image/jpeg`  

**Success Return**

an image content of assigned code

####Example
**Request Example**
```json
curl https://api.emath.math.ncu.edu.tw/problem/o8o_yi_mi_wa_ka_nai
```
