# Charybdis 3x6 — nice!nano v2 / GERBER-adapter_Y13

Left: 3×6 + 5 thumb keys + 5-way switch.
Right: 3×6 + 3 thumb keys + PMW3610 trackball (central).

## 左5方向スイッチ（AE-SKRHAAE010-BO）

ロータリーエンコーダーを廃止し、上下左右＋中央押し込みの5入力に変更しました。
従来の44キーの割り当ては維持しています。追加5入力は全レイヤー共通です。

| 基板端子 | nice!nano v2 GPIO | 互換表記 | 動作 |
| --- | --- | --- | --- |
| UP | P1.11 | D14 | 上矢印 |
| DW | P1.13 | D15 | 下矢印 |
| LT | P0.08 | D0 | 左矢印 |
| RT | P0.06 | D1 | 右矢印 |
| SW | P0.17 | D2 | マウス左クリック |
| +V | VCC (3.3V) | VCC | 基板の10kΩプルアップ電源 |
| GND | GND | GND | 接地（基板のGNDは2個のうち1個を接続） |

+Vは公式nice!nano v2のVCC（3.3V）に接続してください。RAW・電池＋・5Vには接続しません。
互換ボードの場合はその仕様と実際の電圧を確認してください。
既存のエンコーダーを取り外し、電源を切った状態で配線してください。

左のマトリクスと5個の独立したアクティブLOW入力を合成して読み取ります。
追加入力の順番はUP / DW / LT / RT / SWで、キーマップ末尾の5個です。
5msの押下・解放デバウンスを設定しています。
左側でVCC用の外部電源機能を有効にしています。

左右両方の最新ファームウェアを書き込んでください。
PCへの接続は右側です。実機で既存キーと追加5入力の押下・解放を確認してください。

残りの左ヘッダGPIO（設定上未使用）: P0.20/D3、P1.06/D9、P0.10/D16。
アダプター基板や追加配線による使用状況は別途確認してください。

参考:
- [モジュール回路図](https://akizukidenshi.com/goodsaffix/AE-SKRHAAE010-BO.pdf)
- [nice!nano仕様（VCCは3.3V）](https://nicekeyboards.com/docs/nice-nano/)
- [nice!nano端子図](https://nicekeyboards.com/docs/nice-nano/pinout-schematic/)
