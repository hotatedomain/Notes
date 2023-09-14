# 定理環境に tcolorbox を使いたい
何かいいtcboxの枠囲みを定義したら、それを定理環境の「命題n.m」などにも使いたいときのやり方。備忘録。

## 前提
- 動かしたのは overleaf (XeLaTeX) なのでそれ以外の動作は分からない
- tcolorbox および thmtools パッケージを読み込む必要がある
- tcbox を自作できるないしコピペでもいいから使える

## やり方
1. お気に入りのtcbox（ここでは`\mybox`）を定義する。
2. `\mybox` を使う style を thmtools パッケージの `\declaretheoremstyle` で定義するのだが、`headformat` で調整する
   ```tex
   \declaretheoremstyle[
   ..., (その他のオプション(今回は関係ない))
   headpunct={}
   headformat={\mybox{\NUMBER\ \NAME\NOTE.}}
   ]{mystyle}
3. mystyle を style に指定した定理環境では番号、名前、注釈までが `\mybox` で囲われる

## 後書き
- 有名かもしれないけど、定理環境の外の枠を tcolorbox でいじることしかやっていなかったので、中のデザインにも tcbox が使えて驚いた
- `headformat` の自由度が高いのでさまざまな指定ができる
- `headpunct={}` を指定して `headformat` にピリオドを打ち込んでいるのは、こうしないとピリオドが枠の外に出てしまうため。解決法はあるかもしれないけど分からない
