# 用户注册

## 前端路由

注册链接：`/user/signup`

## 后端接口

**URL** `POST /user/signup/`

**Request body**
```json
{
  "username": "username",
  "email": "user@gmail.com",
  "password": "pas5sW0rd",
  "password_r": "pas5sW0rd",
  "captcha_key": "7f225c66a9bc43f536b045436cef73d22d986760",
  "captcha_code": "As8h",
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
| email | `String` | 电子邮箱 | *required |
| password | `String` | 密码 | *required |
| password_r | `String` | 重复密码 | *required |
| captcha_key | `String` | 图形验证码 key | *required |
| captcha_code | `String` | 图形验证码用户识别值 | *required |
