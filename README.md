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

###最初のコミットを行う
作業用ブランチを作成したら，その中で作業を行っていきます．

ローカルのクローンしてきたフォルダの中で作業を行っていきます．
ここではテキストファイルを一つ追加してみます．
![テキストファイルを追加する1](images/img8.png)

![テキストファイルを追加する2](images/img9.png)

GitHubのリポジトリはパブリックなので誰からでも見れるような状況になっています．著作権などに気をつけてあまり不適当なファイルは置かないように．

作業をすすめると，SourceTree上では「コミットされていない変更があります」と表示されます．
これから今加えた変更をコミットしていきます．
![コミットされていない変更があります](images/img10.png)

コミットとはGitにファイルを登録して変更履歴を記録することです．
保存したいものはとりあえずコミットすればOKです．

SourceTree上で「コミットされていない変更があります」の部分をクリックすると，「作業ツリーのファイル」という部分に先程作成したファイルが表示されています．
![hoge.txtが作業ツリーにある](images/img11.png)

これを選んで「Stage Selected」をクリックしてください．
![Stage Selected](images/img12.png)

hoge.txtがindexにステージしたファイルとなりました．
このindexにステージされたものが，コミットすることでGitに保存されます．Gitに保存したい場合は，保存したいファイルをindexにステージしてからコミットをする，と言った手順を取ることになります．
![hoge.txtがステージされた](images/img13.png)

Gitで保存管理したいファイルをステージしたら，コミットをクリックしましょう．
![コミットをクリック](images/img14.png)

コミットメッセージを追加してコミットをクリックすることでコミットが完了します．
コミットにはコミットメッセージが必須です．このコミットメッセージは後で見直すこともあるのでそれっぽいことを書いておきましょう．特に最初の一行が表示されることが多いので，一行で何をやったのかを適当にまとめておけばOKです．
![コミットメッセージを書いてコミットする](images/img15.png)

これでコミットが完了し歴史が進んだことが確認できると思います．
![コミットが完了した](images/img16.png)

まだコミットが完了したのは自分のローカルの中だけです．
GitHubの方にこのコミットを反映してやる必要があります．
そのためにはプッシュを行います．プッシュをクリックしてください．
![プッシュをクリック](images/img17.png)

プッシュするブランチを選びます．今作った作業用のブランチを選択してプッシュをクリックします．
![プッシュするブランチを選ぶ](images/img18.png)

初めてプッシュするときはGitHubのアカウントのユーザー名とパスワードを聞かれるかもしれません．きちんと入力をすればpushが完了するはずです．pushができないときはユーザー名やパスワードが間違っていないか確認しましょう．設定の中から確認変更ができるはずです．
リポジトリの変更権限がないという場合もあるかもしれません．そのときはSlack上でGitHubのアカウント名を教えて下さい．このリポジトリの変更権限をそのアカウントに与えます．
![ユーザー名とパスワードを入力](images/img19.png)

パスワード認証だけでなくsshでの接続もできるようです．
セキュリティ的に気になる人はsshにしておくといいかもしれません．
sshにしたい人は自分で調べてなんとかしてください．

ここまでの作業を終えたらブラウザでGitHubを眺めてみましょう．
自分の作ったブランチがGitHubの方に追加されているはずです．
このブランチを選択すると，自分の追加したファイルが存在すると思われます．
![GitHubを確認する](images/img20.png)

###プルリクエストをする
一度pushをしたら直ぐにPull Request（プルリクエスト，プルリク，PRとも）を行います．

####プルリクエストとは
プルリクエストとはGitHubの機能で，自分の変更を取り込んでくれとリクエストするものです．

プルリクエストには二種類あります．

一つはリポジトリをフォークしてから行うものです．
これはオープンソースプロジェクトみたいな，誰がプログラムを書くかわからないようなときとかそう言うので使われているようです．
今回はこちらは利用しません．

