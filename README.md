# think-wxminilogin
����ThinkPHP5.0��΢��С����composer��

�Ż��������Ŀ��С����Ľ���
https://github.com/wulongtao/think-wxminihelper


1.��config.php�����ļ��м�����������

```
// wx����
'wx'  => [
    'url' => 'https://api.weixin.qq.com/sns/jscode2session',
    'appid' => 'wxde3ea15f3a18f7f6',
    'secret' => '53b1a4e12b88d78f3bcc2786fb72adcf',
    'grant_type' => 'authorization_code'
]
```

2.ʹ��```checkLogin```������֤

```
$code = input("code", '', 'htmlspecialchars_decode');
$rawData = input("rawData", '', 'htmlspecialchars_decode');
$signature = input("signature", '', 'htmlspecialchars_decode');
$encryptedData = input("encryptedData", '', 'htmlspecialchars_decode');
$iv = input("iv", '', 'htmlspecialchars_decode');

$wxHelper = new WXLoginHelper();
$data = $wxHelper->checkLogin($code, $rawData, $signature, $encryptedData, $iv);
```