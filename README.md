# ソフトウェア部門 ダッシュボード

エスワイ・リンク社内向けの静的ダッシュボードです。  
GitHub Pages でホスティングし、サーバー・DB不要・無料で運用できます。

---

## 🚀 GitHub Pages の有効化手順（初回のみ・5分）

### 1. GitHubにリポジトリを作成

1. [github.com](https://github.com) にログイン
2. 右上 `+` → **New repository**
3. Repository name: `sw-dashboard`（任意）
4. **Public** を選択（Privateにする場合は GitHub Team プランが必要）
5. **Create repository** をクリック

### 2. ファイルをアップロード

```bash
# ターミナルを使う場合
git clone https://github.com/あなたのアカウント名/sw-dashboard.git
cd sw-dashboard
# このフォルダの全ファイルをコピー
git add .
git commit -m "initial"
git push origin main
```

または GitHub の画面で「Add file → Upload files」からドラッグ＆ドロップでもOKです。

### 3. GitHub Pages を有効化

1. リポジトリの **Settings** タブ
2. 左メニュー → **Pages**
3. Source: **Deploy from a branch**
4. Branch: **main** / **/ (root)**
5. **Save** をクリック

1〜2分後に以下のURLでアクセスできます：  
`https://あなたのアカウント名.github.io/sw-dashboard/`

---

## 📝 software.html の設定変更（1箇所）

`software.html` の以下の部分をあなたのGitHubアカウント名に変更してください：

```javascript
const OWNER = 'YOUR_GITHUB_USERNAME'; // ← ここを自分のアカウント名に変更
const REPO  = 'sw-dashboard';
```

---

## 📅 毎月の更新手順

| STEP | 作業 | 時間 |
|------|------|------|
| 1 | `ソフトウェア部門_売上分析_2024-2026.xlsx` の **月次入力シート** に当月データを入力 | 10分 |
| 2 | ダッシュボードを開いて「📁 Excelで更新」→ ファイルをアップロード | 1分 |
| 3 | グラフ・KPIが正しく更新されていることを確認 | 1分 |
| 4 | 「☁️ GitHubに保存」→ PAT を入力 → Push | 1分 |
| 5 | 1〜2分後に GitHub Pages に反映される | 待つだけ |

---

## 🔑 PAT（Personal Access Token）の取得

1. GitHub → 右上アイコン → **Settings**
2. 左下 → **Developer settings** → **Personal access tokens** → **Tokens (classic)**
3. **Generate new token** → `repo` にチェック → **Generate token**
4. 発行されたトークンをコピー（**一度しか表示されません**）
5. ダッシュボードの「☁️ GitHubに保存」欄に貼り付け（ブラウザが記憶します）

---

## 📁 ファイル構成

```
sw-dashboard/
├── index.html       ← ポータルトップ
├── software.html    ← ソフトウェア部門ダッシュボード（メイン）
└── README.md        ← このファイル
```

---

## 🛠 技術スタック

| 技術 | 用途 | コスト |
|------|------|--------|
| HTML / CSS / Vanilla JS | 静的ファイル | 無料 |
| Chart.js 4.4 | グラフ描画 | 無料（CDN） |
| XLSX.js 0.18 | Excelブラウザ解析 | 無料（CDN） |
| GitHub Pages | ホスティング | 無料（public repo） |
| GitHub REST API v3 | ファイル保存（PAT認証） | 無料 |

**月額費用：¥0**

---

## ⚠️ セキュリティ注意事項

- Public リポジトリの場合、**URLを知れば誰でも閲覧可能**です
- 機密性の高いデータを扱う場合は **Private リポジトリ + GitHub Team**（$4/人/月）をご検討ください
- PAT はブラウザの localStorage にのみ保存されます。GitHub には送信されません
