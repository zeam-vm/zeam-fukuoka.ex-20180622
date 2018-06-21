## 各スレッドの役割 (2/2)

* **Child Waiting Thread**: 子スレッドの終了を `waitpid()`で待ち受ける
* **Scheduling Thread**: `process_main()` を実行し，バイトコード解釈実行とプロセススケジューリングを行う
  * デフォルトでは論理コアと同じ数だけ生成される
  * 他の Scheduling Thread と比較して負荷が偏らないようにバランシングとプロセスマイグレーションを行う
* **Aux Thread**: 若干時間のかかる処理を受け持つ補助的なスレッド
  * メモリアロケーションやGCの情報を取得する際等に，Scheduling Thread から処理をオフロードされる
* 他に**NIF(Native Implemented Functions)**や**driver関係**のスレッドを起動することがある

