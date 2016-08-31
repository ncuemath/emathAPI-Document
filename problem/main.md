##Problem API
####Protocol: HTTPs
####Host: api.emath.math.ncu.edu.tw
####Require: access_token
If your organization wants to use our api, please contact EMath(子由數學小學堂） @ Department of Mathematics, NCU.

###Method Overview

Get single Problem in range:
```
/problem/single
```
Get Multible Problems in range :
```
/problem/multiple
```
Get Problem/Answer Image Content :
```
/problem/getContent/{code}
```

##Methods

###Get single Problem in range:

####Request
```
POST /problem/single
```

**Header**
Access-Token: api access token

**Data**
* grade : integer [1-6]
* semester : integer [1-2]
* unit : integer [1-12]
* difficulty : integer [1-8]
	* 1 : easy
	* 2 : normal
	* 3 : hard
	* 4 : challenge (expert)
	* 5 : all type easy
	* 6 : all type normal
	* 7 : all type hard
	* 8 : all type challenage (expert)

####Reply
wrong Access-Token : `403`
no problem matching the request properties: `404` 
Success: `Content-Type: application/json`

**Success Return**

* problemNum : serial number of problem
* problemCode : problem image content code
* ansCode : answer image content code
* answer : answer
* choices : total choices

####Example
**Request Example**
```json
curl -X POST -H "Access-Token: nico_nico_ni_love_arrow_shoot" --data "grade=1" --data "semester=1" --data "unit=1" --data "difficulty=1" https://api.emath.math.ncu.edu.tw/problem/single
```
**Reply Example**
```json
{"problemNum":"111011017_007","problemLink":"e3e2064b655867d14cc287d53105378a","ansLink":"03a58230db7b99b469401da341db7950","answer":"1","choices":"3"}
```

###Get multi. Problems in range:

####Request
```
POST /problem/multiple
```

**Header**
Access-Token: api access token

**Data**
* grade : integer [1-6]
* semester : integer [1-2]
* unit : integer [1-12]
* difficulty : integer [1-8]
	* 1 : easy
	* 2 : normal
	* 3 : hard
	* 4 : challenge (expert)
	* 5 : all type easy
	* 6 : all type normal
	* 7 : all type hard
	* 8 : all type challenage (expert)
* num : problem amount to get

####Reply
wrong Access-Token : `403`
no problem matching the request properties: `404` 
Success: `Content-Type: application/json`

**Success Return**
* problemNum[] : serial number of problem
* problemCode[] : problem image content code
* ansCode[] : answer image content code
* answer[] : answer
* choices[] : total choices

####Example
**Request Example**
```json
curl -X POST -H "Access-Token: nozomi_power_ju_ryu_Xpopowo" --data "grade=1" --data "semester=1" --data "unit=1" --data "difficulty=1" --data "num=3" https://api.emath.math.ncu.edu.tw/problem/multiple
```

**Reply Example**
```json
{"problemNum":["111011010_016","111011021_029","111011007_028"],"problemLink":["b4479eba42507f41721e01380e8fcbbb","d1805b1dd19d6684e9ff812580a7c97d","fd1537b9fa0aee541b918df1ff25373b"],"ansLink":["21891e817bc91da38cc552db570afc5c","3745381683a305358f553b82e02407de","b63d53ec449d038d152b3d5656adb83d"],"answer":["1","2","2"],"choices":["3","4","4"]}
```

###Get problem/answer image content

####Request
```
GET /problem/getContent/{code}
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
curl https://api.emath.math.ncu.edu.tw/problem/getContent/o8o_yi_mi_wa_ka_nai
```