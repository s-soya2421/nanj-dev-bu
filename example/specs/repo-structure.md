# リポジトリディレクトリ構造

## 概要
なんJ開発部 skill リポジトリのディレクトリ構造を定義する。
skill 本体と運用文書を分離し、設計判断の追跡可能性を確保する。

## 受け入れ条件
- [x] `history/threads/` が存在し、設計スレッドを格納できる
- [x] `docs/adr/` が存在し、ADR を格納できる
- [x] `specs/` が存在し、仕様書を格納できる
- [x] 空ディレクトリは `.gitkeep` で git 追跡されている
- [x] `.gitignore` が整備されている

## 挙動

### ディレクトリ構成

```
/
├── skills/nanj-dev-bu/   # skill 本体（SKILL.md, core/, handles/, threads/, adr/, specs/, setup/）
├── example/               # 使用例（スレッド → ADR → Spec の一連の流れ）
├── history/threads/       # 設計検討の掲示板風スレッドログ
├── docs/adr/              # 採用された設計判断（ADR）
├── specs/                 # 仕様の正本
├── CLAUDE.md              # プロジェクト指示
└── .gitignore
```

### 優先順位

情報が競合した場合の正本優先順位：

1. `specs/` — 最優先
2. `docs/adr/` — 設計判断の根拠
3. `history/threads/` — 検討過程の記録

### ファイル命名規則

| ディレクトリ | 命名形式 |
|---|---|
| `history/threads/` | `YYYY-MM-DD-<topic>.md` |
| `docs/adr/` | `ADR-XXXX-<topic>.md`（XXXX は連番） |
| `specs/` | `<topic>.md` |

## 制約
- `specs/` 配下にサブディレクトリは現時点では作らない（ファイル増加時に再検討）
- 掲示板風ログを仕様の正本にしない

## 関連
- docs/adr/ADR-0001-repo-init-structure.md
- history/threads/2026-04-09-repo-init-structure.md
