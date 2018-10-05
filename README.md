# rongqiangqin_baiduspeech
百度语音合成sdk(php)-基于官方sdk

#使用方法
~~~
  use rongqiangqin\baiduspeech\AipSpeech;
  
  $APP_ID = 'your-id';
  $API_KEY = 'your-key';
  $SECRET_KEY = 'your-key';

  $client = new AipSpeech($APP_ID, $API_KEY, $SECRET_KEY);

  $text="你好,百度";

  $result = $client->synthesis($text, 'zh', 1, array(
      'vol' => 5,//音量，取值0-15，默认为5中音量
      'per' => 1,//发音人选择, 0为普通女声，1为普通男生，3为情感合成-度逍遥，4为情感合成-度丫丫，默认为普通女声
      'spd' => 7,//语速，取值0-15，默认为5中语速
  ));

  // 识别正确返回语音二进制 错误则返回json 参照下面错误码
  if(!is_array($result)){
      file_put_contents('audio.mp3', $result);
  }
~~~  
  
