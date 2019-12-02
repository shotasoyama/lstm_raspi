# lstm_raspi

Raspberry Pi 3B+用パッケージ
ノートパソコン側に[パソコン用パッケージ](https://github.com/shotasoyama/lstm_note.git)も入れてください。

Raspberry Pi 3,3B  モデルは[こちら](https://github.com/shotasoyama/lstm)です。


## 動作環境

以下の環境を前提として動作確認しています。

* Ubuntu
  * Ubuntu 18.04 LTS
* ROS
  * ROS Melodic

## Start

以下を同時に実行

raspi側
```
 roslaunch lstm_raspi lstm.launch
```

パソコン側
```
 rosrun lstm_note repy_motor.py 
```

## 操作方法

### トレーニング

ロボットの前ボタンを長押しすると左横のLEDが点灯します。
この状態ではロボットがゲームパッドの操作を受け付け、
センサとモータの出力をeventというトピックに記録するようになります。
記録を終了するときは再び前ボタンを押して終了します。

### 学習

トレーニング終了後、ロボットの中ボタンを押すと
パソコンでLSTMモデルへの学習を開始します。

### リプレイ

学習を終了後、
ロボットの後ボタンを長押しするとリプレイがスタートします。
もう一度中ボタンを長押しすると終了します。

