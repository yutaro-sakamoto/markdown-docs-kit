# Markdown 文書執筆テンプレート

Markdown 形式で文書を執筆し、mdBook を使って HTML ファイルを生成するための包括的なテンプレートです。

## 特徴

- 📝 **mdBook 統合** - Markdown で執筆し、美しい HTML ドキュメントを生成
- 🎨 **Prettier フォーマット** - 一貫したスタイルのための自動コード整形
- ✅ **品質チェック** - Markdown の文法チェックとスペルチェック
- 🐳 **Dev Container 対応** - VS Code と GitHub Codespaces で使えるすぐに使える開発環境
- 🚀 **GitHub Actions** - ビルドと検証の自動化されたCI/CDパイプライン
- 🌐 **ライブプレビュー** - localhost:3000でのリアルタイムプレビュー
- ☁️ **GitHub Codespaces 対応** - インスタントクラウドベース開発環境

## クイックスタート

このプロジェクトは **Dev Container** で動作するように設計されており、必要なツールがすべてプリインストールされた一貫した開発環境を提供します。

### Dev Container を使用（推奨）

#### VS Code（ローカル）で使用

1. VS Code でこのプロジェクトを開く
2. "Dev Containers" 拡張機能をインストール
3. `Ctrl+Shift+P` を押して "Dev Containers: Reopen in Container" を選択
4. コンテナのビルドと起動を待つ
5. すべてのツール（Rust、mdBook、Node.js）が自動的に利用可能になります

#### GitHub Codespaces（クラウド）で使用

1. GitHub上でこのリポジトリにアクセス
2. 緑色の "Code" ボタンをクリック
3. "Codespaces" タブを選択
4. "Create codespace on main" をクリック
5. クラウド上で開発環境が自動的にセットアップされます

### 手動セットアップ（非推奨）

Dev Container を使用したくない場合は、手動で依存関係をインストールできます：

1. Rust と Cargo をインストール:

   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
   ```

2. mdBook をインストール:

   ```bash
   cargo install mdbook
   ```

3. Node.js の依存関係をインストール:
   ```bash
   npm install
   ```

## 使用方法

### ドキュメントの執筆

1. `src/` ディレクトリ内のファイルを編集:

   - `SUMMARY.md` - 目次
   - `chapter_1.md` - コンテンツの章
   - 必要に応じて `.md` ファイルを追加

2. `book.toml` でブックのメタデータを更新:
   ```toml
   [book]
   title = "あなたのブックタイトル"
   authors = ["あなたの名前"]
   language = "ja"
   ```

### ビルドと配信

#### 開発環境（ライブリロード付き）

```bash
npm run serve
# または
mdbook serve
```

http://localhost:3000 でドキュメントにアクセス

#### 本番用ビルド

```bash
npm run build
# または
mdbook build
```

生成されたファイルは `book/` ディレクトリに保存されます。

### コード品質

#### Prettier でコードを整形

```bash
npm run format
```

#### 整形チェック

```bash
npm run format:check
```

#### Markdown ファイルの文法チェック

```bash
npm run lint:markdown
```

## プロジェクト構造

```
├── src/                    # Markdown ソースファイル
│   ├── SUMMARY.md         # 目次
│   └── chapter_1.md       # コンテンツの章
├── book/                  # 生成された HTML 出力
├── .devcontainer/         # Dev Container 設定
├── .github/workflows/     # GitHub Actions CI/CD
├── book.toml             # mdBook 設定
├── package.json          # Node.js 依存関係とスクリプト
├── .prettierrc           # Prettier 設定
└── .prettierignore       # Prettier 除外パターン
```

## GitHub Actions

プロジェクトには以下を行う自動化された CI/CD が含まれています:

- ✅ Prettier フォーマットのチェック
- ✅ Markdown 構文の検証
- ✅ ドキュメントのビルド
- 📦 デプロイ用アーティファクトの作成

## カスタマイズ

### スタイリング

`book.toml` を編集してドキュメントの外観と動作をカスタマイズできます。

### プラグインの追加

mdBook は様々なプラグインをサポートしています。Cargo でインストールし、`book.toml` で設定してください。

### より多くの文法チェックルールの追加

`package.json` の文法チェック設定を拡張し、必要に応じてより多くの textlint ルールを追加してください。

## コントリビューション

1. リポジトリをフォーク
2. 変更を加える
3. すべてのチェックが通ることを確認: `npm run format:check && npm run lint:markdown`
4. プルリクエストを提出

## ライセンス

MIT ライセンス - 詳細は LICENSE ファイルを参照してください。
