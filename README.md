# VSCode Git Advice
ドリームキャリアの研修グループに対するVSCodeとGit使用アドバイス

### VSCodeのインデンテーション
インデントを整えることで、コードの可読性が向上し、バグなどを減らすことができます。

多くの現場では、VSCodeでインデントに<b>半角スペース（ホワイトスペース）で入力し、1階層は4文字</b>と設定しています。

VSCodeでインデントを設定する方法:
https://codelikes.com/setting-vscode-indent-tab-spaces/

### Gitの「No newline at end of file」問題について
https://docs.github.com/ja/get-started/getting-started-with-git/configuring-git-to-handle-line-endings?platform=windows より:

「<b>キーボードで return を押すたびに、行末と呼ばれる目に見えない文字が挿入されています。 行終端の処理は、オペレーティングシステムによって異なります。

Git と GitHub でコラボレートしているときに、あなたが Windows マシンで作業をしていて、コラボレーターが macOS で変更を加えた場合、Git により予想外の結果が生じることがあります。

異なるオペレーティングシステムを使用しているユーザとも効果的にコラボレーションができるように、自動的に行終端を処理するよう Git を設定することができます。</b>」

VSCodeでファイル末尾に自動的に改行を挿入することの設定方法:
https://qiita.com/kazuhito_nakayama/items/14c16f1b624ffd2f383c
