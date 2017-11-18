# **API Doc** 


## **login** 
|URL | Header | Methods| 
| :-- | :--| :-- | 
|/api/login/ | Content-Type:application/json | POST| 


**URL Params:None**


**POST Data(json)**
```
{
    'username':string,     //用户名
    'password':string    //用户密码 （base64加密）
}
```
**Return data(json):**
```
{
    'token': string 
}
```
**Status Code**
```
200 OK
404 用户不存在
403 密码错误 
```

*** 

## **signup** 

|URL|Header|Methods|
| :--- | :-- | :-- |
|/api/signup/ |Content-Type:application/json| POST|

**URL Params:None**

**POST data(json):**
```
{
    "username": string,    //用户名
    "password": string     //用户密码
}
```

**Return data(json):**
```
{
    "created":id           //用户id
}
```
**Status Code**
```
200 // OK
403  //用户名已存在 
```
*** 


## **add diary** 
|URL | Header | Methods | 
|-- |--| --| 
|/api/diary/ | Content-Type:application/json, token:string | POST | 

**URL Params:None**

**POST Data(json)**
```
{
    'title' : string , 
    'date' : time ,  
    'rate' : float // 分数 
    'tag' : int // tag id 
    'question' : [int] // 所问问题的id列表
    'answer' : [string] // 所问问题对应的回答
}
``` 

**Return data(json):**
```
{
    "created":id           // 日记id
}
```
**Status Code**
```
200 // OK
403  // 用户验证失败
```
*** 


## **edit diary** 

 ```
 修改用户某一天的日记（日记从时间得出） 
 ```
 
|URL | Header | Methods | 
|-- |--| --| 
|/api/diary/ | Content-Type:application/json, token:string | PUT | 

**URL Params:** 
``` 
{
    'date' : time, 
} 
``` 

**POST Data(json)**
```
{
    'title' : string , 
    'tag' : int // tag id 
    'question' : [int] // 所问问题的id列表
    'answer' : [string] // 所问问题对应的回答
}
``` 

**Return data(json):**
```
{
    "edit":id           // 日记id
}
```
**Status Code**
```
200 // OK
403  // 用户验证失败
404 // 日记不存在 
```
*** 
