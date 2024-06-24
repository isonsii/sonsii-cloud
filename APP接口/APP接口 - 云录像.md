# 1 获取云录像列表

## url

`GET /assign/stream/record/list`

## 请求头

| 请求头   | 类型     | 值                                |
| ----- | ------ | -------------------------------- |
| token | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |

## 请求参数

| 参数    | 类型     | 说明                                             |
| ----- | ------ | ---------------------------------------------- |
| udid  | String | 设备唯一标识                                         |
| stime | Long   | 开始时间，从1970-01-01到当前的时间偏移秒数                     |
| etime | Long   | 结束时间，从1970-01-01到当前的时间偏移秒数<br/>与开始时间间隔最大不能超过一天 |

## 响应

| 键值              | 类型       | 说明               |
| --------------- | -------- | ---------------- |
| code            | Int      | 接口返回码            |
| msg             | String   | 接口返回描述信息         |
| data            | JsonList | 返回数据，对象列表        |
| data.stime      | Long     | 视频开始时间           |
| data.etime      | Long     | 视频结束时间           |
| data.recordType | Int      | 视频类型：1连续录像，2告警录像 |

# 2 获取云录像播放地址

## url

`GET /assign/stream/record/detail`

## 请求头

| 请求头   | 类型     | 值                                |
| ----- | ------ | -------------------------------- |
| token | String | xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx |

## 请求参数

| 参数    | 类型     | 说明                                             |
| ----- | ------ | ---------------------------------------------- |
| udid  | String | 设备唯一标识                                         |
| stime | Long   | 开始时间，从1970-01-01到当前的时间偏移秒数                     |
| etime | Long   | 结束时间，从1970-01-01到当前的时间偏移秒数<br/>与开始时间间隔最大不能超过一天 |

## 响应

| 键值          | 类型     | 说明                |
| ----------- | ------ | ----------------- |
| code        | Int    | 接口返回码             |
| msg         | String | 接口返回描述信息          |
| data        | Json   | 返回数据，Json对象       |
| data.url    | String | 视频播放HLS地址         |
| data.tlsUrl | String | 基于TLS加密的视频播放HLS地址 |