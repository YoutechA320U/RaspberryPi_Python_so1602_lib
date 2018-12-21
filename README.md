# RaspberryPi_Python_so1602_library
RaspberryPi Python OLED so1602用ライブラリ
## 概要
このライブラリは、RaspberryPiで[有機ELキャラクタディスプレイモジュール16x2行](http://akizukidenshi.com/catalog/g/gP-08277/)を扱いやすくするためのライブラリです。直接日本語(カタカナ)や一部特殊文字が使えます。


## 必要なライブラリ
    smbus
## コマンド一覧
    so1602.setaddr(　SlaveAddress　)

モジュールのスレーブアドレスを設定します。最初に必ず使ってください。

    so1602.command( Command )

各種コマンドを実行します。実行できるコマンドは[データシート](http://akizukidenshi.com/download/ds/sunlike/SO1602AWYB-UC-WB-U.pdf)を参照してください。

    so1602.write( "character" )
    so1602.write( 'character' )

ディスプレイに文字列を表示します。文字列は必ずクォーテーションマークかアポストロフィーで囲んでください。表示できる文字は[so1602.py](https://github.com/YoutechA320U/RaspberryPi_Python_so1602_library/blob/master/so1602.py)を参照してください。

## 使用例
    import so1602 #モジュールをインポート
    so1602.setaddr(0x3c) #スレーブアドレスを0x3Cに設定
    so1602.command(0x0c) #so1602をオン
    so1602.command(0x01) #so1602のリセットコマンド
    so1602.command(0x80) #カーソルを1行目の先頭に
    so1602.write("SO1602ナンダヨ!")
    so1602.command(0xa0) #カーソルを2行目の先頭に
    so1602.write('ΩΩΩ<ナ、ナンダッテー!?')


![SS](https://github.com/YoutechA320U/RaspberryPi_Python_so1602_library/blob/master/example.JPG "example")

### 参考コード・資料
 * <http://akizukidenshi.com/download/ds/sunlike/SO1602AWYB-UC-WB-U.pdf>  
 * <http://www.newhavendisplay.com/app_notes/US2066.pdf>  

## 履歴
    [2018/12/21] - 初回リリース
