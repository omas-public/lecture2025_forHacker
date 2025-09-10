## [How To Become A Hacker](https://cruel.org/freeware/hacker.html)

## ハッカーって何(Hackers not Cracker)

ハッカーとは、コンピュータやネットワーク、プログラムなどの技術に精通し、創造的な方法で問題を解決したり、システムを改良したりする人のことです。元々は「高度な技術者」や「工夫する人」を指す言葉でしたが、現在ではセキュリティ分野での活動や、善意・悪意を問わずシステムの解析・改変を行う人も含めて使われています。

## ハッカーが作り出したシステム

- UNIXオペレーティングシステム
- インターネット（ARPANETなどの基礎技術）
- Git（バージョン管理システム）
- Apache HTTP Server
- TCP/IPプロトコル
- Python、Perlなどのプログラミング言語
- Linux,OpenBSDなどのオープンソースOS
- Tor（匿名通信システム）
- OpenSSH（セキュアな通信ツール）


## ハッカー的心構え

- この世界は解決を待っている魅力的な問題でいっぱいだ
- 同じ問題を二度解くような無駄はいやだ
- 退屈と単純作業は悪
- 自由は善
- 心構えは技能の代用にはならない

## 基本的なハッキング技術

- プログラミングを身につけること
    - コードを書くこと
    - コードを読むこと
- The Internet Network の仕組みをおぼえること
- オープンソース UNIX 類をどれか入手し、使いかたと動かしかたをおぼえること
    - Linux
    - MacOS
- World Wide Web の使い方を学び、HTML&javascript を書くこと
- まともに英語ができないならば、身につけること

## ParrotOSを使ってみよう

[公式サイト](https://www.parrotsec.org/)
ParrotOSとは、セキュリティやペネトレーションテスト、デジタルフォレンジクス、プライバシー保護などを目的としたLinuxベースのオープンソースOSです。多くのハッキング・解析ツールが標準で搭載されており、セキュリティ技術者や研究者、ハッカー向けに設計されています。軽量で使いやすく、匿名性や暗号化機能も充実しています。


### 事前準備

BIOS画面を立ち上げSecureBootをOFFにして保存しLiveUSBからの起動を行う

1. PCに配布されたUSBを差す
1. 電源をONしたらF2Keyを連打
1. BIOS画面 -> Security Tab -> Secure Boot OFF -> Save
1. 再起動したら今度はF12Keyを連打
1. 起動先をUSBに指定して起動

### お約束

PCインストールも兼ねているのでデスクトップのインストールアイコンは触らないこと

### Networkの設定

設定するIPアドレスは10.1.18.XXX(displayの番号)

1. ALT + T で　ターミナルを立ち上げる
1．IPアドレスを設定する
    - sudo nmcli -t device
    - sudo nmcli con mod デバイス名 ipv4.method manual
    - sudo nmcli con mod デバイス名 ipv4.addresses 10.1.18.XXX/24
    - sudo nmcli con mod デバイス名 ipv4.gateway 10.1.18.1
    - sudo nmcli con mod デバイス名 ipv4.dns "8.8.8.8,8.8.4.4"

### UNIXコマンドの基礎

- pwd
- ls
- cd
- touch ファイル名 
- rm ファイル名
- mkdir ディレクトリ(フォルダ)名
- rm -r ディレクトリ(フォルダ)名

### 日本語化

今回は特に必要ないが調べものをする際に日本語入力が必要になるかもしれないので
ターミナルに下記コマンドを入力

```sh
sudo apt update
sudo apt install task-japanese task-japanese-desktop
sudo localectl set-locale ja_JP.UTF-8
```

インストールが終わったら、一旦ログアウトして再度ログインする