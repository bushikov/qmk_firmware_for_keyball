# 作業
1. フォークしたレポジトリをクローン
```
git clone --depth 1 -b keyball --recurse-submodules --shallow-submodules git@github.com:bushikov/qmk_firmware_for_keyball.git
```

2. キーマップとか修正

3. qmkとかのインストール
```
./util/qmk_install.sh
```
- 必要なライブラリとともにqmkをインストールしてくれるっぽい

qmkを個別にインストールする場合
```
brew install qmk/qmk/qmk
```

4. コンパイル
```
cd qmk_firmware_for_keyball

# 作成した設定（下は、qmk_firmware_for_keyball/keyboards/keyball/keyball61/keymaps/bushikovに作成した設定を指定）
make SKIP_GIT=yes keyball/keyball61:bushikov
```
- hexファイルが作成されるので、[Promicro Web Uploader](https://sekigon-gonnoc.github.io/promicro-web-updater/index.html)などで、インストールする

以下のコマンドでもコンパイルしてくれるらしい
```
qmk compile -kb keyball/keyball61 -km bushikov
```

## TIPS
- 自動マウスレイヤー（最後のレイヤー）で使えるのは、独自に定義したもの（KC_MY_BTN1とかKC_TO_CLICKABLE_INCなど）だけっぽい

## 参考
- [トラックボール付き自作キーボードをさらに使いやすくするファームウェア 【Keyball】【cocot46plus】](https://zenn.dev/takashicompany/articles/69b87160cda4b9)
- [keyballの自動マウスレイヤーに戻る・進むボタンを追加する方法](https://note.com/twoboy03/n/n791f11d7f261)
- ファームウェア
    - takashicompanyさんバージョン
        - [Keyball44](https://github.com/takashicompany/qmk_firmware/tree/keyball/keyboards/keyball/keyball44/keymaps/takashicompany)
        - [Keyball39](https://github.com/takashicompany/qmk_firmware/tree/keyball/keyboards/keyball/keyball39/keymaps/takashicompany)
        - [Keyball61](https://github.com/takashicompany/qmk_firmware/tree/keyball/keyboards/keyball/keyball61/keymaps/takashicompany)
    - [kamiichi99さんバージョン](https://github.com/kamiichi99/keyball/tree/main/qmk_firmware/keyboards/keyball)
    - [Yowkeesさんバージョン（オリジナル）](https://github.com/Yowkees/keyball/tree/main/qmk_firmware/keyboards/keyball)
- [QMKファームウェアの書き込み(Pro Micro Web Updater利用)](https://yushakobo.zendesk.com/hc/ja/articles/1500011696701)
  - ブラウザを使ってインストールできるPro Micro Web Updaterのやり方とか
- [Remap for qmk_firmware v0.18 or lower](https://qmk018.remap-keys.app/)
- [QMK Firmwareのキーコード一覧](https://github.com/qmk/qmk_firmware/blob/master/docs/keycodes.md)
- [keyballのための はじめてのQMK firmware環境構築 Mac編](https://note.com/yinouet1001/n/n856b45220ad4)
- [QMK Firmware公式ドキュメント](https://docs.qmk.fm/#/)
- [KeyBallのファームウェアをアップグレードするぞ](https://wecanpanic.hatenablog.com/entry/2023/02/05/KeyBallのファームウェアをアップグレードするぞ)
    - レイヤーを増やす、レイヤーのOLED表示、マウスの微調整などが参考になりそう

---
↓ オリジナル

# Quantum Mechanical Keyboard Firmware

[![Current Version](https://img.shields.io/github/tag/qmk/qmk_firmware.svg)](https://github.com/qmk/qmk_firmware/tags)
[![Discord](https://img.shields.io/discord/440868230475677696.svg)](https://discord.gg/Uq7gcHh)
[![Docs Status](https://img.shields.io/badge/docs-ready-orange.svg)](https://docs.qmk.fm)
[![GitHub contributors](https://img.shields.io/github/contributors/qmk/qmk_firmware.svg)](https://github.com/qmk/qmk_firmware/pulse/monthly)
[![GitHub forks](https://img.shields.io/github/forks/qmk/qmk_firmware.svg?style=social&label=Fork)](https://github.com/qmk/qmk_firmware/)

This is a keyboard firmware based on the [tmk\_keyboard firmware](https://github.com/tmk/tmk_keyboard) with some useful features for Atmel AVR and ARM controllers, and more specifically, the [OLKB product line](https://olkb.com), the [ErgoDox EZ](https://ergodox-ez.com) keyboard, and the [Clueboard product line](https://clueboard.co).

## Documentation

* [See the official documentation on docs.qmk.fm](https://docs.qmk.fm)

The docs are powered by [Docsify](https://docsify.js.org/) and hosted on [GitHub](/docs/). They are also viewable offline; see [Previewing the Documentation](https://docs.qmk.fm/#/contributing?id=previewing-the-documentation) for more details.

You can request changes by making a fork and opening a [pull request](https://github.com/qmk/qmk_firmware/pulls), or by clicking the "Edit this page" link at the bottom of any page.

## Supported Keyboards

* [Planck](/keyboards/planck/)
* [Preonic](/keyboards/preonic/)
* [ErgoDox EZ](/keyboards/ergodox_ez/)
* [Clueboard](/keyboards/clueboard/)
* [Cluepad](/keyboards/clueboard/17/)
* [Atreus](/keyboards/atreus/)

The project also includes community support for [lots of other keyboards](/keyboards/).

## Maintainers

QMK is developed and maintained by Jack Humbert of OLKB with contributions from the community, and of course, [Hasu](https://github.com/tmk). The OLKB product firmwares are maintained by [Jack Humbert](https://github.com/jackhumbert), the Ergodox EZ by [ZSA Technology Labs](https://github.com/zsa), the Clueboard by [Zach White](https://github.com/skullydazed), and the Atreus by [Phil Hagelberg](https://github.com/technomancy).

## Official Website

[qmk.fm](https://qmk.fm) is the official website of QMK, where you can find links to this page, the documentation, and the keyboards supported by QMK.
