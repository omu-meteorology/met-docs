---
title: ガイドライン
description: ガイドラインを掲載しています。
sidebar:
  label: ガイドライン
  order: 1
---

このサイトのコンテンツを扱う上で順守すべき規約を掲載しています。

:::danger[警告]
これらの規約を故意に破ることが確認された場合、利用の禁止を命じることがあります。
:::

## 基本事項

- パスワードやAPI Tokenを外部に流出させないこと。
  - パスワードやセキュリティトークンが外部に漏れると、不正アクセスの危険性が高まります。パスワードやセキュリティトークンはセキュリティ上、極秘扱いとし、絶対に外部に公開したり、安全でない通信経路(TLS化されていないHTTP通信など)で送信したりしないでください。
- 第三者が提供するサービスへのアクセスは、そのサービスのガイドラインやポリシーを順守すること。
  - 特にスクレイピングを行う際は、レイテンシ(単位時間当たりのアクセス回数)を意識してプログラムを作成してください。
  - DOMツリーの操作は最低でも1秒に1回の頻度に留めておくことが無難です。

## プログラムについて

- ソースコードを外部に持ち出す際には十分に注意すること。
  - ソースコードには機密情報が含まれている可能性があり、外部に漏洩すると知的財産権の侵害や機密情報の流出につながる恐れがあります。ソースコードは厳重に管理し、許可なく外部に持ち出したり、共有したりしないでください。
- `.env`や`config.json`など、シークレットキーなどが入ったファイルをGitの管理対象に含めないこと。
  - 必ず`.gitignore`で管理対象から外す。シークレットキー(APIキー、データベース認証情報など)はソースコード内に直接記述しないでください。こうした機密情報がGitリポジトリにコミットされると、外部から簡単にアクセスできてしまう恐れがあります。`.gitignore`ファイルで適切に管理し、リポジトリに含めないようにしてください。
  - 万が一GitHubにpushしてしまった場合は、そのコミット履歴を削除することを徹底してください。