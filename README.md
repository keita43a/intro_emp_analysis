# gakulab レポジトリ・テンプレート

↑タイトルもきちんと書く。

## 概要

gakulab内でレポジトリを作る際のテンプレートです。
レポジトリを作るときに、フォルダ構成やREADMEで説明すべき項目などがある程度決まっている方がわかりやすいので、
テンプレート化しておきます。

テンプレートの使い方は[ここを参照](https://docs.github.com/ja/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template)

実際に運用する際には、ここにプロジェクトの概要を簡潔に書きます。

## 説明

プロジェクトのもっと詳しい説明を書く場合は、ここに書く。
どういうプロジェクトなのか、分析の目的や結果はなんなのかを簡潔に。
もしわかりやすい図などがあればなおよい。

[gaku added 2022/07/07]　　　.Rprojと.gitignore　は　repoの下にいれる。

### このレポの使い方
0. Gitをインストールしておく。

1. レポのテンプレートから、Use this template->Create new repositoryでレポを作成。
2. `<> Code`をクリックして、URLをコピー。
3. Rstudioを開いて、New Project -> Version Control -> Git -> Repository URLにコピーしたURLを貼り、ローカルレポの名前をつける（リモートレポと同じ名前がよい）
4. READMEを編集する。(このセクションを消す。）
5. 最初のコミットをする。.Rprojや.gitignoreも含める。


## アウトプット

アウトプットとなる成果物をここに書いておく。主に論文とプレゼン

### 論文原稿
論文はGoogle docsの場合はここにURLを貼る。(Gakulab内の閲覧制限を掛けたものを推奨)
MSwordやLatexファイルを使う場合は、docsに保存する。

### プレゼンテーション
プレゼンはGoogle slidesの場合はここにURLを貼る。(Gakulab内の閲覧制限を掛けたものを推奨)
MSpowerpointやLatexファイルを使う場合は、docsに保存する。

## フォルダ構成

### `data`

データを保存するフォルダ。どういうデータか（どこから取得したか、データのレベルなど）を簡潔に説明する。
`raw`にはオリジナルのデータを保存する。この元データをいじってはいけない。読み込むだけ。データ元がどこかを明記する。プロジェクト外ですでにクリーニングされたデータの場合は、ここに入れてデータ元を明記する（どのデータフォルダのクリーニングデータか明記）。
`cleaned`は元データをデータクリーニングしたデータを保存する。どのコードでどうクリーニングしたか？

`processed`は分析の過程でコードで加工したデータを保存する。どのコードで加工したか？

### `docs`
ここでどういうドキュメントが保存されているかを説明する。
プロジェクトに関するドキュメントを保存する。必要に応じてサブフォルダを作ってもよい。

### `src`
scriptの略で、分析コード群をここに保存する。
`func`には分析を通じて用いる関数を定義する場合に、そのコードを保存する。
必要におうじてサブフォルダを作っても良い。(`data_process`,`main_analysis`,`visualization`など)
それぞれコードがどういうコードなのかを簡潔にここで説明する。

例：
`data_clean.R`: データクリーニングを行ったコード。
`main.Rmd`:　分析を行ったRマークダウンのコード。
`function_gaku.R`: 分析に必要な関数を定義したコード

可能であればmainのコードでは何がinput（データファイルなど）で、何がアウトプットか（さらなるデータか、図か）を示すとわかりやすい。

### `output`

コードで作成したものを保存するフォルダ。画像やテーブルなど。
srcに保存すると乱雑になるので分けて保存する。
必要に応じてサブフォルダを作ってもよい。現状は画像のフォルダ`fig`だけ作ってある。
