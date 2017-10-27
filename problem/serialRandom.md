## Get single or multiple random problem by serial

```
GET /problem/serial/{serial-number}/{num}
```

### Description
- get random single/multiple problem(s) by a given serial number

### Headers
<table>
<tr>
  <td>Name</td>
  <td>Required</td>
  <td>Description</td>
</tr>
<tr>
  <td>Authorization</td>
  <td>yes</td>
  <td>api access token</td>
</tr>
</table>

### Parameters
<table>
<tr>
  <td>Name</td>
  <td>Required</td>
  <td>Type</td>
  <td>Description</td>
</tr>
<tr>
  <td>serial-number</td>
  <td>yes</td>
  <td>integer [9]</td>
  <td>serial number (this should be given by owner (EMath)</td>
</tr>
<tr>
  <td>num</td>
  <td>yes</td>
  <td>integer</td>
  <td>problem amount to get</td>
</tr>
</table>

### Reply
no Access-Token : `403` 
wrong Access-Token : `401`  
no problem matching the request properties: `404`

Success: `Content-Type: application/json`  

#### Example
**Request Example**

```json
curl -H "Authorization: nico_nico_ni_love_arrow_shoot" https://api.emath.math.ncu.edu.tw/problem/serial/125252002/1
```

**Reply Example**

```json
{
  "problem":[
    {
      "problemNum":"111011017_011",
      "problemLink":"0b11479b6354d0c5ac3d4ffd1980cd09",
      "ansLink":"9ab8a119b144f0040bfc0490a5b7c30e",
      "answer":"1",
      "choices":"3"
    }
  ]
}
```
