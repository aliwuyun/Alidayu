# 文本转语音通知


## 1. 官方文档

http://open.taobao.com/docs/api.htm?apiId=25444

## 2. 参数、方法

|官方参数|对应方法|类型|是否必须|默认值|说明|
|----|----|----|----|----|----|
|`called_num`|`setCalledNum($value)`|string|**必须**| |设置被叫号码|
|`tts_param`|`setTtsParam($value)`|array&#124;string|可选| |设置内容模板参数|
|`called_show_num`|`setCalledShowNum($value)`|string|**必须**| |设置被叫号显|
|`tts_code`|`setTtsCode($value)`|string|**必须**| |设置TTS模板ID|
|`extend`|`setExtend($value)`|string|可选| |设置公共回传参数|

## 3. 使用

```php
<?php
use Aliwuyun\Alidayu\AlibabaAliqinFcTtsNumSinglecall;
use Alidayu;

class TestController extends Controller
{
    public function send()
    {
        $message = (new AlibabaAliqinFcTtsNumSinglecall())
            ->setCalledNum('13312311231')
            ->setTtsParam([
                    'username' => 'admin',
                    'time'     => date('Y-m-d'),
                    'client'   => '阿里大于'
                ])
            ->setCalledShowNum('123456789')
            ->setTtsCode('TTS_123456789');

        return Alidayu::send($message);
    }
}
```