もう一方は，同一のリポジトリ内でブランチを合成してほしいとリクエストするものです．
先程作業用のブランチを作ったので，これをmasterに合流させてほしいとリクエストを出すことになります．
今回はこちらの機能を利用していきます．

####プルリクエストを出すタイミングとなぜプルリクエストを出すのか
取り込んでもらえるような完成した状態でなくても，ブランチを作成したらとりあえずPRをだしましょう．
PRでは，他のメンバーが作業過程を見たりコメントしたりすることができるようになるので，そちらの機能を使うためにも作業用ブランチを作ったらすぐにPRを出してしまいます．
PRを出さなくても作業用ブランチをmasterに合流させることはできますが，PRを出しておくことでGitHub上で他のメンバーに何をやっているのかを見てもらえるようになるので，PRを使っていきましょう．

####PRの出し方
GitHub上で現在のブランチがmasterであることを確認して，New pull requestボタンを押しましょう．
![New pull requestを押す](images/img21.png)

その次の画面では自分の作業用ブランチを選択します．
「この選択したブランチをmasterに合流してほしい」というリクエストを出すことになります．
![自分のブランチを選ぶ](images/img22.png)

次にPRの名前と説明を追加します．

先程の作業用ブランチをPRを出すことになるわけですが，作業中のブランチなのでまだmasterに取り込んでほしくはないです．
そこで名前の先頭にはwip（work in progress）とつけて，まだ作業中であることを示しておきましょう．
wipがついていないブランチは，作業が完了しているものとしてmasterにマージしていきます．
作業が終了した段階でこのwipを外すことになります．

名前と説明を追加し終えたら，Create pull requestボタンを押しましょう．
![名前と説明を書いてCreate pull request](images/img23.png)

自分で作成したり変更加えたりした直後のブランチならば，GitHubの上の方に表示されていることが有ります．こちらを利用したほうがお手軽にPRを作れるので，下のように表示されているときは，赤丸で囲ってあるボタンを押しましょう．
![お手軽にpull request](images/img24.png)

Create pull requestボタンを押すとPRが作成されます．
作成されたPRは以下のような画面になっています．
![個別PR画面](images/img25.png)

###作業をすすめる
PRを作成し終わったら実際に作業を進めていきましょう．
先ほど作成したテキストファイルに適当な文字を書いて保存してみます．
![テキストを編集](images/img26.png)

上書き保存を行うと，SourceTreeの方で「コミットされていない変更があります」と表示されます．またコミットを行いましょう．
![コミットされていない変更があります](images/img27.png)

自分が作業用のブランチにいることを確認して，編集したファイルをステージングしてコミットボタンを押します．
![コミットをする](images/img28.png)

コミットメッセージを書いてコミットを完了させましょう．
![コミットをする](images/img29.png)

コミットを終えると，GitHub上にあるものよりも自分のローカルにあるものが一つだけコミットが進んだ状態になります．自分のローカルの変更をGitHubの方に反映させるためにpushをしましょう．
![プッシュする](images/img30.png)

プッシュを終えるとPRの画面の方にコミットが追加されます．
wipでPRを作っておけば，他の人がPR一覧からPRのページに飛ぶことで，その作業の様子をGitHub上で確認できるようになります．
![プッシュが反映される](images/img31.png)

コミットは1つずつプッシュする必要はありません．いくつかまとめてプッシュをすることもできます．
こまめにプッシュをしたほうがGitHub上で表示される作業履歴と実際の作業履歴の差が少なくはなりますが．
![まとめてプッシュする](images/img32.png)

個別のPRの画面ではコメントを追加することができます．
他人の作業についてコメントを残したい場合とかに使っていきましょう．
議論が長くなる場合はSlackの方でやってもいいかもしれませんが．
![PR画面でコメントを書く](images/img33.png)

![PR画面でコメントを書く](images/img34.png)

コミットをクリックすることで，各コミットの個別のページに移動できます．
![コミットをクリック](images/img35.png)

![コミット画面](images/img36.png)

この画面では，ソースコードの行を指定して，その行に対してコメントをつけることができます．

