# EnableSmartAGDpiMonitor

调用EnableSmartAGDpiMonitor开启智能接入网关实例应用识别DPI（Deep Packet Inspection）监控功能。

## 前提条件

-   您已经开启智能接入网关实例的DPI功能。更多信息，请参见[UpdateSmartAGDpiAttribute](~~196146~~)。
-   您已经开通了日志服务。具体操作，请参见[快速入门](~~54604~~)。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Smartag&api=EnableSmartAGDpiMonitor&type=RPC&version=2018-03-13)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|EnableSmartAGDpiMonitor|要执行的操作。

 取值：**EnableSmartAGDpiMonitor**。 |
|RegionId|String|是|cn-shanghai|智能接入网关实例所属地域ID。 |
|SlsLogStore|String|是|test2|您已创建的Logstore实例名称。 |
|SlsProjectName|String|是|test1|您已创建的Project实例名称。 |
|SmartAGId|String|是|sag-vwmylqc9521p5l\*\*\*\*|智能接入网关实例ID。 |
|ClientToken|String|否|02fb3da4-130e-11e9\*\*\*\*|客户端Token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过64个ASCII字符。 |
|DryRun|Boolean|否|true|是否只预检此次请求。取值：

 -   **true**：表示只预检此次请求合法性，不会开启或关闭智能接入网关实例的DPI功能。检查项包括是否填写了必需参数、请求格式、实例状态等。如果检查不通过，则返回对应错误；如果检查通过，则返回对应请求ID。
-   **false**（默认）：表示发送正常请求，通过检查后直接开启智能接入网关实例的DPI监控功能。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|64966488-B3E3-41E2-9570-4596117EC12E|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=EnableSmartAGDpiMonitor
&RegionId=cn-shanghai
&SlsLogStore=test2
&SlsProjectName=test1
&SmartAGId=sag-vwmylqc9521p5l****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<EnableSmartAGDpiMonitorResponse>
  <RequestId>64966488-B3E3-41E2-9570-4596117EC12E</RequestId>
</EnableSmartAGDpiMonitorResponse>
```

`JSON` 格式

```
{"RequestId":"64966488-B3E3-41E2-9570-4596117EC12E"}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidSmartAGId.NotFound|The specified SmartAGId does not exist.|根据SmartAGId未找到对应实例。|
|403|FeatureNotSupport|The current edition of the smart access gateway does not support this feature.|智能接入网关当前版本不支持该功能特性。|
|403|FeatureNotSupportForActiveSmartAG|The current edition of the active smart access gateway does not support this feature.|主智能接入网关的当前版本不支持该功能特性。|
|403|FeatureNotSupportForStandBySmartAG|The current edition of the standby smart access gateway does not support this feature.|备智能接入网关的当前版本不支持该功能特性。|
|400|CreateProjectFailed|Failed to create the SLS project.|创建SLS Project失败。|
|400|IncorrectStatus|The instance status is invalid.|实例状态非法。|

访问[错误中心](https://error-center.aliyun.com/status/product/Smartag)查看更多错误码。

