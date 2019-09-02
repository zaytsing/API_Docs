# 币赢钱包API文档

目前开放了支付模块的api，需要商户与我们联系开户，我们将提供key与secret，商户请求接口需用key与secret做签名认证


# 币支付接口说明

* 接口请求的基础url为 https://yysyservice.com:20002
* 签名说明：这里的签名采用sha256对请求接口的url与参数带上key与时间戳(毫秒级-长度是13位的)进行加密得到密文，然后在请求中将密文赋给sign参数加进请求头里。
例如：get请求 https://yysyservice:20002/api/Pay   参数有symbol、openid、remark，则需要对 http://yysyservice:20002/api/Pay?accessKey=****&openid=1001&remark=111&symbol=usdt&timestamp=1567412503000 进行sha256加密（注意参数的排序是按照键进行升序排序的）然后在请求头里带上sign参数，值就是得到的密文
* 只要请求正常，接口统一返回200状态码，返回的Json格式为
{
  "success": true,
  "data": "string"
}

### 接口列表
请求方法|类型|描述
----------------------|---------------------|-----------------------------|
[/api/Pay](#Pay)	|Get|请求收币地址
[/api/Pay/getbalance](#getbalance)	|Get|请求未确认余额
[/api/Pay/getOrderHistory](#getOrderHistory)	|Get|请求用户收币历史记录
[/api/ticker](#ticker)	|Get|获取服务器上当前币种的人民币价格
[/api/time](#time)	|Get|获取服务器当前时间
[商户回调](#callback)	|Get|商户回调

<span id="Pay">

#### /api/Pay 请求收币地址
请求参数:

参数名称|是否必须|类型|描述|默认值|取值范围
----------------------|---------------------|-----------------------------|----------------------|---------------------|-----------------------------|
symbol	|true|string|币种，如btc|btc|btc、usdt
openid	|true|string|商户系统中用户的id||
remark	|false|string|预留字段，商户的自定义参数，将在回调中返回该数据||
accessKey	|true|string|商户向支付系统申请的key||
timestamp	|true|long|0时区的毫秒级时间戳||
sign	|true|string|签名，用申请的secret对请求的url（包括请求头参数）进行HMACSHA256加密，形成sign参数||

</span>

<span id="getbalance">

#### /api/Pay/getbalance 请求未确认余额


</span>

<span id="getOrderHistory">

#### /api/Pay/getbalance 请求用户收币历史记录


</span>

<span id="ticker">

#### /api/Pay/getbalance 获取服务器上当前币种的人民币价格


</span>

<span id="time">

#### /api/Pay/getbalance 获取服务器当前时间


</span>

<span id="callback">

### 商户回调说明


</span>

# 各语言示例

## PHP<br>
 >  [介绍](https://github.com/coinWinApi/Api-PHP)<br>
 >  [示例](https://github.com/coinWinApi/Api-PHP-Demo)<br>

