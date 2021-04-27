# for Raspberry Pi Test

##### Raspberry Pi Test用に作成したプロジェクト

Raspberry PiのGPIO応答速度 測定用プロジェクト

STマイクロ製Nucleo STM32F411用に作成しているが他のSTマイクロ STM32マイコンにも転用可能

青のプッシュボタンを押すとPC10にチャタリングを取ったトグル信号(押すたびにHigh/Lowがトグルする)を出力。

PA0,PA1をTimer2の両エッジトリガーのインプットキャプチャー入力としていてPA0をstartTime,PA1をendTimeとして記録。

endTimeを記録された時点で(endTime-startTime)を秒換算してresponnseTimeとして記録している。

Timerの分解能は1/84MHz(≒12ns)。
　　
このプロジェクトを使用してラズベリーパイのGPIO応答速度測定に関しての詳細は　　

https://neocode.jp/2021/04/28/raspberrypi_gpio/

を参照下さい。

＊注意点 ＊
このNucleoボードは元々は内部16MHz RC発振器使用の前提だが、別件で10MHzの外付け発振子を実装しており(元々は未実装)、本プロジェクトもそれをそのまま使用している。
購入したNucleoボードをそのまま使用する場合(普通はそうだと思いますが)、Clock Configuratinでクロック設定を実際のボードに合わせてください(HSI RC 16MHｚクロックを使用するようにする)。
