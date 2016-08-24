## Problem API
####Host: emath2.math.ncu.edu.tw

### Method Overview

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

#### Request
```
POST /problem/single/{grade}/{semester}/{unit}/{difficulty}
```

** parameters **

* grade : integer [1-6]
* semester : integer [1-2]
* unit : integer [1-12]
* difficulty : integer [1-8]
	* 1 : easy
	* 2 : normal
	* 3 : hard
	* 4 : challenge (expert)
	* 5 - 8 : 1 - 4 random
#### Reply
```
Content-Type: application/json
```
** Return **

* problemNum : serial number of problem
* problemCode : problem image content code
* ansCode : answer image content code
* answer : answer
* choices : total choices

###Get multi. Problems in range:

#### Request
```
POST /problem/multiple/{grade}/{semester}/{unit}/{difficulty}/{num}
```

** parameters **

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
#### Reply
```
Content-Type: application/json
```
** Return **

* problemNum[] : serial number of problem
* problemCode[] : problem image content code
* ansCode[] : answer image content code
* answer[] : answer
* choices[] : total choices

###Get problem/answer image content
#### Request
```
POST /problem/getContent/{code}
```

** parameters **

* code : problemCode or ansCode
#### Reply
```
Content-Type: image/jpeg
```
** Return **

an image content of assigned code