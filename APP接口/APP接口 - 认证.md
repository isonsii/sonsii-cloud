# 1 登录

## url

`POST /auth/auth/customer/user/login`

## 请求头

| 请求头          | 类型     | 值                |
| ------------ | ------ | ---------------- |
| content-type | String | application/json |

## 请求体

| 参数        | 类型     | 说明       |
| --------- | ------ | -------- |
| clientKey | String | 客户端唯一标识键 |
| username  | String | 用户名      |
| password  | String | 密码       |

## 响应

| 键值                | 类型     | 说明           |
| ----------------- | ------ | ------------ |
| code              | Int    | 接口返回码        |
| msg               | String | 接口返回描述信息【参考】 |
| data              | Json   | 返回数据，Json对象  |
| data.token        | String | 用于后续请求接口的凭证  |
| data.refreshToken | String | 用于刷新token    |
| data.userId       | Int    | 用户ID         |

# 2 退出登录

## url

`POST /auth/auth/customer/user/logout`

## 请求头

| 请求头          | 类型     | 值                                |
| ------------ | ------ | -------------------------------- |
| token        | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |
| content-type | String | application/json                 |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |

# 3 刷新token

## url

`PUT /auth/auth/customer/user/refresh/token`

## 请求头

token的值是登录接口返回响应中的refreshToken。

| 请求头   | 类型     | 值                                |
| ----- | ------ | -------------------------------- |
| token | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |