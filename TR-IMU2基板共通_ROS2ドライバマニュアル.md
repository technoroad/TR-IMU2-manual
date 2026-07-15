<div class="title">TR-IMU2基板共通 ROS2ドライバマニュアル</div>

# 改訂履歴

| 版数 | 日付 | 変更内容 |
|---|---|---|
| 1 | 2026/06/30 | 新規作成 |

<div style="page-break-before:always"></div>

# はじめに

本書は、`TR-IMU-Platform2` および `TR-IMU16607` を ROS2 環境から利用するためのマニュアルです。  
ROS2 ドライバの導入手順、起動方法、および基本的な動作確認方法をまとめています。

接続した IMU の型番は起動時に自動検出されるため、型番ごとに設定を切り替える必要はありません。

基板単体の評価・動作確認や通信仕様に基づく直接利用方法は、`TR-IMU2基板共通_アプリケーションマニュアル.md` を参照してください。

<div style="page-break-before:always"></div>

# ROS2 ドライバの簡単な使い方

## 概要

ROS2 ドライバは本基板と通信する ROS 2 対応ソフトウェアです。  
姿勢推定四元数・加速度・角速度を同時に出力し、TF (Transform) 配信と IMU (Inertial Measurement Unit) トピック配信を行います。

## 想定環境

| OS | ROS 2 | ブランチ |
|---|---|---|
| Ubuntu 22.04 LTS | Humble | `humble` |
| Ubuntu 24.04 LTS | Jazzy | `jazzy` |

## 準備

USB ポート権限を設定します。

```bash
sudo adduser [your_user_name] dialout
```

反映のため、ログアウトまたは再ログインを行ってください。

## ワークスペース作成

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src
```

## ドライバ取得とビルド

サブモジュール（共通ライブラリ）を含めて取得するため `--recursive` を付けます。

```bash
cd ~/ros2_ws/src
git clone --recursive https://github.com/technoroad/ADI_IMU_TR_Driver_ROS2
cd ~/ros2_ws
rosdep update
rosdep install --from-paths src --ignore-src --rosdistro=${ROS_DISTRO} -y
colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release --packages-select adi_imu_tr_driver_ros2
source ~/ros2_ws/install/setup.bash
```

## 接続確認

基板を USB 接続したあと、ポート名を確認します。

```bash
ls /dev | grep ACM
```

例: `ttyACM0`

## 起動例

型番の選択は不要です（起動時に自動検出）。

```bash
ros2 launch adi_imu_tr_driver_ros2 adis_rcv_bin.launch.py
```

デバイスパスや配信レートを指定する場合は launch 引数で渡します。

```bash
ros2 launch adi_imu_tr_driver_ros2 adis_rcv_bin.launch.py device:=/dev/ttyACM0 rate:=100.0 with_rviz:=False
```

| 引数 | 既定値 | 内容 |
|---|---|---|
| `device` | `/dev/ttyACM0` | シリアルデバイスパス |
| `rate` | `100.0` | 配信レート [Hz] |
| `with_rviz` | `True` | RViz2 を同時に起動するか |

## 動作確認

- 基板を回転させ、RViz 上で IMU モデルの姿勢が追従すること
- `ros2 topic echo /imu/data_raw` で生データ（四元数・加速度・角速度）が流れること

出力例

```bash
ros2 topic echo /imu/data_raw
・・・
angular_velocity:
  x: -0.0116995596098
  y: -0.00314657808936
  z: 0.000579557116093
angular_velocity_covariance: [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
linear_acceleration:
  x: 0.302349234658
  y: -0.303755252655
  z: 9.87837325989
linear_acceleration_covariance: [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
・・・
```

## 補足

- 姿勢リセットや各種設定変更などのサービスコマンド、トピック構成の詳細は、ドライバリポジトリのドキュメントを参照してください。  
  https://github.com/technoroad/ADI_IMU_TR_Driver_ROS2
- 上手く動作しない場合は、まず評価用アプリまたは単体通信で USB 通信が正常か確認してください
