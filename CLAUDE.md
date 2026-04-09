# CLAUDE.md

このリポジトリは **なんJ開発部 (`nanj-dev-bu`) skill** の開発・検証・配布元を兼ねる。
自分自身がこの運用のドッグフーディング場として動く。

## 運用ルールの正本

このプロジェクトの設計検討・スレッド運用・ADR / Spec ポリシーは、すべて以下に集約されている：

- `skills/nanj-dev-bu/SKILL.md` — 索引
- `skills/nanj-dev-bu/core/` — 思想・口調・禁止事項・正本ルール
- `skills/nanj-dev-bu/handles/` — 登場ハンドルカタログ
- `skills/nanj-dev-bu/threads/` — スレッドテンプレ・進行ルール・実例
- `skills/nanj-dev-bu/adr/` — ADR ポリシー・テンプレ
- `skills/nanj-dev-bu/specs/` — Spec ポリシー
- `skills/nanj-dev-bu/setup/` — 初期化手順

設計検討・スレッド作成・ADR / Spec 更新を行う際は、上記を読んでから作業すること。

## このリポジトリでの最低ルール

- 設計判断のスレッドは `history/threads/` に置く
- 採用された設計判断は `docs/adr/` に ADR として残す
- 仕様の正本は `specs/` に置く
- 上記の優先順位は `specs/` > `docs/adr/` > `history/threads/`
- 掲示板風ログを仕様の正本にしない

## 配布境界

- **配布対象**: `skills/nanj-dev-bu/` ディレクトリのみ。このディレクトリだけで skill として完結する
- **リポジトリ固有**: `history/threads/`、`docs/adr/`、`specs/`、`CLAUDE.md` はこのリポジトリのドッグフーディング用であり、skill の配布物には含まれない

## skill 自体の改修について

`skills/nanj-dev-bu/` 配下を改修するときは：

- `SKILL.md` は索引に徹し、本体ロジックは参照ファイルに置く
- ハンドル追加は `skills/nanj-dev-bu/handles/` に1ファイル足し、`handles/README.md` のカタログ表に追記する
- 禁止事項・口調ルール変更は必ず `core/` 側を更新する
- 改修自体もこの運用に従い、必要ならスレッドを立てて検討する（ドッグフーディング）
