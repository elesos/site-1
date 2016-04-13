title: 用户
---

本 SDK 中上传素材通过 `Overtrue\Wechat\User`、`Overtrue\Wechat\Group` 提供用户与用户组管理服务。

### 获取实例

```php
<?php

use Overtrue\Wechat\User;

$appId  = 'wx3cf0f39249eb0e60';
$secret = 'f1c242f4f28f735d4687abb469072a29';

$userService = new User($appId, $secret);
```

## API

+ `$userService->get($openId);` 获取用户信息
+ `$userService->lists($nextOpenId = null);` 获取用户列表, `$nextOpenId` 可选
+ `$userService->remark($openId, $remark);` 修改用户备注, 返回boolean
+ `$userService->group($openId);` 获取用户所属用户组ID

example:

```php
$user = $userService->get($openId);

echo $user->nickname;
```

## 用户组

```php
<?php

use Overtrue\Wechat\Group;

$appId  = 'wx3cf0f39249eb0e60';
$secret = 'f1c242f4f28f735d4687abb469072a29';

$group = new Group($appId, $secret);
```

+ `$group->lists();` 获取所有分组
+ `$group->create($name);` 创建分组
+ `$group->update($groupId, $name);` 修改分组信息
+ `$group->delete($groupId);` 删除分组
+ `$group->moveUser($openId, $groupId);` 移动单个用户到指定分组
+ `$group->moveUsers(array $openIds, $groupId);` 批量移动用户到指定分组

关于用户与用户组管理请参考微信官方文档：http://mp.weixin.qq.com/wiki/ `用户管理` 章节。