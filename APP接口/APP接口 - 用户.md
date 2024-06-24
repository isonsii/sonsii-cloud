# 1 重置密码

## url

`POST /user/customer/user/reset/password`

## 请求头

| 请求头          | 类型     | 值                |
| ------------ | ------ | ---------------- |
| content-type | String | application/json |

## 请求体

| 参数           | 类型     | 说明                         |
| ------------ | ------ | -------------------------- |
| clientKey    | String | 客户端唯一标识键                   |
| phone        | String | 手机号                        |
| newPassword  | String | 新密码(客户端对密码进行转换/加密/摘要处理后提交) |
| validateCode | String | 验证码                        |
| registerType | Int    | 类型固定为1                     |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |

# 2 用户注册

## url

`POST /user/customer/user/register`

## 请求头

| 请求头          | 类型     | 值                |
| ------------ | ------ | ---------------- |
| content-type | String | application/json |

## 请求体

| 参数           | 类型     | 说明                        |
| ------------ | ------ | ------------------------- |
| clientKey    | String | 客户端唯一标识键                  |
| country      | String | 国家地区编码，固定为CN              |
| registerType | Int    | 类型固定为1                    |
| phone        | String | 手机号                       |
| username     | String | 用户名                       |
| password     | String | 密码(客户端对密码进行转换/加密/摘要处理后提交) |
| verifyCode   | String | 验证码                       |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |

# 3 获取验证码

## url

`GET /user/sms/customer/user/phone/sms/code`

## 请求参数

| 参数        | 类型     | 说明                       |
| --------- | ------ | ------------------------ |
| clientKey | String | 客户端唯一标识键                 |
| phone     | String | 手机号                      |
| useType   | Int    | 类型(1:用户注册 2:修改密码 3:找回密码) |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |

# 4 获取用户详细信息

## url

`GET /user/customer/user/detail`

## 请求头

| 请求头   | 类型     | 值                                |
| ----- | ------ | -------------------------------- |
| token | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |

## 响应

| 键值              | 类型     | 说明          |
| --------------- | ------ | ----------- |
| code            | Int    | 接口返回码       |
| msg             | String | 接口返回描述信息    |
| data            | Json   | 返回数据，Json对象 |
| data.id         | Int    | 用户ID        |
| data.tenantId   | Int    | 租户ID        |
| data.username   | String | 用户名         |
| data.nickName   | String | 密码          |
| data.phone      | String | 手机号         |
| data.createTime | Date   | 用户创建时间      |

# 5 获取通知告警开关

## url

`GET /user/user/property/alarm-switch`

## 请求头

| 请求头   | 类型     | 值                                |
| ----- | ------ | -------------------------------- |
| token | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |

## 响应

| 键值   | 类型     | 说明                  |
| ---- | ------ | ------------------- |
| code | Int    | 接口返回码               |
| msg  | String | 接口返回描述信息            |
| data | Int    | 返回数据，告警开关，固定值on/off |

# 6 设置通知告警开关属性

## url

`PUT /user/user/property/alarm-switch`

## 请求头

| 请求头          | 类型     | 值                                |
| ------------ | ------ | -------------------------------- |
| token        | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |
| content-type | String | application/json                 |

## 请求体

| 参数    | 类型     | 说明             |
| ----- | ------ | -------------- |
| value | String | 开关属性，固定值on/off |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |

# 7 设置用户基本信息

## url

`PUT /user/customer/user/update`

## 请求头

| 请求头          | 类型     | 值                                |
| ------------ | ------ | -------------------------------- |
| token        | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |
| content-type | String | application/json                 |

## 请求体

| 参数       | 类型     | 说明  |
| -------- | ------ | --- |
| nickName | String | 昵称  |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |

# 8 生成设备操作验证码

## url

`POST /user/customer/user/provision`

## 请求头

| 请求头          | 类型     | 值                                |
| ------------ | ------ | -------------------------------- |
| token        | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |
| content-type | String | application/json                 |

## 请求参数

| 参数            | 类型  | 说明                    |
| ------------- | --- | --------------------- |
| provisionType | Int | 1.设备入网(生成二维码，设备扫码APP) |

## 响应

| 键值   | 类型     | 说明         |
| ---- | ------ | ---------- |
| code | Int    | 接口返回码      |
| msg  | String | 接口返回描述信息   |
| data | String | 用于后续操作的验证码 |