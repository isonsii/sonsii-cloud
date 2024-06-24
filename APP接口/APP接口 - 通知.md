# 1 绑定极光客户端标识

## url

`POST /sms/sms/user/ration/mapping`

## 请求头

| 请求头          | 类型     | 值                                |
| ------------ | ------ | -------------------------------- |
| token        | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |
| content-type | String | application/json                 |

## 请求体

| 参数       | 类型     | 说明            |
| -------- | ------ | ------------- |
| rationId | String | 极光SDK获取的客户端ID |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |

# 2 极光推送开启/关闭

## url

`PUT /sms/sms/user/jpush/push/status`

## 请求头

| 请求头          | 类型     | 值                                |
| ------------ | ------ | -------------------------------- |
| token        | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |
| content-type | String | application/json                 |

## 请求体

| 参数       | 类型     | 说明            |
| -------- | ------ | ------------- |
| pushable | int    | 1开启 0关闭       |
| rationId | String | 极光SDK获取的客户端ID |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |