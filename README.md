# nanj-dev-bu

設計検討を掲示板風スレッドで議論し、結論を ADR / Spec に昇格させる Claude Code skill。

固定ハンドルによる擬似的な多人数レビューで、検討過程を残しながら正本を堅く保つ。

## インストール

配布時の推奨導線（Skills CLI）:

```bash
npx skills add s-soya2421/nanj-dev-bu
```

ローカル開発で直接読み込む場合:

```bash
claude skill add /path/to/skills/nanj-dev-bu
```

## 何ができるか

| 機能 | 説明 |
|---|---|
| 設計検討スレッド | 掲示板風の多人数議論で論点を洗い出す |
| ADR 昇格 | スレッドの結論を Architecture Decision Record として定着させる |
| Spec 管理 | 仕様の正本を明確に保つ |

## 使い方

### 1. 初期セットアップ

skill を追加した後、プロジェクトに必要なディレクトリを作成する:

```
history/threads/   # 設計検討スレッドログ
docs/adr/          # ADR（採用された設計判断）
specs/             # 仕様の正本
```

詳しくは `skills/nanj-dev-bu/setup/init-dirs.md` を参照。

### 2. 設計検討スレッドを立てる

Claude に設計テーマを伝えると、掲示板風のスレッドが生成される。

```
「認証ミドルウェアの刷新について検討スレ立ててくれ」
```

- 3〜5 人の固定ハンドルが議論に参加
- スレッド末尾に「結論」と「次アクション」がまとまる
- 完成したスレッドは `history/threads/` に保存

### 3. ADR に昇格させる

スレッドの結論が採用されたら、ADR として定着させる。

```
「さっきのスレの結論を ADR にしてくれ」
```

- `docs/adr/ADR-XXXX-<topic>.md` として保存される

### 4. Spec を更新する

ADR を受けて仕様の正本を作成・更新する。

```
「ADR-0001 の内容で Spec 書いてくれ」
```

- `specs/<topic>.md` として保存される

### 正本の優先順位

情報が競合した場合: **specs/** > **docs/adr/** > **history/threads/**

## サンプル

`example/` に一連の流れのサンプルを収録している:

| ファイル | 内容 |
|---|---|
| [`example/history/threads/2026-04-09-repo-init-structure.md`](example/history/threads/2026-04-09-repo-init-structure.md) | 設計検討スレッドの実例 |
| [`example/docs/adr/ADR-0001-repo-init-structure.md`](example/docs/adr/ADR-0001-repo-init-structure.md) | スレッドから昇格した ADR の実例 |
| [`example/specs/repo-structure.md`](example/specs/repo-structure.md) | ADR を受けて書かれた Spec の実例 |

**スレッド → ADR → Spec** の流れを一通り確認できる。

## リポジトリ構成

```
/
├── skills/nanj-dev-bu/   # skill 本体（配布対象）
├── example/               # 使用例（スレッド → ADR → Spec の一連の流れ）
├── history/threads/       # 設計検討スレッドログ（リポジトリ固有）
├── docs/adr/              # ADR（リポジトリ固有）
├── specs/                 # 仕様の正本（リポジトリ固有）
└── CLAUDE.md              # プロジェクト指示
```

`skills/nanj-dev-bu/` が skill として配布される単位。それ以外はこのリポジトリ自体のドッグフーディング用。

## ライセンス

MIT
