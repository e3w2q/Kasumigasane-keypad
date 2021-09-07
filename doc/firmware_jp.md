# 霞襲 ファームウェアの書き込み

ここでは、ファームウェアを書き込む2種類の方法を記載します。

前者の[Pro Micro Web UpdaterとRemapを使う場合](#pro-micro-web-updaterとremapを使う場合)が手軽でおすすめです。

より詳しく設定したい場合は、後者の[QMK Firmwareのコマンドを使う場合](#qmk-firmwareのコマンドを使う場合)を参照してください。

<!-- TOC -->

- [霞襲 ファームウェアの書き込み](#霞襲-ファームウェアの書き込み)
    - [Pro Micro Web UpdaterとRemapを使う場合](#pro-micro-web-updaterとremapを使う場合)
        - [ファームウェアのダウンロード](#ファームウェアのダウンロード)
        - [Pro Micro Web Updaterを使ったファームウェアの書き込み](#pro-micro-web-updaterを使ったファームウェアの書き込み)
        - [Remapでのキー書き換え](#remapでのキー書き換え)
    - [QMK Firmwareのコマンドを使う場合](#qmk-firmwareのコマンドを使う場合)

<!-- /TOC -->

## Pro Micro Web UpdaterとRemapを使う場合

### ファームウェアのダウンロード

以下のzipファイルをダウンロードして保存してください。

- https://github.com/e3w2q/Kasumigasane-keypad/blob/main/firmware/e3w2q_kasumigasane_via.zip?raw=true

zipファイルの中のhexファイルを取り出してください。

### Pro Micro Web Updaterを使ったファームウェアの書き込み

- [Pro Micro Web Updater](https://sekigon-gonnoc.github.io/promicro-web-updater/index.html)

霞襲をPCに接続した状態で、Pro Micro Web Updaterにアクセスし、先ほど取り出したhexファイルを選択し、「flash」をクリックします。

シリアルポートへの接続要求の画面が出ます。

霞襲の裏面中央のRESETと書かれたところの左右の穴をピンセットやクリップなどで短絡させ、出てきたUSBシリアルデバイスを選択して「接続」をクリックします。

するとファームウェアが書き込まれます。

### Remapでのキー書き換え

- [Remap](https://remap-keys.app/)

霞襲をPCに接続した状態で、RemapのWebサイトにアクセスし、「START REMAP FOR YOUR KEYBOARD」をクリックします。

「+KEYBOARD」をクリックします。

HIDデバイスへの接続要求の画面が出ます。

「Kasumigasane」を選択して「接続」をクリックします。

キー割り当てを変更できる画面が表示されます。

キー割り当てを変更して右上の「flash」をクリックすると、変更されます。



## QMK Firmwareのコマンドを使う場合

以下のリンク先を参考にして、QMK Firmwareのビルド環境を用意します。

- Windows
  - [QMKビルド環境の構築(Windows Msys2編)](https://gist.github.com/e3w2q/4bc86e531d1c893d3d13af3e9895a94a)
- macOS
  - [セットアップ - QMK Firmware](https://docs.qmk.fm/#/ja/newbs_getting_started?id=macos)
- Linux
  - [セットアップ - QMK Firmware](https://docs.qmk.fm/#/ja/newbs_getting_started?id=linux)

構築中、

```
qmk setup
```

と入力する代わりに

```
qmk setup e3w2q/qmk_firmware --branch e3w2q
```

と入力してください。

または、`qmk setup`した後に、`C:\Users\USER_NAME\qmk_firmware\keyboards`配下に[https://github.com/e3w2q/qmk_firmware/tree/e3w2q/keyboards/e3w2q](https://github.com/e3w2q/qmk_firmware/tree/e3w2q/keyboards/e3w2q)以下をコピーしてもよいです。

用意されたキーマップを書き込むには以下を実行します。

```
qmk flash -kb e3w2q/kasumigasane -km default
```

`Detecting USB port, reset your controller now...`と表示されたら裏面中央のRESETと書かれたところの左右の穴をピンセットやクリップなどで短絡させると書き込みが始まります。

[QMK Configuratorのテストモード](https://config.qmk.fm/#/test)でキー入力が行えるかテストしてください。

