# WMG / WMOC 2027 公式ウェブサイト

このプロジェクトは、主にMarkdownと呼ばれる書式の簡単なテキストフォーマットでリッチなWEBサイトを生成する事ができるフレームワークを用いて World Masters Orienteering Championship 2027 兵庫大会の公式サイトを開発します。

フレームワークには、静的サイトジェネレータである [hugo](https://gohugo.io/) をベースに [hinode](https://gethinode.com/) テーマを用いたウェブサイトとなっています。

編集者の方は、次のツール群でサイトの内容を編集することができます。

* GithubのWEB上から直接編集する場合
    - Githubのアカウントが必要です。こちらからアカウントを作成してください。
    - ブラウザ上でGithubにログインし、その上で直接テキストファイルを編集することができます。
    - テキストの書式は Markdown という書式に則る必要がありますが、あまり複雑ではありません。事前に [このサイト](https://docs.growi.org/ja/guide/getting-started/markdown.html) 等をご覧いただき、書式に慣れておくと良いでしょう。とはいえ、ブラウザ上から直接編集する役割としては翻訳が主となりますので、書式等はあまり気にせず日本語個所を英語にするだけでよいでしょう。

* Github上のプロジェクトファイルを自分のPCに一度ロードして編集する場合
    少なくとも以下の環境をPC側にセットアップする必要があります。
    - Gitクライアント（ Git, TortoiseGit ）
    - テキストエディタ（ [vscode](https://winget.run/pkg/Microsoft/VisualStudioCode) が最も良い ）


## 環境構築

Windowsをお使いの場合、[このサイトを見てhugoをインストール](https://gohugo.io/installation/windows/)してください。たとえばWingetを使ってインストールされる場合は次の通りのコマンドをコマンドターミナルから入力いただければインストールされます。

``` powershell
> winget install Hugo.Hugo.Extended
```

## 編集から公開までの流れ

1. 事前にGit/Githubのセットアップを行ってください。
2. [wmoc2027/public_website](https://github.com/wmoc2027/public_website) から自分のリポジトリへフォークしてください
3. フォークしたリポジトリのSettingsにアクセスし、`Pages` メニューから、Sources設定を `Github Actions`を選んでください。
   ![](assets/2025-12-19-16-16-28.png)
4. 自分のGithubのリポジトリからローカルにクローンしてください。
5. VS Code等で編集を行いサイトを編集します。この際、次のコマンドでローカルPC上にhugoサーバが起動します。メッセージの最後に現れるURL（[http://localhost:1313/](http://localhost:1313/)）にブラウザでアクセスすることでプレビューを確認することができます。
   ``` powershell
   > hugo server -D
      :
     Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
     Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
     Press Ctrl+C to stop
   ```
   VS Codeで上書き保存するたびに自動的に再ビルドが行われ、プレビューに反映されます。編集した結果を確認した上で問題んかえれば適宜コミットを行ってください。
6. ひととおりの編集が終了したら、コミットした変更点をGithub上のリポジトリに反映します。pushを行ってください。
