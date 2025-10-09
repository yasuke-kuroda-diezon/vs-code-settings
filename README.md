## 使い方

- VSCodeのターミナルでgit操作を行うことを想定しています。
- 下記コマンドで管理します。

```
code ~/Library/Application\ Support/Code/User
```

## 参考リンク

- [VSCode 試行錯誤の末たどりついた設定管理術](https://zenn.dev/hacobell_dev/articles/52b383c05ab408)

## 方針

- VSCodeの設定管理に、プロファイルを導入します。
  - `ユーザー設定 < ⭐️プロファイル設定⭐️ < ワークスペース設定`

- 見た方が早く、以下の様な動作になります(60s)
  - https://diezon.gyazo.com/de4a2404dbec1e1551504718871abf62



- 「PHP開発時は、ユーザー設定 extends PHPプロファイル」
- 「Docker開発時は、ユーザー設定 extends Dockerプロファイル」

とすることで、
VSCode全体のグローバル設定を増やさず、軽量に保ち、ワークスペース設定(チームでgit管理してる)を汚さない様にします。

## プロファイル一覧

### docker
- Regolith／Regolith Headless案件でのDocker作業用プロファイルです。
- VSCodeでDockerを操作する際に便利な設定をまとめています。

- 拡張機能
  - Docker関連の拡張機能をインストール
- 対象ディレクトリ例
  - eccube-docker/
  - hazaiya-docker/
  - regolith-docker/
  - olta-docker/

---
### eccube
- Regolith案件でのSymfonyフレームワーク（PHP）開発用プロファイルです。

- 拡張機能
  - Symfony / PHP / Twig / YAML関連の拡張機能をインストール
- ユーザー設定
  - 単語をダブルクリックで選択する際、`$`を単語の一部として認識する設定
- 対象ディレクトリ例
  - hazaiya-docker/eccube_web/eccube/
  - ceralabo-docker/eccube_web/eccube/

---
### regolith-api
- Regolith Headless案件でのNestJSフレームワーク（TypeScript）開発用プロファイルです。

- 拡張機能
  - NestJS / TypeScript / Prisma ORM / GraphQL関連の拡張機能をインストール
- ユーザー設定
  - 単語をダブルクリックで選択する際、`@`を単語の一部として認識する設定
- 対象ディレクトリ例
  - regolith-docker/regolith-api-ctr/regolith-api/
  - olta-docker/regolith-api-ctr/regolith-api/

---
### regolith-admin / regolith-front
- Regolith Headless案件でのNext.jsフレームワーク（TypeScript）開発用プロファイルです。

- 拡張機能
  - Next.js / React.js / TypeScript / GraphQL関連の拡張機能をインストール
- 対象ディレクトリ例
  - regolith-docker/regolith-admin-ctr/regolith-admin
  - regolith-docker/regolith-front-ctr/regolith-front
  - olta-docker/regolith-admin-ctr/regolith-admin
  - olta-docker/regolith-front-ctr/regolith-front

---
### draw.io-view
- VSCodeでdraw.ioファイルを閲覧するためのプロファイルです。

```
aaa/
 ├ xxx.drawio
 ├ yyy.drawio
 └ zzz.drawio
```

上記のように拡張子が.drawioのファイルが複数ある場合、aaa/ディレクトリをVSCodeで開くことで、ファイルを横断して簡単にdraw.ioファイルを閲覧できます。
（Webブラウザではファイルをまたいで表示できないため、このプロファイルを作成しました）

---
### bash-script
- VSCodeでbash言語(bashシェルスクリプト)を書くためのプロファイルです。

- 拡張機能
  - bash言語サポート / 関連の拡張機能をインストール

---
### palyground
- 気になる設定や拡張機能を雑に試すプロファイルです。
- 気に入れば、他のプロファイルに取り入れることを検討します。

- 例：パフォーマンス改善の設定を行い、効果があるか試す.
  - [VSCodeが重いor不具合があるときに読む記事](https://qiita.com/osorezugoing/items/3a2ab8363cf41a2e245f)

```
"files.watcherExclude": {
  "**/.git/objects/**": true,
  "**/.git/subtree-cache/**": true,
  "**/.histroy/**": true,
  "**/.ipynb_checkpoints/**": true,
  "**/node_modules/**": true,
  "**/out/**": true
}
```