# SONY_IXS-6000_Configuration
SONY IXS-6600 IXS-6700の構成用メモ  
ixs-6000.rlg: RLoginのTelnet設定ファイル  
## Telnet接続
host: 192.168.0.135(default IP address for ethernet port A)  
port: 1001  
Fキー割り当てコード  
F1:  `ESC [ 17̃ ` (`1B, 5B, 31, 37, 7E`)  
F2:  `ESC [ 18 ` (`1B, 5B, 31, 38, 7E`)  
F3:  `ESC [ 19 ` (`1B, 5B, 31, 39, 7E`)  
F4:  `ESC [ 20 ` (`1B, 5B, 31, 30, 7E`)  
F5:  `ESC [ 21 ` (`1B, 5B, 31, 31, 7E`)  
## 設定初期化方法
`R : CALL SECONDARY STATION`でステーションID 1を呼び出し  
入れたら`K: RESET TO DEFAULT TABLE`を実行  
## SBusコンパネ設定方法
`Z: SET UNIT DETECTABLE`で各アドレス上でEnterキーを押して状態を?に全部変更  
一度抜けて再び入り、?が機種IDになっているところが認識しているコンパネのアドレス。  
必要に応じて`F: SET ACTIVE UNIT NUMBER`で繋がっているコンパネのアドレスを有効にする。  
`N: SET DESCRIPTION NAME GROUP`でShift+Sを押して、コンパネのアドレスを入力してEnter  
`R : CALL SECONDARY STATION`でコンパネのIDを入力して呼び出し  
`O: SET AVAILABLE SOURCE/DESTINATION`で各DST名が表示されるのを確認。されていなければEnterキーを押していくとデフォルト値に変更される  
`N: SET PANEL TABLE`でDSTに割り当てるボタン、SRCに割り当てるボタンを設定する  
DSTでは、カーソルキーでボタンを選んでEnter→`11`→Enter で1(Output)1chになる  
SRCでは同様にEnter→`01`→Enterで0(Input)1chに設定される  
DSTで0(INPUT)、SRCで1(OUTPUT)を選択するとエラーになる
