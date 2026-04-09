# ADR テンプレート

```md
# ADR-XXXX: <タイトル>

## Status
Proposed | Accepted | Superseded by ADR-YYYY | Deprecated

## Context
判断が必要になった背景。
現在の状況、制約、関係する要件を簡潔に書く。

## Decision
何を決めたか。
代替案を検討した場合は、なぜそれを選ばなかったかも短く触れる。

## Consequences
この決定によって生じる影響。
- 良い影響
- 悪い影響・トレードオフ
- 将来発生しうる制約

## Related
- history/threads/<thread-file>.md
- specs/features/<spec-file>.md
- ADR-YYYY（関連する他の ADR があれば）
```

## 記入例

```md
# ADR-0002: いいね機能のデータモデル

## Status
Accepted

## Context
投稿に対してユーザーがいいねできる MVP を実装する。
将来的に通知機能を追加する可能性がある。

## Decision
`likes(user_id, post_id, created_at)` の中間テーブルを採用する。
MVP では1ユーザー1投稿につき1件までとする。

## Consequences
- 単純な集計が可能
- 通知機能は別実装が必要
- 将来的なリアクション拡張時は再検討が必要

## Related
- history/threads/2026-04-09-like-feature.md
- specs/features/like-feature.md
```
