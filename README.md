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
**Return Data(json):**
```
{
    'token': string 
    'code' : // 200 或 404 或 403 
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

**POST Data(json):**
```
{
    'username': string,    //用户名
    'password': string     //用户密码
}
```

**Return Data(json):**
```
{
    'created':id           //用户id
    'code' : int          // 200 或403 
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
    'rate' : int // 分数 
    'tag' : int // tag id 
    'question' : [int] // 所问问题的id列表
    'answer' : [string] // 所问问题对应的回答
}
``` 

**Return Data(json):**
```
{
    'created':id           // 日记id 
    'code' : int           // 200 或 403 
    'p_url' : string        // 推荐图片的URL
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

**PUT Data(json)**
```
{
    'title' : string, 
    'tag' : int // tag id 
    'rate' : int // 分数 
    'question' : [int] // 所问问题的id列表
    'answer' : [string] // 所问问题对应的回答
}
``` 

**Return Data(json):**
```
{
    'edit':id           // 日记id 
    'code':int          //  200, 403, 404 
    'p_url':string      //  图片URL
}
```
**Status Code**
```
200 // OK
403  // 用户验证失败
404 // 日记不存在 
```
*** 

## **get diary** 
```
获取最近14篇的日记 
```
|URL | Header | Methods | 
|-- |--| --| 
|/api/diary/ | Content-Type:application/json, token:string | GET | 

**URL Params:None** 

**POST Data(json):None**

**Return Data(json):**
```
{
  [ 'title' : string, 
    'tag' : int // tag id 
    'date' : time // 时间 
    'rate' : int // 分数 
    'question' : [int] // 所问问题的id列表
    'answer' : [string] // 所问问题对应的回答
   ] , 
   'code' : int  // 200 或403
}
``` 
**Status Code**
```
200 // OK
403  // 用户验证失败
```

*** 
