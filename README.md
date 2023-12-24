# GroveUART

<img src="https://github.com/akita11/GroveUART/blob/main/GroveUART.jpg" width="320px">

GroveケーブルのUART信号を、FTDI-Basic等のUSBシリアル変換器の標準的な6ピンコネクタに接続します。両者の送信(TX)と受信(RX)の接続を切り替えらるので、ストレート結線・リバース結線の両者の使い方ができます。またソルダージャンパをショートすることでFTDI-Basic側の電源をGroveコネクタ側に供給することができます。


## 使い方

M5Stack等からのUART信号の出ているGroveケーブルをGroveコネクタ側に接続し、6ピンコネクタ側には[FTDI-Basic等のUSB-シリアル変換器](https://www.switch-science.com/products/2782)を接続します。Groveケーブル側のUART信号にあわせて、以下のように2箇所のショートピンを設定します。

また裏面のJP1をハンダでショートすることで、FTDI-Basicからの電源をGroveコネクタ側に供給することができます。

### Grove側がUART親機側(M5Stack等)の場合

<img src="https://github.com/akita11/GroveUART/blob/main/GroveUART1.jpg" width="320px">

このようにR-R側、T-T側にショートピンを接続します。これにより、以下のように接続されます。

- Groveの1番ピン（端）: FTDI-BasicのTXD(TXo)側
- Groveの2番ピン（その横）: FTDI-basicのRXD(RXi)側

※Groveの1番／2番ピンは、M5StackのPortCのGPIO16(RXD2)/17(TXD2)(Basicの場合)や、GPIO13(RXD2)/14(TXD2)(Core2)です。


### Grove側がUART子機側(Groveセンサ等等)の場合

<img src="https://github.com/akita11/GroveUART/blob/main/GroveUART2.jpg" width="320px">

このようにR-T側、R-T側にショートピンを接続します。これにより、以下のように接続されます。

- Groveの1番ピン（端）: FTDI-basicのRXD(RXi)側
- Groveの2番ピン（その横）: FTDI-BasicのTXD(TXo)側

※例えばM5Stack UnitV2では、Groveの1番ピンは"Rx”と表記されていますが、これは「接続先（M5StackBasic等)がRx」という意味ですので、UnitV2にとっては出力(TX)です。


## Author

Junichi Akita (akita@ifdl.jp, @akita11)
