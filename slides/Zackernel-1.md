# Zackernel

* 我々はC++11以降で採用された匿名関数でNode.js同様の機構を実装した
* RFIDのような極端に小規模で消費電力の少ないIoT用途を狙った
* 下記のプログラムは全体としてLED1を`TIC`ミリ秒間隔で繰り返し点滅する
  * `digitalWrite(LED1, HIGH/LOW);`はLED1を点灯/消灯する
  * `sleep`メソッドは，`TIC`ミリ秒の間休止した後，第2引数で与えられた関数を呼び出す
  * `[&] {...}`はC++11で導入された匿名関数の表記である
  * `zLoop`メソッドは，第1引数で与えられた関数を繰り返し呼び出す

```C++
void blinkLed1() {
  zLoop([&] {
    digitalWrite(LED1, HIGH);
    sleep(TIC, [&] {
       digitalWrite(LED1, LOW);
       sleep(TIC, [&] {});
    });
  });
}
```
