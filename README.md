# oshaku-obniz

サーボの使い方
https://obniz.com/ja/sdk/parts/ServoMotor/README.md

var servo = obniz.wired("ServoMotor", {gnd:0,vcc:1,signal:2});
servo.angle(180.0);



WS

https://qiita.com/hmaruyama/items/eee079f035f864638e13

https://obniz.com/ja/doc/reference/cloud/hardware-api/websocket-api



wss://obniz.com/obniz/6203-1656/ws/1



6203-1656
1220-5613

-------------------------

https://elchika.com/article/00000000-0000-0000-0000-000000000000/


目次
デモ動画
背景
材料

obniz Board 			https://akizukidenshi.com/catalog/g/gM-14930/
M5stickC		https://akizukidenshi.com/catalog/g/gM-15151/
両端ロングピンヘッダ 1×40 (40P 6.1)		https://akizukidenshi.com/catalog/g/gC-09056/
（オス−オスのジャンパーワイヤでも代用可能）
TowerPro サーボ MG996R		https://akizukidenshi.com/catalog/g/gM-12534/
遠隔お酌ライト版　外枠			https://make.dmm.com/item/1190592/
遠隔お酌ライト版　内枠♂		https://make.dmm.com/item/1190794/
遠隔お酌ライト版　内枠♀		https://make.dmm.com/item/1190793/
ダブルクリップ　８個
ブックエンド　２個


構成（配線と接続）
ソースコード


はじめに
オンライン飲み会で使える、面白アイテム
センサ付きのM5StickCをコントローラーとして、お酌する動作をすると
リモートにある、obnizに繋がった、装置が傾き、お酒を注ぎます。

システム概要
構成図
装置-サーボ-obniz- html/javascript -M5StaciC

組み立て




----------------

ネットワークの盗聴

どうやって盗聴しているのか、盗聴を防ぐ方法

初めに
情報を盗む行為（ネットワーク犯罪）は、下記の種類がありますが、
１.PCの内容を盗み取る行為
　.ウイルスに感染させ、そのウイルスがPCのデータを外部に送信する
2.ネットワークを流れているデータを見る行為
　PC内のExcelのファイルの内容は漏洩しないが、そのファイルをメールしたり、別のPCに移動した際に漏洩する
今回は２のことについての話です



盗聴器
盗聴に特別な機会は不要、パソコンを使います
有線LANであれば、パソコンにつなげるLANケーブルが必要です、
ケーブル切断して無理やり繋げるのであれば、ケーブルの作成装置とケーブルの中継装置（ハブと呼ばれる装置）が必要ですが
通常使う道具なので、秋葉原で売っています。
無線LANの場合、ノートPCについているものが使えます、後述しますが、電波が弱くても繋がるアンテナ付きの無線LANカードがあります
（盗聴目的でなく工場のような広い場所で無線LANを使う想定で売られている）

スニファと呼ばれる、ネットワークアナライザを使う、ネットワークやアプリのデータ通信の確認などで使うツールなので、特に怪しいツールではない。

∴いわゆる普通の盗聴器は、怪しい人が入手しますが、
ネットワークの盗聴は普通のエンジニアが入手する道具（ツール）でと盗聴出来てしまいます


盗聴方法

有線LAN
LANケーブルの接続口に盗聴器（パソコンなど）を仕掛ける？
→他のPCのデータは流れないので無理
（制御用のデータのみで、実データは流れない）

サーバールームのLANケーブルの接続口に仕掛ける
盗聴器取り付けは簡単だが、鍵がかかっているので、内部犯行でなければ難しい

基幹のLANケーブルの途中に接続
工事業者であれば、やりやすいかも



無線LAN(WiFi)
無線LANが届く範囲に盗聴器（パソコンなど）を設置、アンテナを用意すれば、通常届かないところでも受信可能
ステルス（SSIDが見えない）モードでもツールを利用すれば、盗聴可能
盗聴は、WiFiのパスワードが解かれば可能なので、そのWiFiにログインできる人は盗聴可能

なので、フリーWiFiは盗聴される可能性がある


プロバイダなどの通信業者に盗聴器が仕掛けられる
ないとは思うが、可能
宛先まで、複数の会社を通るので、その会社に盗聴器が仕掛けられる可能性も
（楽天の電話でcanon.jpにアクスルすると、楽天、IIJ、KDDI、NTT、キヤノンのように繋がっていた）


対処方法
通信するときは暗号化して通信する、盗聴されていても、暗号化して解読できなくする
SSLという暗号化が一般的

ブラウザの場合、
先頭に「http://」でなく「https://」を使う
（対応していないサイトもある）

注意：暗号化しても、宛先は暗号化されない
例）https://www.mizuhobank.co.jp/retail/index.html でログイン
IDやパスワードなどの通信内容は暗号化されるが、宛先（みずほ銀行にアクセスしたこと）は盗聴者にわかる
銀行のサーバで複合されるので、銀行内に盗聴器があったら盗聴者にわかる



アプリの場合、アプリが暗号化通信しているか、使う人は判らない
（製造している会社に問い合わせる）
iPhoneのアプリはSSL通信となっている


VPNを使って、PCの通信全体を暗号化させる
VPNのサーバの所まで暗号化される（トンネリングと呼ばれる）






VPN接続する


ネットワークの種類





無線LAN(WiFi)、有線LAN

盗聴のリスクは両方ある、
WEP、WPA、WPA2		TKIP、AES
ニンテンドーDS、10年以上前の古いPCやタブレットのWiFi
フリーWiFiは使って大丈夫？



http://とhttps://の違い
ブラウザのアイコン
送信フォームの内容や入力したパスワードは、大丈夫？



IPアドレスで個人が特定される？
