# TeX環境の設定、fortranの設定が上手くいかない学生へ

この資料は

+ TeX環境の設定がパソコンの都合で上手くいかなかった人
+ コンパイラの設定が上手くいかなかった人
+ 突然パソコンが壊れた人

向けに書いてます。ローカルの設定が全て白紙に戻ってもなんとかする方法をメモしておきます。

## Cloud環境のTeXの利用
インターネットブラウザさえあればTeXがオンラインで使えます。
色々ありますが、有名な二つを紹介しておきます。両者ともログインにはGoogleアカウントが使えるので、stu.kanazawa-u.ac.jpのアカウントで入ることが出来ます。
### Cloud LaTeX
https://cloudlatex.io/
アカリクが提供してるCloudで使えるTeXです。日本語での原稿に最初から対応してるのでおすすめです。
容量制限は1024 MBなので卒論修論の執筆にも問題なく使えると思います。
### Overleaf
https://ja.overleaf.com/
世界的に使われているオンラインTeX環境です。有料版では共同編集などが出来るようです。
日本語に対応したpLaTeX環境を作るために設定が必要です
https://doratex.hatenablog.jp/entry/20180503/1525338512
やることは
1. コンパイラにLaTeXを選択
1. latexmkrcというファイルを作る
1. 中身に以下の内容を書く
```
$latex = 'platex';
$bibtex = 'pbibtex';
$dvipdf = 'dvipdfmx %O -o %D %S';
$makeindex = 'mendex %O -o %D %S';
$pdf_mode = 3; 
```
これでコンパイルが出来るようになります。
### どっちが良いの？
「レポートを書く」ために使うならCloud LaTeXで良いと思います。参考に以下の記事を読んでください。
http://adhara.hatenadiary.jp/entry/2017/03/19/082818
## オンライン実行環境
オンラインでコードをコンパイルして出力を得ることも出来ます。
https://qiita.com/tttamaki/items/2b009aa957cfa4895d50
全世界にコードが共有される可能性があるので自己責任でどうぞ。  
