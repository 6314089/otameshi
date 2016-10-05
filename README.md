# otameshi
GitHubお試しのリポジトリ．

GitHubの使い方になれるためのリポジトリです．
好きなようにいじってもらって構いません．

##GitHubとGitの違い
Gitはバージョン管理のプログラム．
GitHubはそれを管理したりなんだりできるウェブサービス．

Gitが動画ファイルでGitHubがYoutubeみたいな感じ？

##Gitについて
GitHubをつかうにはGitが使えなければならない．
Gitの使い方は[こちら](https://git-scm.com/book/ja/v2)でダウンロードできる電子書籍を読めば理解できるはず．

##SourceTree
![SourceTree](images/sourceTree.png)
SourceTreeはGitをGUIで扱うアプリケーション．
ダウンロードは[公式ページ](https://ja.atlassian.com/software/sourcetree)からしてください．

これを使えばGitについてよく分かっていなくても，割りとなんとかなるかも．

##使い方
なにかうまくいかないことや分からないことがあったらSlack上で質問してくれれば誰かに手助けしてもらえるかもしれません．

###GitHubアカウントの作成
GitHubをアカウントも作成してください．
GitHubのアカウントを作成したらSlackの方でアカウント名を教えて下さい．
リポジトリへの書き込み権を付与します．
GitHubでは自分の作成したリポジトリ以外にはデフォルトでは書き込みできません．
リポジトリの管理者が書き込みの許可を与える必要があるようです．

###SourceTreeのインストール
SourceTreeのインストールをしてください．
途中でAtlassianのアカウントを作る必要があるかもしれません．
インストールは以下のページあたりでも参考にしてください．
- [Gitを視覚的に操作できる「SourceTree」のインストール方法 ](http://nelog.jp/sourcetree)
- [SourceTree for Mac インストールから初期設定の手順](http://glatchdesign.com/blog/web/tools/770)

GitHubのアカウントを登録しておくといいのかもしれません．
ここで登録しなくてもなんとかなるようですが．

###クローンする
作業をするためにGitHub上にあるものをコピーしてくる（クローンする）必要があります．以下でSourceTreeでのクローンの手順を説明します．

「新規/クローンを作成する」をクリックします．
![クローンを押す](images/img1.png)

クローン元のパスにクローンしたいGitHub上のリポジトリのurlを貼り付けます．
保存先のパスにはローカルの作業用のパスを設定してください．
最後にクローンをクリックします．
![クローン元とクローンする場所を選んでクローンする](images/img2.png)

クローンが完了しました．
![クローン完了](images/img3.png)

指定したローカルの場所にクローンされたものが配置されています．
このフォルダの中で作業を進めていきます．
![ローカル](images/img4.png)

###作業用ブランチを作成する
作業をはじめる前にブランチを作成します．

ブランチというのは歴史の分岐みたいな感じです．詳しくはGitについて各自調べてください．きちんと理解していなくても使っていくうちに分かるような気もします．

各自が作業をする前にそれぞれブランチを切って，その中で作業を行い，作業が完了してからその分岐を本流に合流させるという形で作業を進めていきます．このようにして進めることで，基本的に自分の作業用のブランチには他人の作業は混ざり込まなくなるので複数人で作業をしても混乱しにくくなります．

本流であるデフォルトのmasterブランチは全員の出来上がったプログラムが置かれている状況にします．作業が一段落した段階でmasterに合流させるようにすることで，このmasterブランチには基本的に作業途中の中途半端なのが混ざることがないようにします．

これで基本的にはmasterブランチと自分の作業用ブランチを追っていればOKな状況になります．

以下にSourceTreeでブランチを作成する手順を説明します．

まずはブランチをクリックします．
![ブランチをクリック](images/img5.png)

次に作りたい作業用ブランチの名前を入力してブランチを作成を押します．ブランチ名は他人とかぶらないようなものにした方がいいかもしれません．自分のアカウント名などを入れておくと被らなくていいかもしれません．ここでは単純なブランチ名を使っています．
![ブランチ名を入力](images/img6.png)

これで新しいブランチが作成されました．masterブランチから新しい作業用ブランチに移動した状態になっています．ブランチ名の左に二重丸がついているものが現在のブランチです．
![ブランチが作成された](images/img7.png)


->ブランチを作ったらそのブランチ内で作業する．
  ->作業の内容を登録するためにまずaddする．
    ->addしたものがコミットしたときに保存される．
  ->コミットを行う
    ->コミットメッセージは何か書かねばならない
  ->プッシュする
    ->プッシュすることでGitHub上に自分の変更が登録された
    ->プッシュする際にはGitHubのアカウント名とパスワードが必要かもしれません
    ->パスワード認証ではなくssh認証にすることもできるようです
      ->セキュリティが気になる人はsshにしておくといいかもしれません


一度pushしたら，プルリクエストを行う．
->プルリクエストとはGitHubの機能で自分の変更を取り込んでくれとリクエストするもの
->二種類ある
  ->フォークしてプルリクエストするもの
    ->こちらはオープンソースプロジェクトとか大規模な物で行われる
  ->同一のリポジトリ内でブランチを合成してほしいとリクエストするもの
    ->今回はこちらの機能を使う
->自分のブランチをmasterに取り込んでもらう様にプルリクを出す
->取り込んでもらえるような完成した状態でなくてもとりあえずプルリクを出す
->プルリクエストをとりあえず出しておいてそれから作業を続ける
  ->作業中であることを示すためにプルリクエストのタイトルに[wip]をつける
    ->work in progress
  ->作業をしたらaddしてcommitしてpushする．
  ->プルリクエストのページではみんながコメントをつけたりとかできる
    ->周りのメンバーが作業の様子を知ることができる
    ->作業中の段階から周りにコメントを貰うことができるので，作業中の段階からプルリクを出す．
  ->作業が終わったら[wip]を外す
->[wip]が外れたブランチはマージする
  ->マージできないときはmasterがブランチを切ったときより進んでいる場合
    ->masterを取り込んで，再度マージをする
    ->基本的にみんなバラバラのファイルを扱っていて，複数人で同じファイルを編集することはないだろうから，このような事態になることは少ないかもしれない．

GitHub上と自分のローカルを一致させるために適宜プルやフェッチすること．


以上で他の人の作ったプログラムのソースコードをメンバー間で共有することができ，他のメンバーの作業状況も知ることができるようになる．
