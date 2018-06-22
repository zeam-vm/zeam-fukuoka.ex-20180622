# 結果まとめ

1. Elixir/Rustler/OpenCL(GPU) は pure Elixir よりも1.75〜1.95倍高速です。
2. Elixir/Rustler/OpenCL(GPU) は Elixir/Rustler/CPU よりも1.5〜1.83倍高速です。
3. Erlang VM の実行コストと，リスト構造から配列に変換するコストが結構かかっています。リスト構造を最初から配列にする最適化も含めたElixirソースコードからの静的コンパイル/最適化をかけてやると，6.18〜6.88倍高速になる潜在的可能性があります。
4. C言語の実行時間とRust CPUの実行時間はほぼ等しいです。最適化をかけた場合には，Rustそのものによる実行時間のオーバーヘッドはないものと考えて良さそうです。
5. Python から pure Elixir は1.39〜1.54倍，Python から benchmarks9(Elixir/Rustler, OpenCL(GPU), inlining) は2.7倍，Python から Rust OpenCL は9.54倍の速度向上です。Python から Elixir に置き換えることで，このくらいの速度向上を期待できそうです
