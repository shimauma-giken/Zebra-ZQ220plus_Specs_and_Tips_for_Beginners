### Zebra-ZQ220plus_Specs_and_Tips_for_Beginners
# Zebra ZQ220 plus まとめサイト

Update: 2024/10/13

<br>

ZQ220の特徴や設定方法について、短時間で概要を要領よく理解したい方向けの記事です。


<br>

### 目次

<img width="500" src="https://www.link.com.bo/wp-content/uploads/2020/09/zq220-2.jpg">

1. 特徴・機能
2. 機器の基本的な操作方法
3. 基本設定の手順
4. 用紙の調整（キャリブレーション）
5. デモツール
6. 日本語の印刷方法（CPCL）
1. 参考文献

<br>
<br>

### 特徴・機能

<img width="500" src="https://www.link.com.bo/wp-content/uploads/2020/09/zq220-pagina-710x375.jpg">

携帯性とコストパフォーマンスを重要視したモデル。

1. 携帯性にすぐれた設計

   - 携帯に優れたサイズと重量（ 130 x 114 x 59mm, 390g）
2. 屋外ユースでも困らない機能

   - 外出先でも充電に困らない USB Type C コネクタを実装
   - 防塵防滴(IP54)性があるため、急な悪天候でも困らない
   - 1.52m の耐落下性能
   - 標準的なシフト時間を持続可能な大容量バッテリ(2250mAh)
3. お客様をお待たせしないパフォーマンス

   - Fast 起動機能（起動ボタン押下後、瞬時に起動完了）
4. 印刷処理に必要な基本機能を全て実装

   - Bluetooth/USB 接続I/F
   - ラベル、レシート印刷
5. 標準的なラベルサイズをサポート
6. 導入・保守コストを最小化したいお客様向けの価格体系

<br>
<br>

