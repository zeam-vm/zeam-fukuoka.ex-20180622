# 結果まとめ

1. Elixir/Rustler/OpenCL(GPU) は pure Elixir よりも**1.75〜1.95倍高速**です。
2. Elixir/Rustler/OpenCL(GPU) は Elixir/Rustler/CPU よりも**1.5〜1.83倍高速**です。
3. Erlang VM の実行コストと，**リスト構造から配列に変換するコスト**が結構かかっています。リスト構造を最初から配列にする最適化も含めたElixirソースコードからの静的コンパイル/最適化をかけてやると，**6.18〜6.88倍高速になる潜在的可能性**があります。
4. C言語の実行時間とRust CPUの実行時間はほぼ等しいです。最適化をかけた場合には，Rustそのものによる実行時間のオーバーヘッドはないものと考えて良さそうです。
5. Python / NumPy から pure Elixir は**1.39〜1.54倍**，Python から Elixir/Rustler/OpenCL(GPU)は**2.7倍**，Python から Rust OpenCL は**9.54倍**の速度向上です。CuPy と Elixir/Rustler/OpenCL(GPU)はだいたい同等でした。