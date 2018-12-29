# 登录用户修改用户名和密码

登录用户在个人设置页面可以修改自己的用户名和密码。新的用户名不能与其他用户的用户名重复；修改过密码之后，自动登出其他session。


## 修改用户名

**URL** `POST /user/change-username/`

**Request body**
```json
{
  "username": "new_fancy_username"
}
```

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

## 修改密码

**URL** `POST /user/change-password/`

**Request body**
```json
{
  "password": "old_password",
  "new_password": "new_password",
  "new_password_r": "new_password_repeat"
}
```

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
