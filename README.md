# think-wxminilogin
基于ThinkPHP5.0的微信小程序composer包

优化了这个项目的小程序改进：
https://github.com/wulongtao/think-wxminihelper


1.在config.php配置文件中加入必须的配置

```
// wx配置
'wx'  => [
    'url' => 'https://api.weixin.qq.com/sns/jscode2session',
    'appid' => 'wxde3ea15f3a18f7f6',
    'secret' => '53b1a4e12b88d78f3bcc2786fb72adcf',
    'grant_type' => 'authorization_code'
]
```

2.使用```checkLogin```进行验证

```
$code = input("code", '', 'htmlspecialchars_decode');
$rawData = input("rawData", '', 'htmlspecialchars_decode');
$signature = input("signature", '', 'htmlspecialchars_decode');
$encryptedData = input("encryptedData", '', 'htmlspecialchars_decode');
$iv = input("iv", '', 'htmlspecialchars_decode');

$wxHelper = new WXLoginHelper();
$data = $wxHelper->checkLogin($code, $rawData, $signature, $encryptedData, $iv);
```