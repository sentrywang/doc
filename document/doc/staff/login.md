# 管理员登陆

## 前端路由

登陆链接： `/staff/login`

## 后端接口

**URL** `POST /staff/login/`

**Request body**
```json
{
"username": "username",
"password": "password",
"captcha_key": "captcha_key",
"captcha_code": "captcha_code"
}
```

**Response**
```json
{
  "code": "OK",
  "msg": "成功"
}
```

**字段说明**

| Param | Type | Description | Required? |
| --- | --- | --- | --- |
| username | `String` | 用户名 | *required |
| password | `String` | 密码 | *required |
| captcha_key | `String` | 图形验证码 key | *required |
| captcha_code | `String` | 图形验证码用户识别值 | *required |
