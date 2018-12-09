# ファームウェアについて

Natsumiは、[QMK Firmware](https://github.com/qmk/qmk_firmware)で動作します。

# ProMicroへの焼き込み手順

QMK Firmwareをビルドできる環境を整えてください。（ネット上にいろんな記事があるはずです。）

2018/10/13 QMK Firmwareの公式リポジトリにはNatsumi用のファイルが存在していないため、
[こちらのリポジトリ](https://github.com/okayumoka/qmk_firmware)を`git clone`して使用してください。

QMK Firmwareのディレクトリで、次のコマンドを実行してください。

```
$ make natsumi:default:avrdude
```

