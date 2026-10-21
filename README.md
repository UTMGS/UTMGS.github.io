# UTMGS.github.io

UTMGSの公式サイトとブログです。Astroで静的サイトを生成し、GitHub ActionsからGitHub Pagesへデプロイします。

## ローカルでの確認

Node.js 24を用意してください。`.nvmrc` にバージョンを記載しています。nvmを使っている場合は `nvm install 24` と `nvm use 24` で切り替えられます。

```sh
npm ci
npm run build
npm run preview
```

開発サーバーで編集内容を確認する場合は、以下を実行します。

```sh
npm run dev
```

開発サーバーとプレビューのURLはターミナルに表示されます。`npm run build` が成功すれば、公開用ファイルが `dist/` に生成されます。

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

## 固定ページの追加

`src/pages/` に `.astro` ファイルを追加すると、ファイル名に対応するURLのページになります。たとえば `src/pages/about.astro` は `/about/` で公開されます。ブログ記事ではなく常設する案内ページなどに使います。

## GitHub Pagesへの公開

`main` ブランチへのpushでGitHub Actionsがビルドとデプロイを実行します。最初の公開前にGitHubリポジトリの **Settings → Pages → Build and deployment → Source** を **GitHub Actions** に設定してください。

カスタムドメイン `utmgs.com` は `public/CNAME` から公開成果物に含まれます。
