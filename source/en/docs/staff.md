title: 客服
---

微信的客服才能发送消息或者群发消息，而且还有时效限制，真恶心的说。。。

本 SDK 由 `Overtrue\Wechat\Staff` 提供客服相关服务。



### 获取实例

```php
<?php

use Overtrue\Wechat\Staff;

$appId  = 'wx3cf0f39249eb0e60';
$secret = 'f1c242f4f28f735d4687abb469072a29';

$userService = new Staff($appId, $secret);
```

### API

+ `$staff->lists();` 获取所有客服账号列表
+ `$staff->onlines();` 获取所有在线的客服账号列表
+ `$staff->create($email, $nickname, $password);` 添加客服帐号
+ `$staff->update($email, $nickname, $password);` 修改客服帐号
+ `$staff->delete($email, $nickname, $password);` 删除客服帐号
+ `$staff->avatar($email, $avatarPath);` 设置客服帐号的头像
+ `$staff->send($message)->to($openId);` 主动发送消息给用户
+ `$staff->send($message)->by('account@test')->to($openId);` 指定客服发送消息

关于更多客服接口信息请参考微信官方文档：http://mp.weixin.qq.com/wiki/9/6fff6f191ef92c126b043ada035cc935.html
