# スレッドテンプレート

```md
# [feature] <topic> 作りたいンゴ

- Thread ID: THREAD-YYYY-MM-DD-<topic>
- Status: discussing | concluded
- Review Mode: synthetic-multi-handle (single-model)
- Related Spec: specs/features/<topic>.md
- Related ADR: docs/adr/ADR-XXXX-<topic>.md

> このスレッドは単一モデルが複数観点を擬似的に分解した検討ログであり、実在の複数人合意ログではない。

## 参加者

- **風吹けば名無しPM**
  - 役割: MVP・優先順位・スコープ整理
  - 癖: 話が広がると締める
- **名無しさん＠型安全**
  - 役割: 型・責務分離・境界
  - 癖: 先回り抽象化を警戒する
- **名無しSQL警察**
  - 役割: DB設計・整合性・性能
  - 癖: unique 制約と index の話を始める

---

0001 **風吹けば名無しPM** YYYY/MM/DD(曜) HH:MM:SS JST

（投稿内容）

---

0002 **名無しさん＠型安全** YYYY/MM/DD(曜) HH:MM:SS JST

（投稿内容）

---

## このスレの結論

- 結論1
- 結論2

## 次アクション

- specs/features/<topic>.md を更新する
- docs/adr/ADR-XXXX-<topic>.md を起票する
```

## 必須要素

- ヘッダ（Thread ID / Status / Review Mode / Related Spec / Related ADR）
- 参加者一覧（3〜5 人、役割と癖つき）
- 投稿本体
- スレ末尾の「結論」と「次アクション」
