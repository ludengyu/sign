# 考勤API

{% api-method method="get" host="http://120.27.226.1:8080/sign-server" path="/api/sign/sync/status" %}
{% api-method-summary %}
 同步状态
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="deptId" type="string" required=true %}
 机构ID
{% endapi-method-parameter %}

{% api-method-parameter name="userId" type="string" required=true %}
 用户ID
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "data": {
        "arrivalTime": "2018-12-29 08:30:00", // 上班时间，白名单内或者节假日时为空
        "leaveTime": "2018-12-29 17:30:00", // 下班时间，白名单内或者节假日时为空
        "serverTime": "2018-12-29 15:44:36", // 服务器时间
        "type": "-1" // 类型(-1:签到,0:签退,1:已结束)
    },
    "msg": "ok", // ok,fail,empty
    "ret": 200 // 200,500,404
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="http://120.27.226.1:8080/sign-server" path="/api/sign/logs" %}
{% api-method-summary %}
 提交记录
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-form-data-parameters %}
{% api-method-parameter name="userId" type="string" required=true %}
 用户ID
{% endapi-method-parameter %}

{% api-method-parameter name="userName" type="string" required=true %}
 用户姓名
{% endapi-method-parameter %}

{% api-method-parameter name="deptId" type="string" required=true %}
 机构编码
{% endapi-method-parameter %}

{% api-method-parameter name="deptName" type="string" required=true %}
 机构名称
{% endapi-method-parameter %}

{% api-method-parameter name="address" type="string" required=true %}
 地址
{% endapi-method-parameter %}

{% api-method-parameter name="lat" type="string" required=true %}
 经度
{% endapi-method-parameter %}

{% api-method-parameter name="lon" type="string" required=true %}
 纬度
{% endapi-method-parameter %}

{% api-method-parameter name="remark" type="string" required=false %}
 备注
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=true %}
 类型\(0:签到,1:签退\)
{% endapi-method-parameter %}

{% api-method-parameter name="imei" type="string" required=true %}
 设备唯一标识，后期审计用
{% endapi-method-parameter %}

{% api-method-parameter name="attachment" type="string" required=true %}
 附件key
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
	"data": {
		"rank": 1 // 排名
	},
	"msg": "ok", // ok,fail
	"ret": 200 // 200,500
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="http://120.27.226.1:8080/sign-server" path="/api/sign/logs" %}
{% api-method-summary %}
 查询记录
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="userId" type="string" required=true %}
 用户ID
{% endapi-method-parameter %}

{% api-method-parameter name="startDate" type="string" required=true %}
 开始时间\(format:yyyy-MM-dd HH:mm:ss\)
{% endapi-method-parameter %}

{% api-method-parameter name="endDate" type="string" required=true %}
 结束时间\(format:yyyy-MM-dd HH:mm:ss\)
{% endapi-method-parameter %}

{% api-method-parameter name="pi" type="string" required=true %}
 分页页码\(0:查询全部\)
{% endapi-method-parameter %}

{% api-method-parameter name="ps" type="string" required=false %}
 分页大小
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
	"data": [
		{
			"address": "广泓大厦", // 地址
			"createTime": "2018-10-29 13:33:47", // 提交时间
			"deptId": "3007", // 机构编码-web
			"deptName": "开发7组", // 机构名称-web
			"id": 68, // 主键-web
			"imei": "869885037401936", // 设备标识
			"imgUrls": [ // 图片链接数组
			"http://120.27.226.1:8080/sign-server/api/attachment/F2F0520A60774EF39FE4C74CDA504A1D.png"
			],
			"lat": "31.270726", // 经度
			"lon": "120.743925", // 纬度
			"rank": 1, // 排名
			"type": "0", // 类型
			"userId": "jiangy2", // 用户ID-web
			"userName": "姜勇" // 用户名称-web
		},
		{
			"address": "广泓大厦",
			"createTime": "2018-10-26 14:10:44",
			"deptId": "3007",
			"deptName": "开发7组",
			"id": 64,
			"imei": "869885037401936",
			"imgUrls": [
			"http://120.27.226.1:8080/sign-server/api/attachment/9AEE639189C145D28FDAFC7C2110AF09.png"
			],
			"lat": "31.270727",
			"lon": "120.743924",
			"rank": 1,
			"remark": "哈哈哈哈好",
			"type": "0",
			"userId": "jiangy2",
			"userName": "姜勇"
		},
		{
			"address": "广泓大厦",
			"createTime": "2018-10-25 11:08:41",
			"deptId": "3007",
			"deptName": "开发7组",
			"id": 63,
			"imei": "869885037401936",
			"imgUrls": [
			"http://120.27.226.1:8080/sign-server/api/attachment/2C9B821004EE4AB2BAF77A5349090D86.png"
			],
			"lat": "31.270727",
			"lon": "120.743924",
			"rank": 1,
			"type": "0",
			"userId": "jiangy2",
			"userName": "姜勇"
		}
	],
	"msg": "ok", // ok,fail,empty
	"ret": 200, // 200,500,404
	"total": 3 // 全部记录，非本页返回大小
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



