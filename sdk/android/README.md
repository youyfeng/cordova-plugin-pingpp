Pingpp Android SDK
============

## 简介
lib 目录包含三个 Library Project：`pingpp`、`pingpp_one` 和 `bdwallet_pay_sdk`。  
可以直接将三个 Library Project 作为依赖库，导入到你的项目。支持 Android Studio（建议）和 Eclipse。  
example 文件夹里面是一个简单的接入示例，该示例仅供参考。想使用该示例，请直接将本仓库导入。  
docs 目录里面是 Android SDK 的接入指南。

## 版本要求
Android SDK 要求 Android 2.3 及以上版本  
请使用 Java 7 或以上版本

## 接入方法
关于如何使用 SDK 请参考 docs 目录下面的接入文档或者参考提供的 example 工程。

## 注意事项
* Pingpp Android SDK 可能会与友盟、百度地图等其他第三方 jar 包冲突，当同时使用这些 jar 包的时候用户需要根据情况判断保留哪一方的 jar 包。
* 新版建议使用 Android Studio
* 请勿直接使用客户端支付结果作为最终判定订单状态的依据，由于 Ping++ 没有参与你的客户端和第三方渠道的交互，无法保证客户端支付结果的安全性，建议订单状态的更新对比客户端的渠道同步回调信息和服务端的 Ping++ Webhooks 通知来确定是否修改。