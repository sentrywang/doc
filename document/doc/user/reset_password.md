# 重置密码

用户在登录页面点击忘记密码，可以进行密码重置操作。

1. 点击忘记密码，进入重置密码页面；
2. 在重置密码页面，输入邮箱，点击提交；
3. 服务器向用户输入的邮箱发送邮件，邮件里包含密码重置链接；
4. 用户打开邮箱，点击邮件中的链接；
5. 进入重设密码页面；
6. 用户在重设密码页面，输入两次新的密码，点击提交；
7. 服务器进行必要检查，修改用户密码为新密码，或者返回错误提示。

## 请求重置密码

用户输入电子邮箱，服务器向该邮箱发送重设密码链接。

**URL** `POST /user/send-reset-password-email/`

**Request body**
```json
{
  "email": "user@example.com"
}
```

**Response**

```json
{
  "code": "OK",
  "msg": "成功"
}
```


## 用户重设密码

前端重设密码页面的路由为：`/user/reset-password?id=xxxxxxxxxx&token=xxxxxxxxxx`

用户输入两次新密码后，将用户输入的内容及 path 中的 `id` 和 `token` 字段发送给服务器。

**URL** `POST /user/reset-password/`

**Request body**
```json
{
  "password": "pas5sW0rd1",
  "password_r": "pas5sW0rd1",
  "id": "xxxxxxxxx",
  "token": "xxxxxxxxxxxxx"
}```

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
| password | `String` | 密码 | *required |
| password_r | `String` | 重复密码 | *required |
| id | `String` | path 中的 id 参数 | *required |
| token | `String` | path 中的 token 参数 | *required |
