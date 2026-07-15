# TR-IMU-Platform2 / TR-IMU16607 説明書

このリポジトリは、`TR-IMU-Platform2` および `TR-IMU16607` のマニュアル類をまとめたものです。

初めて使う場合は、最初に使用する製品を選んでください。そのまま該当する手順を上から読めるようにしています。

## TR-IMU-Platform2 の場合

`TR-IMU-Platform2` は、対応する ADI 製 IMU を取り付けて使うプラットフォーム基板です。

1. [TR-IMU-Platform2_ハードウェアマニュアル.md](./TR-IMU-Platform2_ハードウェアマニュアル.md) を確認し、取り扱い上の注意、電源条件、コネクタ位置を確認します。
2. 使用する IMU が対応しているか、[TR-IMU-Platform2_ハードウェアマニュアル.md](./TR-IMU-Platform2_ハードウェアマニュアル.md#対応-imu) の「対応 IMU」を確認します。
3. 使用する IMU に合わせて取り付けマニュアルを確認します。
   評価ボードを使用する場合は [TR-IMU-Platform2_取り付けマニュアル_評価ボード.md](./TR-IMU-Platform2_取り付けマニュアル_評価ボード.md)、`ADIS16575-2` を使用する場合は [TR-IMU-Platform2_取り付けマニュアル_ADIS16575.md](./TR-IMU-Platform2_取り付けマニュアル_ADIS16575.md) を参照してください。
4. [TR-IMU2基板共通_初回動作確認書.md](./TR-IMU2基板共通_初回動作確認書.md) に沿って、USB 接続とアプリで最低限の動作確認を行います。
5. 継続して評価・設定変更・データ取得を行う場合は、[TR-IMU2基板共通_アプリケーションマニュアル.md](./TR-IMU2基板共通_アプリケーションマニュアル.md) を参照してください。

## TR-IMU16607 の場合

`TR-IMU16607` は、`ADIS16607-2` をオンボード搭載した基板です。

1. [TR-IMU16607_ハードウェアマニュアル.md](./TR-IMU16607_ハードウェアマニュアル.md) を確認し、取り扱い上の注意、電源条件、コネクタ位置を確認します。
2. [TR-IMU2基板共通_初回動作確認書.md](./TR-IMU2基板共通_初回動作確認書.md) に沿って、USB 接続とアプリで最低限の動作確認を行います。
3. 継続して評価・設定変更・データ取得を行う場合は、[TR-IMU2基板共通_アプリケーションマニュアル.md](./TR-IMU2基板共通_アプリケーションマニュアル.md) を参照してください。

## 目的別の進み方

| やりたいこと | 読む資料 |
|---|---|
| 購入直後に動作するか確認したい | [TR-IMU2基板共通_初回動作確認書.md](./TR-IMU2基板共通_初回動作確認書.md) |
| Windows アプリや Python テストアプリで評価したい | [TR-IMU2基板共通_アプリケーションマニュアル.md](./TR-IMU2基板共通_アプリケーションマニュアル.md) |
| ROS2 で利用したい | [TR-IMU2基板共通_ROS2ドライバマニュアル.md](./TR-IMU2基板共通_ROS2ドライバマニュアル.md) |
| USB / UART で自作アプリから直接通信したい | [TR-IMU2基板共通_USB,UART通信仕様書.md](./TR-IMU2基板共通_USB,UART通信仕様書.md) |
| `TR-IMU-Platform2` を CAN FD で使いたい | [TR-IMU-Platform2_CANFD通信仕様書.md](./TR-IMU-Platform2_CANFD通信仕様書.md) |
| `TR-IMU-Platform2` に IMU 評価ボードを取り付けたい | [TR-IMU-Platform2_取り付けマニュアル_評価ボード.md](./TR-IMU-Platform2_取り付けマニュアル_評価ボード.md) |
| `TR-IMU-Platform2` に `ADIS16575-2` を取り付けたい | [TR-IMU-Platform2_取り付けマニュアル_ADIS16575.md](./TR-IMU-Platform2_取り付けマニュアル_ADIS16575.md) |
| TCP 変換基板経由で通信したい | [W55RP20-S2Eを用いたTR-IMU2基板TCP通信マニュアル.md](./W55RP20-S2Eを用いたTR-IMU2基板TCP通信マニュアル.md) |
| TR-IMU2基板を最新版にしたい | [TR-IMU2基板共通_ファームウェアアップデートマニュアル.md](./TR-IMU2基板共通_ファームウェアアップデートマニュアル.md) |
| ファームウェアを開発・ビルドしたい | [TR-IMU2基板共通_ファームウェア開発マニュアル.md](./TR-IMU2基板共通_ファームウェア開発マニュアル.md) |

## 資料一覧

### 共通資料

- [TR-IMU2基板共通_初回動作確認書.md](./TR-IMU2基板共通_初回動作確認書.md): 初回起動、Windows / Linux での最低限の動作確認
- [TR-IMU2基板共通_アプリケーションマニュアル.md](./TR-IMU2基板共通_アプリケーションマニュアル.md): 製品概要、Windows アプリと Python テストアプリの使い方、直接通信時の考え方
- [TR-IMU2基板共通_ROS2ドライバマニュアル.md](./TR-IMU2基板共通_ROS2ドライバマニュアル.md): ROS2 ドライバの導入、ビルド、起動、動作確認
- [TR-IMU2基板共通_USB,UART通信仕様書.md](./TR-IMU2基板共通_USB,UART通信仕様書.md): USB / UART のバイナリ通信仕様、コマンド
- [TR-IMU2基板共通_ファームウェアアップデートマニュアル.md](./TR-IMU2基板共通_ファームウェアアップデートマニュアル.md): ファームウェア更新手順
- [TR-IMU2基板共通_ファームウェア開発マニュアル.md](./TR-IMU2基板共通_ファームウェア開発マニュアル.md): STM32CubeIDE を使った開発環境構築と書き込み

### TR-IMU-Platform2 専用資料

- [TR-IMU-Platform2_ハードウェアマニュアル.md](./TR-IMU-Platform2_ハードウェアマニュアル.md): 仕様、対応 IMU、電源条件、コネクタ、機械情報
- [TR-IMU-Platform2_取り付けマニュアル_評価ボード.md](./TR-IMU-Platform2_取り付けマニュアル_評価ボード.md): ADI 製 IMU 評価ボードの取り付け手順
- [TR-IMU-Platform2_取り付けマニュアル_ADIS16575.md](./TR-IMU-Platform2_取り付けマニュアル_ADIS16575.md): `ADIS16575-2` の取り付け手順
- [TR-IMU-Platform2_CANFD通信仕様書.md](./TR-IMU-Platform2_CANFD通信仕様書.md): CAN FD 通信の仕様、CAN ID、コマンド

### TR-IMU16607 専用資料

- [TR-IMU16607_ハードウェアマニュアル.md](./TR-IMU16607_ハードウェアマニュアル.md): 仕様、電源条件、コネクタ、機械情報

### オプション資料

- [W55RP20-S2Eを用いたTR-IMU2基板TCP通信マニュアル.md](./W55RP20-S2Eを用いたTR-IMU2基板TCP通信マニュアル.md): W55RP20-S2E を使った UART-TCP 変換通信

## 関連リポジトリ

- [Windows用テストアプリ - technoroad/TR-IMU2-Monitor](https://github.com/technoroad/TR-IMU2-Monitor)
- [Pythonテストアプリ - technoroad/TR-IMU2-PythonTestApp](https://github.com/technoroad/TR-IMU2-PythonTestApp)
- [ROS2ドライバ - technoroad/ADI_IMU_TR_Driver_ROS2](https://github.com/technoroad/ADI_IMU_TR_Driver_ROS2)
- [基板ファームウェア - technoroad/TR-IMU2-STM32](https://github.com/technoroad/TR-IMU2-STM32)
