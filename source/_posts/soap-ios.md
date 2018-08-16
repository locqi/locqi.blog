---
title: 快速使用 SOAP-IOS 请求 国内手机号码归属地查询WEB服务
date: 2018-08-15 08:56:11
tags: 敲敲码
comments: true
categories: 敲敲码
---

## 前言

Web Service技术， 能使得运行在不同机器上的不同应用无须借助附加的、专门的第三方软件或硬件， 就可相互交换数据或集成。依据Web Service规范实施的应用之间， 无论它们所使用的语言、 平台或内部协议是什么， 都可以相互交换数据。Web Service是自描述、 自包含的可用网络模块， 可以执行具体的业务功能。Web Service也很容易部署， 因为它们基于一些常规的产业标准以及已有的一些技术，诸如标准通用标记语言下的子集XML、HTTP。Web Service减少了应用接口的花费。Web Service为整个企业甚至多个组织之间的业务流程的集成提供了一个通用机制。

简单来说 Web Service 请求就是往服务器POST XML数据，然后服务器响应得到的也是XML数据；

好了，概念性的东西就说到这里（需要了解更多详细内容，请自行问度娘）。

>下面进入正题：

接下来就来说说如何使用iOS NSMutableURLRequest 接口进行webservice 请求示例；

 测试使用的接口 http://ws.webxml.com.cn/WebServices/MobileCodeWS.asmx

 根据接口描述使用了两种版本的soap请求：soap1.1,soap1.2 两种区别在于 soap请求体xml的格式上；

## 环境部署

需要下载以下内容：

[SOAP-IOS](https://github.com/xujialiang/SOAP-IOS)

### IOS SOAP的使用方法:

#### 1.引用KissXML（具体如何在项目中添加KissXML，这里就不写了）。

#### 2.将服务的WebService的wsdl文件添加到项目中

在火狐或者谷歌浏览器```（Safari浏览器保存不了xml格式）```上打开 [此链接](http://ws.webxml.com.cn/WebServices/MobileCodeWS.asmx?wsdl) 另存页面为MobileCodeWebService.xml。将此文件添加到项目中，后缀名必须为xml。

#### 3.获取soap信封

``` bash
SoapUtility *soaputility = [[SoapUtility alloc] initFromFile:@"MobileCodeWebService"];这里的MobileCodeWebService是步骤2中添加的wsdl文件。不包含扩展名。
NSString *SoapXML = [soaputility BuildSoapwithMethodName:@"getMobileCodeInfo" withParas:@{@"mobileCode": @"18712345678"}];
``` 

#### 4.获取soapAction

``` bash
NSString *soapAction = [soaputility GetSoapActionByMethodName:method SoapType:SOAP];
``` 

#### 5.得到了soap信封和SoapAction，就可以用使用http post 来提交了。

``` bash
SoapService *soaprequest = [[SoapService alloc] init];
soaprequest.PostUrl = @"http://ws.webxml.com.cn/WebServices/MobileCodeWS.asmx";
soaprequest.SoapAction = [soaputility GetSoapActionByMethodName:methodName SoapType:SOAP];
``` 

>至此基础环境搭建完毕!!!

### 接下来运行项目，看结果!
![](https://i.imgur.com/QpmODSk.png)

>PS（附言）：请求方式有两种，实际应用时依情况而定。

同步方式

``` bash
ResponseData *result= [soaprequest PostSync:postData];
``` 

异步方式

``` bash
[soaprequest PostAsync:postData Success:^(NSString *response) {
        [self.result setText:response];        
    } falure:^(NSError *response) {    
        [self.result setText:response.description];        
    }];
``` 



