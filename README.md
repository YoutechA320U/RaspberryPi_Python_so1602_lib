# RaspberryPi_Python_so1602_library
RaspberryPi Python OLED so1602用ライブラリ
## 概要
このライブラリは、RaspberryPiで[有機ELキャラクタディスプレイモジュール16x2行](http://akizukidenshi.com/catalog/g/gP-08277/)を扱いやすくするためのライブラリです。直接日本語(カタカナ)や一部特殊文字が使えます


## 必要なライブラリ
    smbus

### 使用例
    import so1602
    so1602.setaddr(0x3c)
    so1602.command(0x01)
    so1602.command(0x80)
    so1602.write("SO1602ナンダヨ!")
    so1602.command(0xa0)
    so1602.write("ΩΩΩ<ナ、ナンダッテー!?")


![SS](https://github.com/YoutechA320U/RaspberryPi_Python_so1602_library/blob/master/example.JPG "example")


## 備考
エクスクルーシブメッセージのテストはポケットミクで行っています。あまりにも長いメッセージだと読み取りに失敗するかもしれません。

MIDI端子の名前にちなんで`UART_MIDI_IN`、`UART_MIDI_OUT`という仮想MIDIポート名ですが、Linux内部的には`UART_MIDI_IN`は仮想出力、`UART_MIDI_OUT`は仮想入力ポートです。

一度に大量のMIDIメッセージを受信すると処理落ちする事があります。また -d オプションを付けて実行すると入出力をコンソールに表示するので処理が重くなります。

### 参考コード・資料
 * <http://www.samplerbox.org/article/midiinwithrpi>  
 * <https://docs.python.org/ja/2.7/library/functions.html>
 * <https://qiita.com/unchainendo/items/1ea305d87c797ba02450>  
 * <https://github.com/SpotlightKid/python-rtmidi>  

## 履歴
    [2018/08/16] - 初回リリース
    [2018/08/18] - 余計なループ・変数を省いて高速化
    [2018/08/31] – 2018/09/01に取り下げました
    [2018/10/08] – 出力に対応
