##Get problem/answer image content
```
GET /problem/{code}
```
> Description
- Get problem content image 

###Parameters
<table>
<tr>
  <td>Name</td>
  <td>Required</td>
  <td>Type</td>
  <td>Description</td>
</tr>
<tr>
  <td>code</td>
  <td>yes</td>
  <td>string</td>
  <td>problemCode or ansCode</td>
</tr>
</table>

###Reply
no image matching the request code: `404`  
Success: `Content-Type: image/jpeg`  

###Example
**Request Example**
```json
curl https://api.emath.math.ncu.edu.tw/problem/o8o_yi_mi_wa_ka_nai  
```
