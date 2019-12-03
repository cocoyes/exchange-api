# 隐私接口
---
注意：隐私接口需要进行签名验证。

## 获取账户ID
#### 限速规则：/
#### HTTP请求

``` vbscript
GET /user/get/accoun
```
#### 响应示例

``` json
{
    "data": {
        "memberId": 11
    },
    "code": 0,
    "message": "SUCCESS",
    "total": null
}
```






## 查询个人账户信息
#### 限速规则：/
#### HTTP请求

``` vbscript
GET /user/account
```

#### 参数
memberId		账户ID
 
#### 响应示例

``` json
{
	"data": [{
		"memberId": 11,
		"coinId": "USDT",
		"balance": 3207100.00831661,
		"frozenBalance": 363567515.696024,
		"address": "0x70edb9e59161006d53e2b5af0fcd9f45aa0120f2",
		"isLock": 0
	}],
	"code": 0,
	"message": "SUCCESS",
	"total": null
}
```





## 添加订单
#### 限速规则：/
#### HTTP请求

``` vbscript
GET /user/add_order
```

#### 参数
memberId		账户ID  
direction			订单方向，BUY买，SELL卖  
symbol			交易对 BTC/USDT
price				价格
amount			数量
type				订单类型，MARKET_PRICE市价，LIMIT_PRICE限价  
#### 响应示例

``` json
{
	"data": {
		"orderId": 9
	},
	"code": 0,
	"message": "SUCCESS",
	"total": null
}
```





## 查询订单详情
#### 限速规则：/
#### HTTP请求

``` vbscript
GET /user/query/order_detail
```

#### 参数
orderId		订单号

#### 响应示例

``` json
{
	"data": {
		"orderId": "E155722091722695",
		"memberId": 9,
		"type": "LIMIT_PRICE",
		"amount": 0.1899,
		"symbol": "BTC/USDT",
		"tradedAmount": 0.1899,
		"turnover": 1128.138031,
		"coinSymbol": "BTC",
		"baseSymbol": "USDT",
		"status": "COMPLETED",
		"direction": "BUY",
		"price": 5942.83,
		"triggerPrice": 0,
		"time": 1557220917226,
		"completedTime": 1557220917243,
		"canceledTime": null,
		"marginTrade": 0,
		"orderResource": "ROBOT",
		"detail": [{
			"orderId": "E155722091722695",
			"price": 5939.72,
			"amount": 0.079,
			"turnover": 469.23788,
			"fee": 0.00158,
			"time": 1557220917243
		}, {
			"orderId": "E155722091722695",
			"price": 5941.39,
			"amount": 0.1109,
			"turnover": 658.900151,
			"fee": 0.002218,
			"time": 1557220917263
		}],
		"amountStr": null,
		"priceStr": null,
		"completed": true
	},
	"code": 0,
	"message": null,
	"total": null
}
```





## 查询订单列表
#### 限速规则：/
#### HTTP请求

``` vbscript
GET /user/query/order
```

#### 参数
memberId		账户ID  
direction			订单方向，BUY买，SELL卖  
symbol			交易对 BTC/USDT
startTime		时间戳long  
endTime			时间戳long  
type				订单类型，MARKET_PRICE市价，LIMIT_PRICE限价  
pageNum			页编号
pageSize			每页大小

#### 响应示例

``` json
{
	"data": {
		"content": [{
			"orderId": "E155722139978120",
			"memberId": 9,
			"type": "LIMIT_PRICE",
			"amount": 0.51,
			"symbol": "ETH/USDT",
			"tradedAmount": 0,
			"turnover": 0,
			"coinSymbol": "ETH",
			"baseSymbol": "USDT",
			"status": "TRADING",
			"direction": "BUY",
			"price": 177.33,
			"triggerPrice": 0,
			"time": 1557221399781,
			"completedTime": null,
			"canceledTime": null,
			"marginTrade": 0,
			"orderResource": "ROBOT",
			"detail": [],
			"amountStr": null,
			"priceStr": null,
			"completed": false
		}],
		"totalElements": 21,
		"totalPages": 21,
		"last": false,
		"size": 1,
		"number": 0,
		"first": true,
		"sort": [{
			"direction": "DESC",
			"property": "time",
			"ignoreCase": false,
			"nullHandling": "NATIVE",
			"ascending": false,
			"descending": true
		}],
		"numberOfElements": 1
	},
	"code": 0,
	"message": null,
	"total": null
}
```







## 取消订单
#### 限速规则：/
#### HTTP请求

``` vbscript
GET /user/query/cancel_order
```

#### 参数
memberId		用户ID
orderId		订单号

#### 响应示例

``` json
{
	"data": null,
	"code": 0,
	"message": "执行成功",
	"total": null
}
```






## 查询用户历史委托
#### 限速规则：/
#### HTTP请求

``` vbscript
GET /user/history
```

#### 参数
memberId		账户ID  
direction			订单方向，BUY买，SELL卖  
symbol			交易对 BTC/USDT
startTime		时间戳long  
endTime			时间戳long  
type				订单类型，MARKET_PRICE市价，LIMIT_PRICE限价  
pageNum			页编号
pageSize			每页大小

#### 响应示例

``` json
{
	"data": {
		"content": [{
			"orderId": "E155722139978120",
			"memberId": 9,
			"type": "LIMIT_PRICE",
			"amount": 0.51,
			"symbol": "ETH/USDT",
			"tradedAmount": 0,
			"turnover": 0,
			"coinSymbol": "ETH",
			"baseSymbol": "USDT",
			"status": "TRADING",
			"direction": "BUY",
			"price": 177.33,
			"triggerPrice": 0,
			"time": 1557221399781,
			"completedTime": null,
			"canceledTime": null,
			"marginTrade": 0,
			"orderResource": "ROBOT",
			"detail": [],
			"amountStr": null,
			"priceStr": null,
			"completed": false
		}],
		"totalElements": 21,
		"totalPages": 21,
		"last": false,
		"size": 1,
		"number": 0,
		"first": true,
		"sort": [{
			"direction": "DESC",
			"property": "time",
			"ignoreCase": false,
			"nullHandling": "NATIVE",
			"ascending": false,
			"descending": true
		}],
		"numberOfElements": 1
	},
	"code": 0,
	"message": null,
	"total": null
}
```