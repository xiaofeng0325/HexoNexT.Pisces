---
title: android get请求和post请求区别
tags:
  - Android
  - Android Tips
categories:
  - Android
  - Android Tips
abbrlink: cec09649
date: 2018-08-06 14:44:42
---

#### Get请求与Post请求的区别

##### Get是向服务器发索取数据的一种请求
- Get是获取信息，而不是修改信息，类似数据库查询功能一样，数据不会被修改
- Get请求的参数会跟在url后进行传递，请求的数据会附在URL之后，以?分割URL和传输数据，参数之间以&相连,％XX中的XX为该符号以16进制表示的ASCII，如果数据是英文字母/数字，原样发送，如果是空格，转换为+，如果是中文/其他字符，则直接把字符串用BASE64加密。
- Get传输的数据有大小限制，因为GET是通过URL提交数据，那么GET可提交的数据量就跟URL的长度有直接关系了，不同的浏览器对URL的长度的限制是不同的。
- GET请求的数据会被浏览器缓存起来，用户名和密码将明文出现在URL上，其他人可以查到历史浏览记录，数据不太安全。在服务器端，用Request.QueryString来获取Get方式提交来的数据

##### Post是向服务器提交数据的一种请求
- Post请求则作为http消息的实际内容发送给web服务器，数据放置在HTML Header内提交，Post没有限制提交的数据。Post比Get安全，当数据是中文或者不敏感的数据，则用get，因为使用get，参数会显示在地址，对于敏感数据和不是中文字符的数据，则用post
- POST表示可能修改变服务器上的资源的请求，在服务器端，用Post方式提交的数据只能用Request.Form来获取

<!--more-->