コメント追加の横の隣のレビューというボタンはレビュー機能みたいです．
レビューを受けるまでマージできないようにするとかそういった機能のようです．詳しくは[こちら](http://qiita.com/terra_yucco/items/fa08bd2a4b498963a313)や[こちら](http://qiita.com/edwardkenfox/items/6340715d84f180832978)など．
この機能は使うほどでもないのかなと思っていますが．
![行コメント](images/img37.png)

行に対してコメントを付けたときのPRページの様子です．
![PR画面での行コメント](images/img38.png)

###作業完了したらマージする
作業が完了したらwipを外します．
EditをクリックしPRのタイトルからwipを取り除いて保存しましょう．
![Editを取り除く](images/img39.png)

![wipを消して保存する](images/img40.png)

本来ならばwipを外した人とマージする人は別人にするべきです．そうすることで作業した人と別の人が確認をしてからマージすることになるので，バグを防いだりできます．が，今回はそこまでする必要もないので，自分の作業用ブランチは自分で処理してしまいましょう．

これからwipを外した作業用ブランチをマージしていきます．
「Merge pull request」ボタンをクリックしましょう．
![Merge pull requestをクリック](images/img41.png)

マージコミットのメッセージを入力して「Confirm merge」をクリックしましょう．
![Confirm mergeをクリック](images/img42.png)

作業用ブランチをmasterに合流させることに成功したので，もう作業用ブランチは必要ありません．PR画面でマージを終えるとご丁寧にブランチ削除のボタンが表示されます．「Delete branch」をクリックしましょう．
![Delete branchをクリック](images/img43.png)

ブランチが削除されました．
![ブランチが削除された](images/img44.png)

マージとブランチの削除をGitHub上で行ったので，ローカルの方ではまだブランチの合流も削除もされていない状況になっています．SourceTreeに表示されているローカルの方をGitHubに同期していきましょう．

まずはmasterブランチの方に移ります．「master」をダブルクリックしましょう．
![masterをダブルクリック．](images/img45.png)

masterブランチに移ったことを確認します．
![masterブランチに移った](images/img46.png)

masterに移ったらプルをします．プルをクリックします．
![プルをクリックする](images/img47.png)

okを押します．
![okを押す](images/img48.png)

するとローカルの方でも作業用ブランチがmasterにマージされた状況になります．
![マージされた](images/img49.png)

次にフェッチも行います．フェッチをするとGitHub上の他の人のブランチの情報とか，GitHub上で削除したブランチの情報を持ってくることができます．
![フェッチする](images/img50.png)

![フェッチする](images/img51.png)

これでGitHubの作業用ブランチが削除されたことがローカルの方に反映されたので，「origin/add_text_file」ブランチは消えています．
最後にローカル専用のoriginのついていない「add_text_file」を削除します．

masterブランチにいることを確認して，「add_text_file」の上で右クリックして「add_text_fileを削除」を選びます．
これで一通りマージが完了しました．
![ローカルのブランチを削除](images/img52.png)

プルとフェッチの違いや「origin/add_text_file」と「add_text_file」の違い，そもそも「origin」とは何かなどが気になる人は各自Gitを勉強してください．割とややこしいので別に調べなくても何とかなるかもしれません．

###マージできないとき
場合によってはマージできないことがあるかもしれません．
![マージボタンが押せない](images/img53.png)

マージできないときはmasterがブランチを切ったときより進んでいてコンフリクトを起こした場合です．このときは一旦作業用ブランチの方に最新のmasterを取り込んでから，作業用ブランチをmasterに合流させます．

今回は複数人同時に同じファイルを編集したりしないので，基本的にマージできないような状況にはなりませんが説明だけしておきます．

マージできないときは，まずはローカルのmasterを最新にする必要があります．上の方で説明しているとおりにmasterをプルしましょう．

下の画像はマージできないときにプルしてmasterを最新にした時の様子です．
2つのブランチで同じテキストファイルを編集してしまいました．
現在いるブランチとは別の黄色いブランチの方が先にmasterにマージしてしまったので，このブランチをコンフリクト無しでmasterに合流させることはできません．

この場合は一旦masterを現在の作業用ブランチの方に取り込みます．
masterブランチでプルしてmasterを最新にしてあることを確認して作業用ブランチに移りましょう．
作業用ブランチにいることを確認してマージボタンを押しましょう．
![マージボタンを押す](images/img54.png)

そしたらmasterの部分をを選択します．そしてOKを押しましょう．
![masterを選択してOK](images/img55.png)

するとコンフリクトを起こすのでエラーになります．
このエラーが出ると，マージコンフリクト解決中のモードになります．
![エラーが出る](images/img56.png)

エラーが出た後でファイルを開いてみると，「<<<<<<< HEAD」，「=======」，「>>>>>>> master」などが追加されているのがわかります．
「\nfooboo\nFooooo!」というのが今回の作業用ブランチで追加したものです．
「FizzBuzz」というのがもう一方の黄色いブランチの方で作業した内容です．Gitがコンフリクトを起こした部分について，両方の変更点を1つのファイルに纏めてくれているわけですね．
![マージコンフリクト](images/img57.png)

編集をして両方の変更を問題なく融合させたファイルを作成して上書き保存しましょう．
![コンフリクト解消](images/img58.png)

マージ時にコンフリクトを起こしてエラーが出た場合はマージコンフリクトを解消させるためのモードになっています．マージと表示されていることを確認しましょう．

ファイルを変更して保存したのでコミットされていない変更がある状態になります．

マージコンフリクトを起こした後，コミットを行うとそのコンフリクトを解消したものと判断してマージを行ってくれます．
![マージコンフリクト解消コミット](images/img59.png)

コミットを終えることで作業用ブランチに最新のmasterブランチを取り込むことができました．
これで作業用ブランチに最新masterを取り込んだので，作業用ブランチをmasterに安全に合流させることができるようになりました．
![安全に合流できるように](images/img60.png)

GitHub上で「Merge pull request」ボタンが押せるようになりました．
![Merge pull requestできる](images/img61.png)

マージを完了させてブランチの削除等も行うと以下のようになります．
![マージ完了](images/img62.png)

![マージ完了](images/img63.png)

複数人で同じファイルを同時に編集したりしなければ，こんな面倒なことにはならないと思います．

###README.mdについて
README.mdはGitHub上で特別な扱いのファイルです．
フォルダの中にREADME.mdファイルが存在すると，そのファイルの中身をGitHub上でいい感じに表示してくれるようになっています．

実際にREADME.mdファイルを作成してみましょう．

今までと同じように作業用ブランチを作成し作業を進めていきましょう．

まずフォルダを作成します．
作業用フォルダ内に自分のアカウント名のフォルダを作成しましょう．
![アカウント名のフォルダ作成](images/img64.png)

そのフォルダの中に「README.md」と言う名前のファイルを作成します．
![README.md追加](images/img65.png)

README.mdと言うのはマークダウンファイルです．

マークダウンの表記方法については以下のページなどを参考にしてください．マークダウンについてはネット上にたくさん解説があると思うので各自調べてください．
- [
README.mdファイル。マークダウン記法まとめ](http://codechord.com/2012/01/readme-markdown/)
- [翻訳 GitHub Help - GitHub Flavored Markdown](http://qiita.com/qurage/items/a2f3f52c60d7c64b2e08)
- [Markdownで行こう！ ](https://gist.github.com/wate/7072365)
- [文章作成やメモ書きにも便利、Markdown記法](http://kojika17.com/2013/01/starting-markdown.html)

何かマークダウン記法で書いてコミットしてプッシュしてみてください．
![コミットをした](images/img66.png)

GitHub上でフォルダが追加されているのが確認できます．
![GitHub上](images/img67.png)

フォルダの中を見るとREADME.mdで書いた内容がいい感じに整形されて表示されていると思います．
![いい感じにREADME.mdの内容が表示](images/img68.png)
