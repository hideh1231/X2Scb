# 🚀 hideh1231/X2Scb セットアップガイド

あなた専用のTwitter連携Scrapbox日誌システムの設定を完了させましょう！

**📋 設定の流れ**：テンプレートコピー → Tampermonkey → API設定 → Pages → 動作確認

## ✅ ステップ1: リポジトリのテンプレート利用（完了済み）

**🎉 このステップは完了しています！**
あなたは既に [tkgshn/X2Scb](https://github.com/tkgshn/X2Scb) テンプレートから `hideh1231/X2Scb` を作成済みです。

## 🔧 ステップ2: Tampermonkey + ユーザースクリプト

### 2.1 Tampermonkey拡張機能をインストール
1. [Tampermonkey公式サイト](https://www.tampermonkey.net/) からブラウザ拡張機能をインストール
2. Chrome、Firefox、Safari、Edgeに対応

### 2.2 ユーザースクリプトをワンクリックインストール
**⬇️ 今すぐクリックしてインストール ⬇️**

[![Tampermonkeyにインストール](https://img.shields.io/badge/Tampermonkey-ワンクリックインストール-00d000?style=for-the-badge&logo=tampermonkey)](https://github.com/hideh1231/X2Scb/raw/main/src/frontend/userscript/scrapbox-twitter-daily.user.js)

### 2.3 インストール確認
クリック後：
1. Tampermonkeyの新しいタブが開く
2. スクリプトコードが表示される
3. 「Install」をクリック
4. ✅ **完了！** Scrapboxでの連携が利用可能に

## 🔑 ステップ3: APIキー取得 + GitHub設定

### 3.1 必要なAPIキーを取得

#### Twitter API Bearer Token
1. [Twitter Developer Portal](https://developer.twitter.com/) にアクセス
2. プロジェクト → Keys and tokens → Bearer Token をコピー

#### OpenAI API Key
1. [OpenAI Platform](https://platform.openai.com/api-keys) にアクセス
2. 「Create new secret key」をクリック
3. 生成されたキーをコピー

### 3.2 GitHub Actionsシークレットに設定

**🔗 直接リンク**: [📋 シークレット設定画面](https://github.com/hideh1231/X2Scb/settings/secrets/actions/new)

以下の **4つのシークレット** を追加：

| Name | Secret | 説明 |
|------|---------|------|
| `TW_BEARER` | あなたのTwitter API Bearer Token | Twitter データ取得用 |
| `OPENAI_API_KEY` | あなたのOpenAI API Key | AI要約生成用 |
| `SCRAPBOX_PROJECT` | `hideh1231` | あなたのScrapboxプロジェクト名 |
| `TWITTER_USERNAME` | `hideh1231` | あなたのTwitterユーザー名 |

**設定手順**:
1. [シークレット設定画面](https://github.com/hideh1231/X2Scb/settings/secrets/actions/new) を開く
2. Name と Secret を入力して「Add secret」
3. 4つ全て繰り返す

## 🌐 ステップ4: GitHub Pages を有効化

1. **[リポジトリ設定](https://github.com/hideh1231/X2Scb/settings)** を開く
2. 左メニューから **「Pages」** をクリック
3. **Source** で **「GitHub Actions」** を選択
4. **「Save」** をクリック

**✅ 完了後**: `https://hideh1231.github.io/X2Scb/` でアクセス可能になります

## 🧪 ステップ5: 手動でAction実行

### 5.1 ワークフローを手動実行
1. **[Actions タブ](https://github.com/hideh1231/X2Scb/actions)** を開く
2. **「Daily Twitter Collection」** ワークフローをクリック
3. **「Run workflow」** → **「Run workflow」** をクリック
4. 実行完了まで待機（約2-3分）

### 5.2 実行成功の確認
- ✅ ワークフローが緑色のチェックマークで完了
- ✅ `public/` フォルダに新しいファイルが生成される
- ✅ [あなたのPages](https://hideh1231.github.io/X2Scb/) でデータが表示される

## 📱 ステップ6: 自分のPagesでツイート確認

### 6.1 生成されたデータを確認
1. **[あなたのPages](https://hideh1231.github.io/X2Scb/)** を開く
2. 昨日の日付のファイル（例: `2025-01-17.json`）が表示されることを確認
3. ファイルをクリックして、あなたのツイートデータが含まれていることを確認

### 6.2 Scrapboxで日付ページテスト

1. **あなたのScrapboxプロジェクト** を開く
2. **今日の日付ページ**（例: `2025/01/18`）に移動
3. **自動**: ページを開くと前日のツイートが自動で取得される
4. **手動**: URLに `?date=2025-01-17` を追加して特定日付を取得

### 6.3 動作確認のポイント
- ✅ モーダルウィンドウが表示される
- ✅ あなたのツイートが整形されて表示される
- ✅ 「コピー」ボタンでScrapboxにペースト可能
- ✅ AI要約が含まれている（OpenAI設定済みの場合）

          ## ✅ 設定完了チェックリスト

**📋 順序通りに完了させてください：**

### ステップ1: テンプレート利用
- [x] **リポジトリ作成** - テンプレートから `hideh1231/X2Scb` を作成済み

### ステップ2: Tampermonkey
- [ ] **Tampermonkey拡張機能** をブラウザにインストール
- [ ] **ユーザースクリプト** をワンクリックインストール

### ステップ3: API設定
- [ ] **Twitter API Bearer Token** を取得
- [ ] **OpenAI API Key** を取得
- [ ] **GitHub Actionsシークレット** を全て設定:
  - [ ] `TW_BEARER` を追加
  - [ ] `OPENAI_API_KEY` を追加
  - [ ] `SCRAPBOX_PROJECT` を追加
  - [ ] `TWITTER_USERNAME` を追加

### ステップ4: GitHub Pages
- [ ] **GitHub Pages** を有効化（Source: GitHub Actions）

### ステップ5: 動作確認
- [ ] **手動でAction実行** - ワークフローを手動実行
- [ ] **Pagesでツイート確認** - 生成されたデータを確認
- [ ] **Scrapboxでテスト** - 日付ページでインポートをテスト

**🎉 全て完了すると、毎日自動でツイート収集が開始されます！**

## 🔧 自動実行スケジュール

セットアップ完了後、システムは以下のスケジュールで自動実行されます：
- **毎日 9:00 AM (JST)** - 前日のツイートを自動収集
- **手動実行** - いつでもActionsタブから手動で実行可能

## 🆘 トラブルシューティング

### よくある問題
- **ワークフローが失敗**: シークレット設定を再確認
- **データが表示されない**: GitHub Pages の設定を確認
- **ユーザースクリプトが動作しない**: Tampermonkeyの有効化を確認

### サポート
- 📖 [元テンプレートのWiki](https://github.com/tkgshn/X2Scb/wiki)
- 🐛 [Issues](https://github.com/tkgshn/X2Scb/issues)

---

## 🎉 完了後の次のステップ

1. **このSETUP.mdファイルを削除**（もう必要ありません）
2. **README.mdを確認**（あなた専用の情報に更新済み）
3. **毎日のツイート収集を楽しむ**！

**設定完了おめでとうございます！ 🎊**

