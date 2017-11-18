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
