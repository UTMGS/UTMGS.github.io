# UTMGS.github.io

UTMGSの公式サイトとブログです。Astroで静的サイトを生成し、GitHub ActionsからGitHub Pagesへデプロイします。

## ローカルでの確認

Node.js 20.3.0以上を用意して、以下を実行します。

```sh
npm install
npm run dev
```

開発サーバーのURLはターミナルに表示されます。公開用ビルドは `npm run build`、ビルド結果の確認は `npm run preview` で行えます。

## ブログ記事の追加

`src/content/blog/` にMarkdownファイルを追加します。先頭にタイトル、概要、公開日を記述します。

```md
---
title: 記事タイトル
description: 記事の概要
pubDate: 2026-10-21
---

記事本文をMarkdownで書きます。
```

記事一覧と記事ページはビルド時に自動生成されます。

## GitHub Pagesへの公開

`main` ブランチへのpushでGitHub Actionsがビルドとデプロイを実行します。最初の公開前にGitHubリポジトリの **Settings → Pages → Build and deployment → Source** を **GitHub Actions** に設定してください。

カスタムドメイン `utmgs.com` は `public/CNAME` から公開成果物に含まれます。
