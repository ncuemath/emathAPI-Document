##Problem API
####Host: api.emath.math.ncu.edu.tw

###Method Overview

Get single Problem in range:
```
/problem/single/{grade}/{semester}/{unit}/{difficulty}
```
Get Multible Problems in range :
```
/problem/multi/{grade}/{semester}/{unit}/{difficulty}/{num}
```
Get Problem/Answer Image Content :
```
/problem/getContent/{code}
```

##Methods
###Get single Problem in range:

####Request
```
GET /problem/single/{grade}/{semester}/{unit}/{difficulty}
```

**Parameters**

* grade : integer [1-6]
* semester : integer [1-2]
* unit : integer [1-12]
* difficulty : integer [1-8]
	* 1 : easy
	* 2 : normal
	* 3 : hard
	* 4 : challenge (expert)
	* 5 - 8 : 1 - 4 random
####Reply
```
Content-Type: application/json
```
**Return**

* problemNum : serial number of problem
* problemCode : problem image content code
* ansCode : answer image content code
* answer : answer
* choices : total choices

**Example**
```json
{"problemNum":"111011017_007","problemLink":"e3e2064b655867d14cc287d53105378a","ansLink":"03a58230db7b99b469401da341db7950","answer":"1","choices":"3"}
```
###Get multi. Problems in range:

####Request
```
GET /problem/multiple/{grade}/{semester}/{unit}/{difficulty}/{num}
```

**Parameters**

* grade : integer [1-6]
* semester : integer [1-2]
* unit : integer [1-12]
* difficulty : integer [1-8]
	* 1 : easy
	* 2 : normal
	* 3 : hard
	* 4 : challenge (expert)
	* 5 - 8 : 1 - 4 random
* num : problem amount to get
####Reply
```
Content-Type: application/json
```
**Return**

* problemNum[] : serial number of problem
* problemCode[] : problem image content code
* ansCode[] : answer image content code
* answer[] : answer
* choices[] : total choices

####Example
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
```
Content-Type: image/jpeg
```
**Return**

an image content of assigned code
