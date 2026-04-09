# ADR-0001: リポジトリ初期ディレクトリ構造

## Status
Accepted

## Context
なんJ開発部 skill リポジトリは skill 本体（`skills/nanj-dev-bu/`）のみ存在し、CLAUDE.md で定義された運用ディレクトリ（設計スレッド、ADR、仕様書）が未作成だった。
ドッグフーディングを開始するにあたり、初期構造を確定する必要があった。

## Decision
リポジトリ直下に以下のディレクトリを設置する。

| ディレクトリ | 用途 |
|---|---|
| `history/threads/` | 設計検討の掲示板風スレッドログ |
| `docs/adr/` | 採用された設計判断の記録 |
| `specs/` | 仕様の正本 |

空ディレクトリは `.gitkeep` で git 追跡する。

`specs/` 配下にサブディレクトリ（`features/` 等）を事前に掘ることは見送り、ファイルが増えた段階で再検討する。

## Consequences
- CLAUDE.md の運用ルールに従った文書管理が即座に開始できる
- 優先順位の正本ルール（`specs/` > `docs/adr/` > `history/threads/`）が機能する
- サブディレクトリの分割は後日判断が必要になる可能性がある

## Related
- history/threads/2026-04-09-repo-init-structure.md
- specs/repo-structure.md
