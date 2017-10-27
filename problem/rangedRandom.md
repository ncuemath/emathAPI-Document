## Get single or multiple problem in range

```
GET /problem/random/range/{grade}/{semester}/{unit}/{difficulty}/{num}
```

### Description
- get random single/multiple problem in range (grade/semester/unit/difficulty)

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
  <td>grade</td>
  <td>yes</td>
  <td>integer [1-6]</td>
  <td>None</td>
</tr>
<tr>
  <td>semester</td>
  <td>yes</td>
  <td>integer [1-2]</td>
  <td>None</td>
</tr>
<tr>
  <td>unit</td>
  <td>yes</td>
  <td>integer [1-12]</td>
  <td>None</td>
</tr>
<tr>
  <td>difficulty</td>
  <td>yes</td>
  <td>integer [1-8]</td>
  <td>None</td>
</tr>
<tr>
  <td>num</td>
  <td>yes</td>
  <td>integer</td>
  <td>problem amount to get</td>
</tr>
</table>

#### Difficulty Table
<table>
<tr>
  <td>value</td>
  <td>Difficulty</td>
</tr>
<tr>
  <td>1</td>
  <td>easy</td>
</tr>
<tr>
  <td>2</td>
  <td>normal</td>
</tr>
<tr>
  <td>3</td>
  <td>hard</td>
</tr>
<tr>
  <td>4</td>
  <td>challenge (expert)</td>
</tr>
<tr>
  <td>5</td>
  <td>all type easy</td>
</tr>
<tr>
  <td>6</td>
  <td>all type normal</td>
</tr>
<tr>
  <td>7</td>
  <td>all type hard</td>
</tr>
<tr>
  <td>8</td>
  <td>all type challenge (expert)</td>
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
curl -H "Authorization: nico_nico_ni_love_arrow_shoot" https://api.emath.math.ncu.edu.tw/problem/random/range/1/1/1/1/1
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

**Request Example**
```json
curl -H "Authorization: nozomi_power_ju_ryu_Xpopowo" https://api.emath.math.ncu.edu.tw/problem/random/range/1/1/1/1/3
```

**Reply Example**
```json
{
  "problem":[
    {
      "problemNum":"111011016_017",
      "problemLink":"07be3649eb707b713576eac0949e0bbc",
      "ansLink":"2e424fb203baae697f83e7dbefbf236c",
      "answer":"2",
      "choices":"3"
    },
    {
      "problemNum":"111011021_028",
      "problemLink":"62f8c1cdbdec013eda609f9bace10521",
      "ansLink":"4b308f5511622bd7285290e29ccb8605",
      "answer":"3",
      "choices":"4"
    },
    {
      "problemNum":"111011009_028",
      "problemLink":"52cc77efc75887a3f9821ee83a29aec2",
      "ansLink":"a6101c38d08a652ee2d0c0ef5e437b7f",
      "answer":"4",
      "choices":"4"
    }
  ]
}
```