その他機能や詳細については下記リンクを参照すること。
[ZQ220 plus スペック](https://www.zebra.com/jp/ja/products/spec-sheets/printers/mobile/zq220-plus.html)

<br>
<br>

### 機器の基本的な操作方法

<img width="500" src="https://www.link.com.bo/wp-content/uploads/2020/09/LD0005681233_1.jpg">

電源ON/OFF、用紙の交換、各種機能については下記リンクの動画を参照すること。

[ZQ220 Plusのハウツービデオ](https://www.zebra.com/jp/ja/support-downloads/printers/mobile/zq220-plus.html#Tab-item-f2af9ec2d7-tab)

<br>
<br>

### 基本設定の手順

<img width="500" src="https://www.link.com.bo/wp-content/uploads/2020/09/zq220-3.jpg">

1. 接続、用紙設定を運用環境に合わせて設定しておくこと。
   コマンドによる設定に不慣れな方は下記リンクを参照すること。

[ZQ220+設定ガイド](https://www.zebra.com/jp/ja/support-downloads/printers/mobile/zq220-plus.html)

<br>
<br>

#### 一般的な運用でよく利用する設定項目

```
bluetooth.discoverable : on , Choices: on,off
bluetooth.minimum_security_mode : 2 , Choices: 2,4
media.sense_mode : bar , Choices: gap,bar
media.type : label , Choices: journal,label
print.tone : 100 , Choices: -100-200
print.print_adj : 0 , Choices: -30-30
ezpl.power_up_action : no motion , Choices: feed,no motion
ezpl.head_close_action : feed , Choices: feed,no motion
```

<br>
<br>

#### 設定コマンド（例）

```
! U1 setvar "bluetooth.discoverable" "on"
! U1 setvar "bluetooth.minimum_security_mode" "2"
! U1 setvar "media.sense_mode" "gap"
! U1 setvar "media.type" "label"
! U1 setvar "print.tone" "100"
! U1 setvar "print.print_adj" "0"
! U1 setvar "ezpl.power_up_action" "no motion"
! U1 setvar "ezpl.head_close_action" "feed"
```

<br>
<br>

##### 設定確認コマンド

```
! U1 getvar "bluetooth.discoverable"
! U1 getvar "bluetooth.minimum_security_mode"
! U1 getvar "media.sense_mode"
! U1 getvar "media.type"
! U1 getvar "print.tone"
! U1 getvar "print.print_adj"
! U1 getvar "ezpl.power_up_action"
! U1 getvar "ezpl.head_close_action"
```

<br>
<br>

### 用紙の調整

<img height="500" src="https://img.directindustry.com/ja/images_di/photo-g/5091-16840413.jpg">

ZQ220 plusが対応しているラベルは下記の通り。

- レシート
- 黒マーク

<br>

基本設定を実施後に下記コマンドを実行すること。

```
! U1 AUTOCAL
```

<br>
<br>

### デモツール

<img height="500" src="https://play-lh.googleusercontent.com/TbWAyJJPIbS1ZaHZzss_Rlq8eEU44MLbyAp4ii9mreD7_kW-JEE_4s_Rh85sQQa2p1U=w2560-h1440-rw">

[Google Play: Zlabel Designer](https://play.google.com/store/apps/details?id=com.zlabel.designer)

[Zlabelで新規ZQ220+プリンタをペアリングする方法](https://github.com/shimauma-giken/Zebra-Printer_Pair-ZQ220plus-with-Zlabel)

[ZQ200 デモガイド（簡易版）](https://github.com/shimauma-giken/Zebra-Printer_ZQ200_Demo_Guide)


<br>
<br>

### 日本語の印刷方法（CPCL）

<img height="500" src="https://thumb.photo-ac.com/18/1851d6c82d18a9d695adedf463868c27_t.jpeg">

<br>

プリンタ内部のフォントを用いて日本語フォントを印刷する場合の概要は下記の通り。

<br>

1. ZQ220+向けの日本語フォントファイルをプリンタにインストールする。利用可能なフォントは下記の通り。英数字のフォントはプレインストールされている。

   | フォントファイル | 概要                            | 入手方法                             |
   | ---------------- | ------------------------------- | ------------------------------------ |
   | JIS.DAT          | Shift-JIS用テーブル             | zebra.comからDL可能                  |
   | GT16NF55.CPF     | 固定長フォント（2mm）、ゴシック | 有償フォント                         |
   | GT16NF55.CPF     | 固定長フォント（3mm）、ゴシック | プリンタにプレインストールされている |


   <br>

   フォントのインストール状況は下記コマンドで確認可能。

   ```
   ! U1 getvar "file.dir"

   "  Directory
   LOWPOWER.WML       189
   INDEX   .WML       853
   INFO_TIM.WML       426
   INFO_ACK.WML       393
   CONFIG  .WML      3488
   ICON    .CPF      5084
   NSMTTC16.CPF    909344
   DEJAVU12.CPF      5323
   DEJAVU14.CPF      7001
   DEJAVU16.CPF      8183
   DEJAVU20.CPF     10288
   SWIS721 .CSF     22219
   GT16NF55.CPF    310456 ★
   GT24NF55.CPF    606448 ★
   JIS     .DAT     28232 ★
   8208000 Bytes Free
   ```
2. 日本語フォント（CPF）を用いて印刷するCPCLコードは下記の通り。

   <br>
    <br>

##### サンプルコード（Shift-JISで送信すること）

<br>

構文：

```
TEXT [FontNameOrNumber] [FontSize] [X] [Y] [Data]<CR><LF>
```

<br>

サンプルコード

```
! 0 200 200 600 1
COUNTRY JAPAN-S
TEXT GT16NF55.CPF 0 0 0 日本語ゴシック、サイズ 2mm
TEXT GT24NF55.CPF 0 0 30 日本語ゴシック、サイズ 3mm
PRINT
```

<br>
<br>

##### 印刷イメージ

```

日本語ゴシック、サイズ 2mm

日本語ゴシック、サイズ 3mm

```

<br>
<br>

##### 注意点

- 必ずShift-JISコードで送信すること。
- サポートしているフォントはゴシックで、明朝は非対応である。
- 固定長のフォントのみサポート。
- Link-OS Basic型のプリンタであるため、ZPL/ZBIは非対応。

<br>
<br>

### 参考文献

[CPCL Programming Guide for link-OS enabled Printer](https://www.zebra.com/content/dam/support-dam/en/documentation/unrestricted/guide/software/cpcl-link-os-pg-en.pdf)

[CPCL Programming Manual](https://www.zebra.com/content/dam/support-dam/en/documentation/unrestricted/guide/software/cpcl-pm-en.pdf)
