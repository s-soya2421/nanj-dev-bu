---
name: nanj-dev-bu
description: 掲示板文化にインスパイアされた設計検討skill。掲示板風スレッドで議論し、結論を ADR / Spec に昇格させる。固定ハンドルによる擬似的な多人数レビューで、検討過程を残しながら正本を堅く保つ。
license: MIT
compatibility: Claude Code またはテキストベースのエージェント環境。外部ツール・ネットワーク不要。
metadata:
  author: nanj-dev-bu
  version: "0.1.0"
  lang: ja
---

# なんJ開発部

設計判断を掲示板風スレッドで進める運用 skill。
軽い口調で検討過程を残しつつ、正本（specs / ADR）は堅く保つことを目的とする。

## ディレクトリ構成

```
nanj-dev-bu/
├── SKILL.md              # メタデータ + 索引（このファイル）
├── core/                 # references: 思想・口調・禁止事項
├── handles/              # references: 登場ハンドルカタログ
├── threads/              # references: スレッドテンプレ・進行ルール・実例
├── adr/                  # references: ADR ポリシー・テンプレ
├── specs/                # references: Spec ポリシー
└── setup/                # references: 初期化手順
```

## 基本原則

- おもしろさより、まず正確さ
- キャラより、まず可読性
- ログより、まず正本の明確化
- ただし過程の保存価値があるなら、掲示板風に気持ちよく残す

## いつ何を読むか

### 必ず最初に読む
- `core/philosophy.md` — 運用思想
- `core/source-of-truth.md` — specs / adr / threads の優先順位
- `core/style.md` — 口調・語尾・薄味ルール
- `core/forbidden.md` — 禁止表現

### スレッドを書くとき
- `threads/template.md` — スレッドテンプレ
- `threads/naming.md` — ファイル名・タイトル規則
- `threads/flow.md` — コメント進行・収束ルール
- `threads/metadata.md` — 投稿番号・JST 日時規則
- `handles/README.md` を読み、必要なハンドルだけ `handles/<name>.md` を読む

### ADR に昇格するとき
- `adr/policy.md`
- `adr/template.md`

### Spec を更新するとき
- `specs/policy.md`

### 初回セットアップ
- `setup/init-dirs.md`

## 参考実例
- `threads/example-like-feature.md` — 完成スレッド1本フル
- `RELEASE_CHECKLIST.md` — 配布前チェックリスト

## スレッドを書く前のチェック

1. このトピックはスレ化する価値があるか（軽微 typo・自明リファクタはスレ不要）
2. ハンドルを 3〜5 人選んだか
3. `casual-light` / `business` の文体プロファイルを明示したか（未指定時は `business`）
4. スレ末尾に「結論」と「次アクション」を書く準備があるか
