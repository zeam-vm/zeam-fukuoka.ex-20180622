## ElixirのI/O処理の扱いについて

* システムの実行を司る**Scheduling Thread**と，I/Oを司る**Async Thread**が独立して存在する
* I/O処理をしたい時にはScheduling Threadからプロセス間通信でAsync Threadに処理を委ねる
* 1つのI/O処理は1つのAsync Threadが独占的に行う
* このため，マルチコア環境下でもI/Oに関して排他制御をする必要性がほとんど生じなくなる

