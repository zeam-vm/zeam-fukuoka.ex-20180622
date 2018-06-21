# Node.jsのコード例

* Node.jsでは匿名関数を用いて非同期I/Oの処理を記述する
* 下記のコード例では`sleep.sleep(1000)`で1000ミリ秒間スリープし，その後，`.then()`の中に記述された匿名関数を呼び出している

```javascript
const sleep = require('sleep-async')().Promise;

const startTime = new Date().getTime();
console.log('startTime: ' + startTime);

sleep.sleep(1000)
  .then(() => new Date().getTime())
  .then(stopTime => {
    console.log('stopTime: ' + stopTime);
    console.log('Difference: '+((stopTime-startTime)/1000)+' [s]');
  });
```
