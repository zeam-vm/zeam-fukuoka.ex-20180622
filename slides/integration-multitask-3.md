## 各スレッドの役割 (1/2)

* **Main Thread**: シグナルを受信して，Singal Handling Thread に通知する
* **Signal Handling Thread**: シグナルハンドラ本体
  * Main Threadが受信したシグナルに相当するハンドラを起動する
* **System Message Handling Thread**: システムメッセージのハンドラ
  * システムメッセージは，トレース情報の出力やプロセスの再開・中断等をリクエストする特殊なメッセージである
* **Async Thread**: Erlang プロセスによるファイル操作を非同期に行う
  * プロセスが file モジュールを通じてファイルの読み書きや開閉を行うと，Scheduling Threadに代わってAsync Threadがそれらの処理を請け負う
  * Async Thread はバイトコードを解釈実行するScheduling Thread の動作を止めないために，処理を肩代わりする
  * スレッドの起床は `futex()`システムコールで行う
