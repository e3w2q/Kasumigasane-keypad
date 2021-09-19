# 霞襲 ファームウェアの書き込み

ここでは、ファームウェアを書き込む3種類の方法を記載します。

[Pro Micro Web UpdaterとRemapを使う場合](#pro-micro-web-updaterとremapを使う場合)が手軽でおすすめです。

より詳しく設定したい場合は、[QMK Firmwareのコマンドを使う場合](#qmk-firmwareのコマンドを使う場合)を参照してください。

<!-- TOC -->

- [霞襲 ファームウェアの書き込み](#霞襲-ファームウェアの書き込み)
    - [Pro Micro Web UpdaterとRemapを使う場合](#pro-micro-web-updaterとremapを使う場合)
        - [ファームウェアのダウンロード](#ファームウェアのダウンロード)
        - [Pro Micro Web Updaterを使ったファームウェアの書き込み](#pro-micro-web-updaterを使ったファームウェアの書き込み)
        - [Remapでのキー書き換え](#remapでのキー書き換え)
    - [QMK ToolboxとVIAを使う場合](#qmk-toolboxとviaを使う場合)
        - [ファームウェア・キーマップJSONのダウンロード](#ファームウェア・キーマップjsonのダウンロード)
        - [QMK Toolboxのインストール](#qmk-toolboxのインストール)
        - [QMK Toolboxを使ったファームウェアの書き込み](#qmk-toolboxを使ったファームウェアの書き込み)
        - [VIAのインストール](#viaのインストール)
        - [VIAでのキー書き換え](#viaでのキー書き換え)
    - [QMK Firmwareのコマンドを使う場合](#qmk-firmwareのコマンドを使う場合)

<!-- /TOC -->

## Pro Micro Web UpdaterとRemapを使う場合

### ファームウェアのダウンロード

以下のzipファイルをダウンロードして保存してください。Remapでは使いませんが、キーマップJSONも同梱してあります。

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

## QMK ToolboxとVIAを使う場合

### ファームウェア・キーマップJSONのダウンロード

以下のzipファイルをダウンロードして保存してください。

- https://github.com/e3w2q/Kasumigasane-keypad/blob/main/firmware/e3w2q_kasumigasane_via.zip?raw=true

zipファイルの中のhexファイルとjsonファイルを取り出してください。

### QMK Toolboxのインストール

- [Releases ・ qmk/qmk_toolbox ・ GitHub](https://github.com/qmk/qmk_toolbox/releases)

からダウンロードし、実行します。Windowsの場合、「qmk_toolbox.exe」です。

Windowsでは最初の実行時に必要なドライバーをインストールするように求められます。

### QMK Toolboxを使ったファームウェアの書き込み

サリチル酸さんの解説ページがわかりやすいです。

- [（初心者編）自作キーボードにファームウェアを書き込む - 自作キーボード温泉街の歩き方](https://salicylic-acid3.hatenablog.com/entry/qmk-toolbox#QMK-Toolbox%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88%E6%97%A7%E8%AA%AC%E6%98%8E%E5%86%85%E5%AE%B9)

霞襲をPCに接続した状態で、QMK Toolboxの右上の「Open」をクリックし、先ほど取り出したhexファイルを選択し、「Flash」をクリックします。

霞襲の裏面中央のRESETと書かれたところの左右の穴をピンセットやクリップなどで短絡させると書き込みが始まります。

### VIAのインストール

- [Releases ・ the-via/releases ・ GitHub](https://github.com/the-via/releases/releases/tag/v1.3.1)

からダウンロードし、実行します。Windowsの場合、「via-*-win.exe」です。

### VIAでのキー書き換え

サリチル酸さんの解説ページがわかりやすいです。

- [（初心者編）VIAを使ってキーマップを書き換えよう - 自作キーボード温泉街の歩き方](https://salicylic-acid3.hatenablog.com/entry/via-manual#via%E3%81%AB%E3%82%AD%E3%83%BC%E3%83%9E%E3%83%83%E3%83%97%E3%81%8C%E3%83%9E%E3%83%BC%E3%82%B8%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%81%AA%E3%81%84%E5%A0%B4%E5%90%88)

VIAを起動したあと、左上の「File」→「Import Keymap」をクリックし、先ほど取り出したjsonファイルを選択します。

キー割り当てを変更できる画面が表示されます。

VIAの画面でキー割り当てを変更するとその都度キーボード側にも設定が反映されます。

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

