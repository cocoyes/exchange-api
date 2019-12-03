# 交易所接口简介
______
## API 简介

欢迎使用 API接口！ 你可以使用此 API 获得市场行情数据，进行交易，并且管理你的账户。

此文档为用户提供了一整套简单而又强大的开发工具，旨在帮助用户快速、高效地将交易功能整合到自己的应用当中。 接口是提供服务的基础，API公共和私有两类。开发者在网站创建账号后，可以创建调用API所需要的apiKey和秘钥。 账户和交易API需要通过apiKey和秘钥进行签名，提供下单、撤单，查询订单和帐户信息等功能。行情API提供市场的行情数据，所有行情接口都是公开的。 如果api返回值里出现文档上没有的字段，则意味着这些字段即将被弃用，请使用文档上的字段。

## 签名方式说明
签名算法：HmacSHA256
签名组成信息包括“前置部分”、“隐私部分”、“参数部分”。

### 前置部分
前置部分为接口基本信息，顺序为：method+host+接口路径
例如：

``` lsl
POST
192.168.1.1
/open-api/user/add_order
```
注意：需要用换行符连接这三个参数，第三行末尾需要换行。

### 隐私部分
隐私部分由加密key、加密方式、版本、时间戳组成。
分别为：accessKeyId、signatureMethod、signatureVersion、timestamp的键值拼接。
例如：

``` lsl
accessKeyId=68c108f2-45c3-4aaf-a378-bc513439ae28&signatureMethod=HmacSHA256&signatureVersion=2&timestamp=0002-09-24T22%3A55%3A22
```
注意：accessKeyId需要申请，时间戳格式为uuuu-MM-dd'T'HH:mm:ss，键值间通过&符连接。

### 参数部分
参数部分即请求该接口的必要参数的键值组成，键值间通过&符连接，按照key的升序排列。
例如：

``` dts
amount=1&direction=SELL&memberId=12&price=9000&symbol=BTC/USDT&type=LIMIT_PRICE
```
注意：最终参与签名的字符串，“隐私部分”与“参数部分”需要通过&符连接。