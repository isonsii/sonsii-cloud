# 1 分页获取设备列表

## url

`GET /device/device/user/device/page`

## 请求头

| 请求头   | 类型     | 值                                |
| ----- | ------ | -------------------------------- |
| token | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |

## 请求参数

| 参数       | 类型  | 说明   |
| -------- | --- | ---- |
| page     | Int | 页码   |
| pageSize | Int | 每页数量 |

## 响应

| 键值                      | 类型       | 说明            |
| ----------------------- | -------- | ------------- |
| code                    | Int      | 接口返回码         |
| msg                     | String   | 接口返回描述信息      |
| data                    | Json     | 返回数据，Json对象   |
| data.records            | JsonList | 返回数据，对象列表     |
| data.total              | Int      | 总记录条数         |
| data.size               | Int      | 当前页面大小        |
| data.current            | Int      | 当前页码          |
| data.pages              | Int      | 总页数           |
| data.records.udid       | String   | 设备唯一标识        |
| data.records.pid        | String   | 设备所属产品id      |
| data.records.deviceName | String   | 设备名称          |
| data.records.bindTime   | Date     | 设备最后一次绑定用户的时间 |

# 2 获取设备详情

## url

`GET /device/device/tenant/user/device/info`

## 请求头

| 请求头   | 类型     | 值                                |
| ----- | ------ | -------------------------------- |
| token | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |

## 请求参数

| 参数   | 类型     | 说明     |
| ---- | ------ | ------ |
| udid | String | 设备UDID |

## 响应

| 键值                       | 类型     | 说明                                                 |
| ------------------------ | ------ | -------------------------------------------------- |
| code                     | Int    | 接口返回码                                              |
| msg                      | String | 接口返回描述信息                                           |
| data                     | Json   | 返回数据，Json对象                                        |
| data.udid                | String | 设备UDID                                             |
| data.pid                 | String | 产品UDID                                             |
| data.deviceName          | String | 设备名称                                               |
| data.bindTime            | Date   | 设备最后一次绑定用户的时间                                      |
| data.attrs               | Json   | 设备属性                                               |
| data.attrs.connectState  | Int    | 设备连接状态                                             |
| data.attrs.activityState | Int    | 设备活跃状态，当connectState和activityState都为1时，可以认为设备在线且活跃 |
| data.attrs.sleep         | Int    | 休眠唤醒状态：0正常1休眠                                      |

# 3 获取设备属性数据

## url

`GET /device/device-attribute/user/device`

## 请求头

| 请求头   | 类型     | 值                                |
| ----- | ------ | -------------------------------- |
| token | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |

## 请求参数

| 参数   | 类型     | 说明     |
| ---- | ------ | ------ |
| udid | String | 设备UDID |

## 响应

| 键值   | 类型     | 说明          |
| ---- | ------ | ----------- |
| code | Int    | 接口返回码       |
| msg  | String | 接口返回描述信息    |
| data | Json   | 返回数据，Json对象 |

# 4 设备告警消息列表

## url

`POST /device/device-telemetry/user/all`

## 请求头

| 请求头          | 类型     | 值                                |
| ------------ | ------ | -------------------------------- |
| token        | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |
| content-type | String | application/json                 |

## 请求参数

| 参数      | 类型     | 说明                                   |
| ------- | ------ | ------------------------------------ |
| keys    | String | 告警类型键值key列表，可以通过逗号连接一次查询多个，但最长不超过256 |
| limit   | Int    | 数量限制                                 |
| ossKeys | String | 固定值picDict                           |

## 请求体

| 参数      | 类型     | 说明       |
| ------- | ------ | -------- |
| udid    | String | 设备UDID   |
| startTs | Long   | 开始时间【毫秒】 |
| endTs   | Long   | 结束时间【毫秒】 |

## 响应

| 键值         | 类型       | 说明                          |
| ---------- | -------- | --------------------------- |
| code       | Int      | 接口返回码                       |
| msg        | String   | 接口返回描述信息                    |
| data       | JsonList | 返回数据，对象列表                   |
| data.key   | String   | 告警消息键值                      |
| data.ts    | Long     | 告警时间戳(云端)，设备触发时间详见value中内容。 |
| data.udid  | String   | 设备UDID                      |
| data.value | String   | 告警内容                        |

# 5 删除设备

## url

`DELETE /device/device/user/device`

## 请求头

| 请求头          | 类型     | 值                                |
| ------------ | ------ | -------------------------------- |
| token        | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |
| content-type | String | application/json                 |

## 请求参数

| 参数   | 类型     | 说明     |
| ---- | ------ | ------ |
| udid | String | 设备UDID |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |

# 6 修改设备名称

## url

`PUT /device/device/user/device`

## 请求头

| 请求头          | 类型     | 值                                |
| ------------ | ------ | -------------------------------- |
| token        | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |
| content-type | String | application/json                 |

## 请求参数

| 参数         | 类型     | 说明     |
| ---------- | ------ | ------ |
| udid       | String | 设备UDID |
| deviceName | String | 设备名称   |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |

# 7 设备配置

## url

`POST /device/device-config/user/cloud-request/device-config`

## 请求头

| 请求头          | 类型     | 值                                |
| ------------ | ------ | -------------------------------- |
| token        | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |
| content-type | String | application/json                 |

## 请求体

| 参数   | 类型     | 说明        |
| ---- | ------ | --------- |
| udid | String | 设备UDID    |
| cmd  | String | 设备配置指令字符串 |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |

## url

`POST /device/device-ctrl/user/exe-cmd/device-ctrl`

## 请求头

| 请求头          | 类型     | 值                                |
| ------------ | ------ | -------------------------------- |
| token        | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |
| content-type | String | application/json                 |

## 请求体

| 参数   | 类型     | 说明        |
| ---- | ------ | --------- |
| udid | String | 设备UDID    |
| cmd  | String | 设备控制指令字符串 |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |

# 9 读取设备信息指令

## url

`POST /device/device-get-info/user/cloud-request/device-info`

## 请求头

| 请求头          | 类型     | 值                                |
| ------------ | ------ | -------------------------------- |
| token        | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |
| content-type | String | application/json                 |

## 请求体

| 参数   | 类型     | 说明          |
| ---- | ------ | ----------- |
| udid | String | 设备UDID      |
| cmd  | String | 读取设备信息指令字符串 |

## 响应

| 键值   | 类型     | 说明       |
| ---- | ------ | -------- |
| code | Int    | 接口返回码    |
| msg  | String | 接口返回描述信息 |