# ロジポケ 共通ID管理 モックアップ

ロジポケ 共通ID管理画面のHTMLモックアップです。各HTMLは外部依存（CDNのアイコンフォント）のみで動く単独ファイルなので、ローカルでもGitHub Pagesでもそのまま閲覧できます。

## 画面構成

| ファイル | 画面 |
| --- | --- |
| `index.html` | サービス一覧（共通ID管理ホーム） |
| `users.html` | ユーザー管理 |
| `organizations.html` | 組織図管理 |

サイドバーから各画面へ相互に遷移できます。

## ローカルでの確認

ブラウザで `index.html` を直接開くだけで動作します。HTTPサーバーで配信する場合は以下のどちらでも構いません。

```bash
# Python
python3 -m http.server 8000

# Node.js
npx serve .
```

http://localhost:8000 にアクセスしてください。

## GitHub Pages で公開する

1. このリポジトリを GitHub にプッシュします。
2. リポジトリの **Settings → Pages** を開きます。
3. **Source** を `Deploy from a branch` にし、ブランチ `main`（または `master`）の `/ (root)` を選択して保存します。
4. 数十秒〜数分後、`https://<ユーザー名>.github.io/<リポジトリ名>/` で公開されます。

## ファイル構成

```
.
├── index.html          # サービス一覧（ホーム）
├── users.html          # ユーザー管理
├── organizations.html  # 組織図管理
├── README.md
└── .gitignore
```

## 依存関係

- [Tabler Icons](https://tabler.io/icons) — CDN 経由で読み込み (`@tabler/icons-webfont@2.44.0`)

ビルド工程は不要です。
