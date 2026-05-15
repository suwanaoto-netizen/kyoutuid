# ロジポケ モックアップ

ロジポケの管理画面HTMLモックアップ集です。各HTMLは外部依存（CDNのアイコンフォント）のみで動く単独ファイルなので、ローカルでもGitHub Pagesでもそのまま閲覧できます。

## 画面構成

| ファイル | 画面 |
| --- | --- |
| `index.html` | 共通ID管理 / サービス一覧（ホーム） |
| `users.html` | 共通ID管理 / ユーザー管理 |
| `organizations.html` | 共通ID管理 / 組織図管理 |
| `ledger.html` | 台帳管理 |

## 画面間の遷移

- **共通ID管理（index.html）** のサイドバーから `users.html` / `organizations.html` に遷移可能
- **共通ID管理** のサービスカード／ヘッダーの「ロジポケシリーズ」ドロップダウンから `ledger.html` に遷移可能
- **台帳管理（ledger.html）** のサイドバー「共通管理へ戻る」とヘッダーの「共通ID管理」から `index.html` に戻れる
- **台帳管理** のサイドバー「従業員管理（連動）」から `users.html`（共通ID管理のユーザー管理）に遷移
  - ユーザー管理は共通ID管理と台帳管理で連動している想定

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
├── index.html          # 共通ID管理 / サービス一覧（ホーム）
├── users.html          # 共通ID管理 / ユーザー管理
├── organizations.html  # 共通ID管理 / 組織図管理
├── ledger.html         # 台帳管理
├── README.md
└── .gitignore
```

## 依存関係

- [Tabler Icons](https://tabler.io/icons) — CDN 経由で読み込み (`@tabler/icons-webfont@2.44.0`)

ビルド工程は不要です。
