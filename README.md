zmk-config for charybdis (3x6)
nicenanov2
GERBER-adapter_Y13
left 3×6＋5
right 3×6＋3

## 左ロータリーエンコーダー（EC11互換・機械式）

左側は設定済みです。キーの割り当ては変更していません。

| エンコーダー端子 | nice!nano v2 のGPIO | Pro Micro互換表記 |
| --- | --- | --- |
| A相 | P1.11 | D14 |
| B相 | P1.13 | D15 |
| C / COM（回転接点の共通端子） | GND | GND |

端子の並びは製品のデータシートで確認してください。A/B/Cは回転用接点です。
押し込みスイッチの端子とは別です。押し込み動作は設定していません。
上の配線は機械式の接点を持つエンコーダー用です。
基板付きモジュールでは電源や出力電圧を別途確認してください。

- 全レイヤーで縦スクロールします。
- 回転方向が逆なら、A相とB相の配線を入れ替えてください。
- 回転量は現在 `steps = <12>`、`triggers-per-rotation = <10>` です。
  1クリックごとの動作量は製品のパルス数・クリック数に合わせて実機で調整してください。
- `charybdis.dtsi` でピンと回転量を定義し、
  `charybdis_left.overlay` と `charybdis_left.conf` で左のみ有効化しています。
- 左エンコーダーの信号は右の親機に送られます。通常使用には左右の接続が必要です。

### 左側で現在のキー・エンコーダー設定が使用していないヘッダGPIO

| GPIO | Pro Micro互換表記 |
| --- | --- |
| P0.08 | D0 |
| P0.06 | D1 |
| P0.17 | D2 |
| P0.20 | D3 |
| P1.06 | D9 |
| P0.10 | D16 |

これはファームウェア上の未使用一覧です。アダプター基板での接続や追加配線は別途確認してください。
P1.11/D14 と P1.13/D15 は左エンコーダーに予約済みです。
右側では同じGPIOをトラックボールに使用するため、この表は左側専用です。

参考:
- [nice!nano公式端子表](https://nicekeyboards.com/docs/nice-nano/pinout-schematic/)
- [ZMK v0.3のPro Micro端子対応](https://github.com/zmkfirmware/zmk/blob/v0.3/app/boards/arm/nice_nano/arduino_pro_micro_pins.dtsi)
