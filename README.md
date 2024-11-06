# Next.js Project Structure

## Directory Structure

```plaintext
├── app/                  # アプリケーションのルーティング
├── components/           # 共通コンポーネント
│   ├── elements/         # 汎用的なUI要素
│   │   ├── Button/
│   │   ├── Input/
│   │   └── ...
│   └── layouts/          # レイアウトコンポーネント
│       ├── Header/
│       ├── Footer/
│       └── ...
├── configs/             # 設定ファイル
│   ├── site.ts          # サイト全体の設定
│   └── meta.ts
└── features/             # 機能単位のコンポーネント
    ├── blog/
    │   ├── components/   # ブログ機能特有のコンポーネント
    │   └── ...
    └── ...
```

## Directory Details

### `app/`

- Next.jsのApp Routerを使用したルーティングを管理
- ページコンポーネントとルートレイアウトを配置

### `components/`

共通で使用されるコンポーネントを管理するディレクトリ

#### `components/elements/`

- 全ページで使用される基本的なUI要素を配置
- 例：ボタン、入力フォーム、カード、アラートなど
- 高い再利用性と一貫性のあるデザインを維持

#### `components/layouts/`

- ページの基本構造を形成するコンポーネントを配置
- 例：ヘッダー、フッター、サイドバーなど
- アプリケーション全体で一貫したレイアウトを提供

### `features/`

特定の機能やページに関連するコンポーネントを管理

#### `features/[feature-name]/components/`

- 特定の機能専用のコンポーネントを配置
- 例：`features/blog/components/`にはブログ機能特有のコンポーネントを配置
- 機能単位でのコンポーネントの独立性を維持

## Conventions

### コンポーネントの命名規則

- パスカルケース（PascalCase）を使用
- 例：`Button.tsx`, `HeaderNavigation.tsx`

### ディレクトリ構造のガイドライン

1. 新しいコンポーネントを作成する際は、その用途に応じて適切なディレクトリに配置
2. 複数のページで使用するコンポーネントは`components/elements/`に配置
3. 特定の機能でのみ使用するコンポーネントは`features/`配下に配置

### コードの整理

- 各コンポーネントは独立したディレクトリに配置し、関連するファイル（スタイル、テスト、型定義など）をまとめる
- 例：

  ```plaintext
  Button/
  ├── Button.tsx
  ├── Button.test.tsx
  ├── Button.styles.ts
  └── index.ts
  ```

## Development Guidelines

### 新機能の追加

1. 機能に必要なコンポーネントを適切なディレクトリに配置
2. 共通で使用する可能性のあるコンポーネントは`components/`に配置
3. 機能特有のコンポーネントは`features/`配下に配置

### コンポーネントの設計原則

- 単一責任の原則に従う
- Props経由でのカスタマイズを可能にする
- 適切なTypeScriptの型定義を行う

## Getting Started

1. プロジェクトのクローン:

```bash
git clone [repository-url]
```

1. 依存関係のインストール:

```bash
npm install
# or
yarn install
```

1. 開発サーバーの起動:

```bash
npm run dev
```

1. ブラウザで開く:

```plaintext
http://localhost:3000
```
