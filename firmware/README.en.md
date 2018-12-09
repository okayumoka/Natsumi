# About Firmware

Natsumi work with [QMK Firmware](https://github.com/qmk/qmk_firmware).

# How to build

Setup QMK Firmware, and execute this command.

(2018/10/13) There is no Natsumi's sources in original QMK Firmware repository.
So, please use [this repository](https://github.com/okayumoka/qmk_firmware) files.
QMK Firmwareの公式リポジトリにはNatsumi用のファイルが存在していないため、

```
$ make natsumi:default:avrdude
```


