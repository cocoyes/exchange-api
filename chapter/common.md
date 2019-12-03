# 公开接口
---
公开接口不需要签，直接调用即可。

## 同步服务器时间
查询服务器当前时间戳，保持时间基本同步。
#### 限速规则：/
#### HTTP请求

``` vbscript
GET /open/synTime
```
#### 响应示例

``` json
{
    "data": 1569341402664,
    "code": 0,
    "message": "success",
    "total": null
}
```





## 获取支持的交易对
获取交易所当前支持的交易对。
#### 限速规则：/
#### HTTP请求

``` vbscript
GET /open/symbol_thumb
```
#### 响应示例

``` json
{
	"data": [{
		"symbol": "ETH/USDT",
		"open": 0,
		"high": 0,
		"low": 0,
		"close": 198.0908,
		"chg": 0,
		"change": 0,
		"volume": 401.2624,
		"turnover": 80689.6935,
		"lastDayClose": 198.0908,
		"usdRate": 198.0908,
		"baseUsdRate": 1,
		"closeStr": "198.0908",
		"trend": [201.0936, 198.0908],
		"proportion": 3
	}, {
		"symbol": "KTCH/USDT",
		"open": 1.8879,
		"high": 1.8988,
		"low": 1.8879,
		"close": 1.8899,
		"chg": 0.0011,
		"change": 0.002,
		"volume": 28417.9903,
		"turnover": 53975.80362441,
		"lastDayClose": 1.8879,
		"usdRate": 1.8899,
		"baseUsdRate": 1,
		"closeStr": "1.8899",
		"trend": [1.8919, 1.8907, 1.8919, 1.8897, 1.8899, 1.8909, 1.8958, 1.894, 1.8897, 1.894, 1.8879, 1.8889, 1.8909, 1.8929, 1.8899, 1.8919, 1.8929, 1.8938, 1.8988, 1.8909, 1.8907, 1.8978, 1.8927, 1.8899],
		"proportion": 3
	}],
	"code": 0,
	"message": "SUCCESS",
	"total": null
}
```






## 获取历史K线图
获取指定交易对的历史K线图。
#### 限速规则：/
#### HTTP请求

``` tcl
GET /open/history/kline
```
#### 参数
symbol		交易对，例如 BTC/USDT  
period		时间柱，例如 1min  
size		页数，例如10  
#### 响应示例

``` json
{
	"data": [{
		"symbol": null,
		"openPrice": 198.0908,
		"highestPrice": 198.0908,
		"lowestPrice": 198.0908,
		"closePrice": 198.0908,
		"time": 1569342180000,
		"period": "1min",
		"count": 0,
		"volume": 0,
		"turnover": 0
	}],
	"code": 0,
	"message": "SUCCESS",
	"total": null
}
```





## 获取盘口信息
获取指定交易对当前的盘口信息。
#### 限速规则：/
#### HTTP请求

``` vbscript
GET /open/trade_plate
```
#### 参数
symbol		交易对，例如 BTC/USDT  
size		页数，例如10
#### 响应示例

``` json
{
	"data": {
		"ask": [{
			"price": 198.0908,
			"amount": 0.2887,
			"priceStr": "198.0908",
			"amountStr": "0.2887"
		}],
		"bid": [{
			"price": 198.09,
			"amount": 1.8452,
			"priceStr": "198.0900",
			"amountStr": "1.8452"
		}]
	},
	"code": 0,
	"message": "SUCCESS",
	"total": null
}
```




## 获取历史成交信息
获取指定交易对历史成绩信息
#### 限速规则：/
#### HTTP请求

``` vbscript
GET /open/trade_history
```
#### 参数
symbol		交易对，例如 BTC/USDT  
size		页数，例如10
#### 响应示例

``` json
{
	"data": [{
		"symbol": "ETH/USDT",
		"price": 198.0908,
		"priceStr": "198.0908",
		"amount": 0.0113,
		"amountStr": "0.0113",
		"buyTurnover": 2.23842604,
		"sellTurnover": 2.23842604,
		"direction": "SELL",
		"buyOrderId": "E156717399263154",
		"sellOrderId": "E156930565562254",
		"time": 1569305655631
	}],
	"code": 0,
	"message": "SUCCESS",
	"total": null
}
```




