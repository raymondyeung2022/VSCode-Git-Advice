# VSCode Git Advice
ドリームキャリアのエンジニアたちへのVSCodeとGit使用アドバイス

### VSCodeのインデンテーション
インデントを整えることで、コードの可読性が向上し、バグなどを減らすことができます。

多くの現場では、VSCodeでインデントに<b>半角スペース（ホワイトスペース）で入力し、1階層は4文字</b>と設定しています。

VSCodeでインデントを設定する方法:
https://codelikes.com/setting-vscode-indent-tab-spaces/

### Gitの「No newline at end of file」問題について
![DC_2023060802](https://github.com/raymondyeung2022/VSCode-Git-Advice/assets/119655633/7259f19e-831e-4953-9696-c73d40dc9ab4)

https://docs.github.com/ja/get-started/getting-started-with-git/configuring-git-to-handle-line-endings?platform=windows より:

「<b>キーボードで return を押すたびに、行末と呼ばれる目に見えない文字が挿入されています。 行終端の処理は、オペレーティングシステムによって異なります。

Git と GitHub でコラボレートしているときに、あなたが Windows マシンで作業をしていて、コラボレーターが macOS で変更を加えた場合、Git により予想外の結果が生じることがあります。

異なるオペレーティングシステムを使用しているユーザとも効果的にコラボレーションができるように、自動的に行終端を処理するよう Git を設定することができます。</b>」

これは元々Gitではなく、C言語における標準です。

参考リンク:
1. https://thoughtbot.com/blog/no-newline-at-end-of-file (英語)

上記の英語の文章に「History Lesson」のところ:

```So, it turns out that, according to POSIX, every text file (including Ruby and JavaScript source files) should end with a \n, or “newline” (not “a new line”) character. This acts as the eol, or the “end of line” character. It is a line “terminator”.```

\nまたは改行が「一行を終わらせるキャラクター」という意味です。
POSIXとは、https://e-words.jp/w/POSIX.html#google_vignette より、
「主にUNIX系OSに共通する機能などについて、プログラムからの呼び出し方法などの標準を定めた規格。」です。

2. https://stackoverflow.com/a/74062169 (英語)

```The reason is simple. One of the main purpose of git diff is display changes, unambiguously so that it can be used as a input to git apply. To do this, Git needs to know what it is supposed to do with newlines when applying a diff. Should it remove, keep or change them?```

「git diff」を実行する時、Gitが改行に対して、削除か、保留か、あるいは変更か、
明確に知りたいので、ファイルの最後に改行を付けるのが必要だからです。

VSCodeでファイル末尾に自動的に改行を挿入することの設定方法:
https://qiita.com/kazuhito_nakayama/items/14c16f1b624ffd2f383c

### Gitの「The head ref may contain hidden characters」問題について
![DC_2023060801](https://github.com/raymondyeung2022/VSCode-Git-Advice/assets/119655633/5e058277-1dea-4fff-b518-6e7055e47657)

ブランチ名に日本語があれば、プルリクエストを作成する時、上記のスクリーンショットの問題が発生します。

恐らく本来Gitでブランチを作成する時、Unicodeの入力が想定していないんだろうと思います。

大きな問題ではありませんが、この問題を避けたいなら日本語を入れない方がいいです。

参考:
ブランチ名標準的な命名規則(英語):
https://git-scm.com/docs/git-check-ref-format
