---
title: gimonfuを使ってはてなブログの記事を GitHub と同期させてみた ~その2~
draft: true
---

[:contents]

## 前回まで
[gimonfuを使ってはてなブログの記事を GitHub と同期させてみた ~その1~](https://10-minute-workouts.hateblo.jp/entry/2020/10/22/022955)

pushのワークフローを動かしてみたが記事が投稿されなかった　ところから

## やったこと
前回動かなかったところを確認してワークフローが動くようにしたのと、Github Actionを修正した。
- [otsubo666/hatenablog-article](https://github.com/otsubo666/hatenablog-article)

### Github Actionを修正
`pull.yaml`,`push.yaml` をそれぞれ修正。

- はてなブログから記事を同期するワークフローを手動実行に
  - `workflow_dispatch` triggerを実装して、手動実行できるように設定。
  - はてなブログから記事を同期させるブランチも手動パラメータから指定するようにしたが、実行ブランチを選ぶ形でも実現できたのかも？
- はてなブログへ記事を投稿するアクションについて、releaseブランチにマージされたときに実行されるように設定。

### 記事が投稿できなかった問題について
日付フォルダをちゃんとつくってあげればできる(はず)

### 詰まったところ
- [解決済]VSCodeでgit関連の拡張が動かなかった
  - VSCodeでgitが見つからないと言われた(Mac)
  - VSCodeで`git.path`を設定した。[Visual Studio Code で git.exe が 見つからないと言われた場合の対処](https://azriton.github.io/2017/12/18/Visual-Studio-Code%E3%81%A7git%E3%81%8C%E8%A6%8B%E3%81%A4%E3%81%8B%E3%82%89%E3%81%AA%E3%81%84%E3%81%A8%E8%A8%80%E3%82%8F%E3%82%8C%E3%81%9F%E5%A0%B4%E5%90%88%E3%81%AE%E5%AF%BE%E5%87%A6/)
  - Xcodeのライセンス同意を実行。[Agreeing to the Xcode/iOS license... のエラーがでた時の対処法](https://qiita.com/kazoo04/items/880283612abd85c0610a)

### 所要時間
60分ぐらい

Github Actionについて少しわかった。ようやくブログ投稿の準備がととのっただけなのでこれから頑張りたい。

あと、新しいTwitterアカウント連携を始めた。勉強系の活動はこっちでアウトプットしていく予定。
