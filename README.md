# 📱 X2Scb - あなたのTwitter連携Scrapbox日誌

> ✅ **設定完了済み！** - このリポジトリは hideh1231 さん専用に設定されています。

## 🎯 ユーザースクリプトのインストール

**Scrapbox連携の最初のステップ**: 以下のボタンでTampermonkeyに直接インストールしてください！

[![Tampermonkeyにインストール](https://img.shields.io/badge/Tampermonkey-インストール-00d000?style=for-the-badge&logo=tampermonkey)](https://github.com/hideh1231/X2Scb/raw/main/src/frontend/userscript/scrapbox-twitter-daily.user.js)

または、手動でインストール：
- [ユーザースクリプトファイル](https://github.com/hideh1231/X2Scb/raw/main/src/frontend/userscript/scrapbox-twitter-daily.user.js) を開く
- Tampermonkeyで「新しいスクリプト」を選択してコードをコピー＆ペースト

## 📖 概要

X2Scb は、hideh1231 さんの日々のツイートを自動的に収集し、Scrapboxのページへ簡単にインポートできる形式に整形するシステムです。

## ✨ 現在の機能

- 🔄 GitHub Actions による**ツイート自動収集** (毎日9時に実行)
- 🤖 OpenAI による**AI要約機能**
- 📋 Scrapbox 互換の**整形機能**
- 🌐 **GitHub Pages デプロイ** - [https://hideh1231.github.io/X2Scb/](https://hideh1231.github.io/X2Scb/)
- 🔧 **ブラウザユーザースクリプト** - Scrapbox と完全連携

## 🚀 簡単5ステップでセットアップ

**📋 この順序で設定してください**：

### 1️⃣ Tampermonkey + スクリプトインストール
上の緑色の **「Tampermonkeyにインストール」** ボタンをクリック
→ Scrapbox連携が有効になります

### 2️⃣ APIキー取得 + シークレット設定
Twitter・OpenAI のAPIキーを取得して [📋 シークレット設定](https://github.com/hideh1231/X2Scb/settings/secrets/actions/new) に追加

### 3️⃣ GitHub Pages 有効化
[リポジトリ設定](https://github.com/hideh1231/X2Scb/settings) → Pages → Source: GitHub Actions

### 4️⃣ 手動でAction実行
[Actions タブ](https://github.com/hideh1231/X2Scb/actions) → 「Run workflow」で動作確認

### 5️⃣ Scrapboxでテスト
日付ページでツイートが自動インポートされることを確認

**🎉 設定完了後の動作**:
- **毎日 9:00 AM (JST)** に自動でツイート収集
- **Scrapbox日付ページ** で前日のツイートを自動取得
- **手動インポート**: `?date=YYYY-MM-DD` で特定日付も取得可能

## 🔧 設定状況

- ✅ **ユーザースクリプト**: hideh1231/X2Scb 用に設定済み
- 🔄 **GitHub Actions**: 日次実行ワークフロー準備完了
- 📁 **公開データ**: [https://uithub.com/hideh1231/X2Scb/tree/main/public](https://uithub.com/hideh1231/X2Scb/tree/main/public)

## 📋 次のステップ

**[SETUP.md](SETUP.md) ファイルを確認してください** - 以下の設定が必要です：

1. 🔑 **API 設定**: Twitter Bearer Token、OpenAI API Key を取得
2. 🌐 **GitHub Pages**: リポジトリ設定でPages を有効化
3. 🔐 **シークレット設定**: [📋 こちら](https://github.com/hideh1231/X2Scb/settings/secrets/actions/new) で以下を追加
   - `TW_BEARER` = あなたのTwitter API Bearer Token
   - `OPENAI_API_KEY` = あなたのOpenAI API キー
   - `SCRAPBOX_PROJECT` = `hideh1231` (あなたのScrapboxプロジェクト名)
   - `TWITTER_USERNAME` = `hideh1231` (あなたのTwitterユーザー名)
4. 🧪 **テスト実行**: 手動で Actions を実行して動作確認

### 🚨 重要: API設定が最優先です

まず **[シークレット設定](https://github.com/hideh1231/X2Scb/settings/secrets/actions/new)** を完了してください。設定しないとワークフローがエラーになります。

## 📁 ディレクトリ構造

```
X2Scb/
├── .github/workflows/     # 設定済み自動化ワークフロー
│   └── daily.yml         # 毎日9時実行
├── public/               # 生成データ (GitHub Pages)
├── src/
│   ├── backend/          # ツイート処理・整形
│   └── frontend/         # hideh1231 専用ユーザースクリプト
├── scripts/              # ユーティリティ
├── daily.js              # メイン収集処理
└── SETUP.md              # あなた専用のセットアップガイド
```

## 🛠️ データアクセス

生成されたデータは以下からアクセスできます：

- **JSON**: `https://hideh1231.github.io/X2Scb/public/YYYY-MM-DD.json`
- **TXT**: `https://hideh1231.github.io/X2Scb/public/YYYY-MM-DD.txt`
- **HTML**: `https://hideh1231.github.io/X2Scb/public/YYYY-MM-DD.html`

## 📚 リンク

- 🏠 **あなたのデータ**: [https://uithub.com/hideh1231/X2Scb/tree/main/public](https://uithub.com/hideh1231/X2Scb/tree/main/public)
- 📖 **セットアップガイド**: [SETUP.md](SETUP.md)
- 🔧 **ユーザースクリプト**: [scrapbox-twitter-daily.user.js](src/frontend/userscript/scrapbox-twitter-daily.user.js)
- 🔄 **Actions 履歴**: [Actions タブ](https://github.com/hideh1231/X2Scb/actions)

## 📄 ライセンス

MIT ライセンス - 自由に使用、変更してください！

## 🙏 元テンプレート

このリポジトリは [@tkgshn](https://github.com/tkgshn) の [X2Scb](https://github.com/tkgshn/X2Scb) テンプレートから作成されました。

---

> **🚀 今すぐ開始**: [SETUP.md](SETUP.md) の手順に従って、API設定を完了させましょう！
