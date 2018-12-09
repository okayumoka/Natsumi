# Natsumi

Natsumiは、コンパクトな左右分割型の自作キーボードです。

## 特徴

- 左右分離型
- キー数は両手で52キーと比較的少なく、コンパクト
- 手の形に合わせて山なりに配置したキー配列
- ケーブル類はすべて上部から接続

## 準備物

このリポジトリの内容物に加えて、以下のものが必要です。

### 部品

* ProMicroまたはその互換品×2
* ダイオード（1N4148または1SS178）
* Cherry MXキースイッチ、またはその互換スイッチ
* キーキャップ
* 配線用ケーブル
* [3.5mm 4極ミニジャック 基板取付用 MJ-4PP-9](http://akizukidenshi.com/catalog/g/gC-06070/)（秋月電子で購入可能）
* 3.5mm ステレオミニケーブル
* M3ネジ 長さ8mm ×8本（ケースのフタ固定用）
* M3ネジ 長さ5mm ×2本（ProMicro固定用）

Arduino Microは左右に一つずつ、合計2台必要です。
ダイオード、キースイッチ、キーキャップはキーの数だけ必要です。

### 工具・その他

* 半田ごて、半田
* ヤスリ、カッター（筐体の微調整用）
* グルーガン（ホットボンド）
* 3Dプリンター（なくてもOK）

ケースを印刷するために3Dプリンターを利用しますが、
無い場合は[DMM.make](https://make.dmm.com/print/)などの3Dプリントサービスを利用したので問題ありません。
むしろ多くの場合は、3Dプリントサービスに発注したほうが精度の高いケースを入手できます。

### 入手先

部品、工具の入手先の一例です。

* [TALP KEYBOARD](https://talpkeyboard.stores.jp/)
  * ProMicro互換機、ダイオード、キースイッチ、キーキャップとすべて揃います。
  * AliExpressと比べるとさすがに高いですが、すぐ発送してくれる・国内配送なので安心感があります。
* [AliExpress](https://www.aliexpress.com/)
  * ダイオード以外をAliExpressで買うと一番安く収まると思います。
* [秋月電子](http://akizukidenshi.com/catalog/default.aspx)
  * ダイオード、半田付けの道具、配線用ケーブルなどが購入できます。
  * 3.5mm 4極ミニジャック 基板取付用 MJ-4PP-9 はここで購入できます。
  * 安く揃えるなら以下がおすすめです。
    * 高速スイッチング・ダイオード　１ＳＳ１７８（１００本入）
    * 半田ごて：ニクロムはんだこて　ＫＳ－３０Ｒ（３０Ｗ）
    * 半田：はんだ　０．８ｍｍ SD-62
    * こて台：はんだこて台　ＳＴ－１１
    * ケーブル：スズメッキ線0.6mm、耐熱電子ワイヤー2m×7色
* [Amazon](https://www.amazon.co.jp/)
  * キーキャップ、半田付けの道具などが購入できます。
  * RepRap Prusa i3など、自分で組み立てるタイプの3Dプリンターも比較的安く手に入ります。


### 1.ケースの作成

`case` 以下の3Dモデルがケースとなっています。
3Dプリンターか、3Dプリントサービスを利用して出力します。

自前の3Dプリンターで印刷する場合、素材はPLAがおすすめです。
キーボード筐体は平たく、薄いため、熱収縮の大きいABSで反らないように印刷することは難しいでしょう。

### 2.キースイッチはめ込み

筐体の穴にCherry MXキースイッチをはめ込みます。

3Dプリンターの精度によっては穴のサイズがまちまちなので、ヤスリとカッターで調整します。
削りすぎないように注意してください。

キーキャップを交換するときなどにキースイッチが抜けてしまうのが嫌な場合は、
グルーガンでケースと固定してしまうとよいでしょう。

### 3.ミニジャック固定

3.5mm 4極ミニジャックを筐体に固定します。穴サイズが小さい場合はヤスリで調整します。
固定はグルーガンがおすすめです。

### 4.配線（半田付け）

配線図(`wiring`以下のファイル参照)通りに配線していきます。
ダイオードの向きに注意してください。
キースイッチから伸びている先の数字は、ProMicroのピン番号です。

配線図は、スイッチを筐体にはめ込んで裏返した状態となっています。
表から見た状態ではないので注意してください。

また、ProMicroの互換品はMicro USBジャックが折れやすいものが多いので、グルーガンで補強すると良いでしょう。
ただし、コネクタ内部にグルーガンのボンドが入らないように注意してください。

![配線した状態](https://raw.githubusercontent.com/okayumoka/natsumi/master/pictures/picture_09.jpg)

### 5.ファームウェア書き込み

ProMicroにQMK Firmwareを書き込みます。
QMK Firmwareのビルド環境を構築した後、`make natsumi:default:avrdude`を実行してください。

(2018/10/14) QMK Firmwareの公式リポジトリにはNatsumi用のファイルが存在していないため、
[こちらのリポジトリ](https://github.com/okayumoka/qmk_firmware)を`git clone`して使用してください。

### 6.ProMicro固定、裏蓋装着

ProMicro固定用の部品とネジで固定します。
グラつくときは、固定用部品をグルーガンで接着してください。

その後、裏蓋をネジ止めします。

### 7.キーキャップはめ込み

お好みのキーキャップを取り付けて、完成です。

## License

MIT License

Copyright (c) 2018 okayu

