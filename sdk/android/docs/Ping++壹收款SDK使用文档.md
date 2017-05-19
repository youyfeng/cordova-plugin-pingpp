## Ping++ Android 壹收款 SDK 相关文档

__这里仅指出与标准 SDK 不同的地方__

### 项目配置
##### 权限声明
与标准 SDK 相同

##### 注册 activity
``` xml
<!-- 壹收款 -->
<activity
    android:name="com.pingplusplus.libone.PayActivity"
    android:configChanges="orientation|keyboardHidden|navigation|screenSize"
    android:theme="@android:style/Theme.Translucent"/>
<activity
    android:name="com.pingplusplus.libone.PaySuccessActivity"
    android:configChanges="orientation|keyboardHidden|navigation|screenSize"/>
```

### 设置支付渠道及参数
设置要使用的支付方式
``` java
PingppOne.enableChannels(new String[]{"wx", "alipay", "upacp"});
```

提交数据的格式，默认格式为json
``` java
// PingppOne.CONTENT_TYPE = "application/x-www-form-urlencoded"; // form 表单格式
PingppOne.CONTENT_TYPE = "application/json"; // JSON 格式
```

### 调用支付接口
``` java
PingppOne.showPaymentChannels(
            activity,  // 当前页面
            // 获取charge参数字符串
            //{"order_no":"123456789", "amount":10, "custom_params":{"extra1":"extra1"}}
            bill.toString(), 
            SERVER_CHARGE_URL, // 获取charge的URL
            new PaymentHandler() { // 结果回调接口
            /**
             * 返回支付结果
             * @param data
             */
            @Override
            public void handlePaymentResult(Intent data) {
                if (data != null) {
                    /**
                     * code：支付结果码  -2:服务端错误、 -1：失败、 0：取消、1：成功
                     * result：支付结果信息
                     */
                    int code = data.getExtras().getInt("code");
                    String result = data.getExtras().getString("result");
        
                }
            }
});
```

