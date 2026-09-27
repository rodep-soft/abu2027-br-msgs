# abu2027-br-msgs

ABU2027 BR ロボットおよび STM32 マイコン間通信用の共有 ROS 2 メッセージ定義パッケージ（`robot_msgs`）。

## 含まれるメッセージ
* `Frame.msg`: CAN バスフレーム通信用
* `ImuData.msg`: IMU センサデータ（加速度・角速度）
* `MotorCommand.msg`: モータ指令（目標速度・トルクリミット）
* `MotorStatus.msg`: モータステータス（シーケンス・速度・電流・位置・イネーブル状態）
* `Ping.msg`: 生存確認・レイテンシ計測用カウンター

## 連携
* **PC 側 (`abu2027-br-pc`)**: `my_robot.repos` (vcs) 経由でクローンし `colcon build`。
* **STM32 側 (`br-stm32-proj`)**: Git submodule として取り込み、`msg2cdr.py` により Micro-CDR C ヘッダ（REP-2011 準拠型ハッシュ付き）を自動生成。
