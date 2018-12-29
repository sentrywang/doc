# 管理员登出

## 前段路由

**URL**  `/user/get-info`

## 后端接口

**URL**  `GET /user/profile/`



**Response**
```json
{
  "code": "OK",
  "msg": "成功",
  "data": {
    "uid": 3,
    "username": "username",
    "email": "email@explem.com",
    "email_verified": true,
    "create_time": "2018-06-13 16:37:49",
    "last_login": 1529910977,
    "last_login_ip": "127.0.0.1"
  }
}
```