# 結果まとめ

* とにかく，**ビルド設定に関しては，ほとんど何も考える必要なく OpenCL を駆動できた**のは素晴らしいです！
	* これは，Rust の ocl ライブラリと，Rustler の功績です。
	* NumPy 互換の CuPy で CUDA 経由で GPU を使うのにあれこれ煩雑な設定がたくさん要ることを考えると，この利点だけでも相当なアドバンテージです。

* ただし，**Rust プログラミングはかなり熟練が必要**です。
	* **コード1行書くのに1時間かかる**というのも決して誇張ではない状況です。
	* 今後の研究で**Elixir のコードからじかに コンパイルして GPU 駆動できるように**ライブラリを整備していきたいと思います。

