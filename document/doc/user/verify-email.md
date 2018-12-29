# 验证邮箱

在用户注册后，系统会向用户填写的 email 地址中发送一封注册验证邮件，其中验证链接的 path 为：
`/user/verify-email?id=<XXXXXX>&token=<XXXXXX>`。

用户点击链接进入网站，在该路由下，前端代码应获取 URL 中的 `id` 和 `token` 字段，向后端发送请求，验证其有效性。

## 1. 验证 token

**URL** `POST /user/verify-email/`

**Request body**
```json
{
  "id": "xxxxx",
  "token": "xxxxx"
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
| id | `String` | 用户id | *required |
| token | `String` | token | *required |

## 2. 重发验证链接
如果当用户点击链接后，链接已过期，应该有重发验证邮件的功能。

**URL** `POST /user/resend-verify-email/`

**Request body**

空 body

**Response**
```json
{
  "code": "OK",
  "msg": "成功"
}
```

- 如果服务器返回用户未登录，应跳转到登录界面让用户登录。
- 重发验证邮件的接口后台进行了频率限制，登录用户，每IP每分钟最多2次请求。
    