# 定理環境に tcolorbox を使いたい
何かいいtcboxの枠囲みを定義したら、それを定理環境の「命題n.m」などにも使いたいときのやり方。備忘録。

## 前提
- 動かしたのは overleaf (XeLaTeX) なのでそれ以外の動作は分からない
- tcolorbox および thmtools パッケージを読み込む必要がある
- tcbox を自作できるないしコピペでもいいから使える

## やり方
1. お気に入りのtcbox（ここでは`\mybox`）を定義する。
2. thmtools パッケージの `\declaretheoremstyle` で定理環境のスタイルを定義する。このとき、
   ```tex
   
