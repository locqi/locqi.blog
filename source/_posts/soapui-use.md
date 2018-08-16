---
title: soapUI的安装和使用（基于请求国内手机号码归属地查询WEB服务）
date: 2018/8/16 9:26:16
tags: 敲敲码
comments: true
categories: 敲敲码
---

## 前言

soapUI是一款用来模拟webService客户端的软件，使用soapUI可以更方便的解析webService服务对外公布的类和方法。使用soapUI还可以进行压力测试等。接下来小编介绍下soapUI的基本使用方法，方便网友们及时上手。

>下面进入正题：

### 下载安装soapUI软件

在浏览器url中输入[soapUI官网地址](https://www.soapui.org/)或通过搜索引擎搜索到soapUI的官方网站，点击进入首页，在首页有下载字样，点击下载就可以了，安装的过程和普通的软件类似，这里不再赘述。
![](https://i.imgur.com/VIOoWEH.png)

### 使用soapUI

#### 1.打开soapUI，新建一个soap工程```(点击File，在弹出框中，点击New SOAP Project)```，如下图
![](https://i.imgur.com/FaomVR1.png)

国内手机号码归属地查询WEB服务接口：http://ws.webxml.com.cn/WebServices/MobileCodeWS.asmx?wsdl

#### 2.将webService服务端的地址输入到如下位置，点OK。``【注意：输入的地址后面要加?wsdl】``
![](https://i.imgur.com/jTMpwzc.png)


#### 3.然后就可以得到如下wsdl中所有的接口。
![](https://i.imgur.com/y1RiSaX.png)

#### 4.双击Request1，打开报文，即可对该接口进行接口测试。如下，输入mobileCode``(将？问号替换为实际的参数值)``，点击左上角的三角形发送图标，就可以模拟客户端向服务器发送请求数据了。
![](https://i.imgur.com/D6AzOn4.png)

#### 5.编辑项目。在创建的项目上点击右键，可以对项目名称进行修改、删除、重新加载文件等。
![](https://i.imgur.com/aW4WmIW.png)

>PS（附言）：最后附上网上常用免费的webService

天气预报Web服务，数据来源于中国气象局 公用事业 
http://www.webxml.com.cn/WebServices/WeatherWebService.asmx

中国股票行情分时走势预览缩略图 
http://www.webxml.com.cn/webservices/ChinaStockSmallImageWS.asmx

中国股票行情数据 WEB 服务（支持深圳和上海股市的基金、债券和股票） 
http://www.webxml.com.cn/WebServices/ChinaStockWebService.asmx

国内飞机航班时刻表 WEB 服务 公用事业 
http://www.webxml.com.cn/webservices/DomesticAirline.asmx

中国电视节目预告（电视节目表） WEB 服务 公用事业 
http://www.webxml.com.cn/webservices/ChinaTVprogramWebService.asmx

火车时刻表 （第六次提速最新列车时刻表） 公用事业 
http://www.webxml.com.cn/WebServices/TrainTimeWebService.asmx

中文 <-> 英文双向翻译 WEB 服务 获得标准数据 
http://www.webxml.com.cn/WebServices/TranslatorWebService.asmx

验证码图片 WEB 服务 支持中文、字母、数字 图像和多媒体 
http://www.webxml.com.cn/WebServices/ValidateCodeWebService.asmx

中国邮政编码 <-> 地址信息双向查询/搜索 WEB 服务 获得标准数据 
http://www.webxml.com.cn/WebServices/ChinaZipSearchWebService.asmx

IP地址来源搜索 WEB 服务（是目前最完整的IP地址数据） 获得标准数据 
http://www.webxml.com.cn/WebServices/IpAddressSearchWebService.asmx

国内手机号码归属地查询

http://webservice.webxml.com.cn/WebServices/MobileCodeWS.asmx

外汇-人民币即时报价

http://webservice.webxml.com.cn/WebServices/ForexRmbRateWebService.asmx

腾讯QQ在线状态 WEB 服务

http://webservice.webxml.com.cn/webservices/qqOnlineWebService.asmx

中文简体字<->繁体字转换 WEB 服务 
http://webservice.webxml.com.cn/WebServices/TraditionalSimplifiedWebService.asmx

IP地址搜索 WEB 服务包含中国和国外已知的IP地址数据，是目前最完整的IP地址数据，记录数量现已超过37万条并还在不断更新和增加中 
http://webservice.webxml.com.cn/WebServices/IpAddressSearchWebService.asmx





