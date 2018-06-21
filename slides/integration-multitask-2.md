## 従来マルチタスク機構のスレッド構成

|スレッド名                      |関数名                           |個数     |
|:-----------------------------|:-------------------------------|--------:|
|Main Thread                   |erts\_sys_main_thread           |        1|
|Signal Handling Thread        |signal\_dispatcher\_thread\_func|        1|
|System Message Handling Thread|sys\_msg\_dispatcher\_func      |        1|
|Async Thread                  |async\_main                     |       10|
|Child Waiting Thread          |child\_waiter                   |        1|
|Scheduling Thread             |sched\_thread\_func             |論理コア数|
|Aux Thread                    |aux\_thread                     |        1|

