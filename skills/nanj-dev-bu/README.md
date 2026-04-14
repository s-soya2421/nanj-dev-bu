# なんJ開発部 (nanj-dev-bu)

掲示板文化にインスパイアされた、設計検討を掲示板風スレッドで進める Claude Code skill。

固定ハンドルによる擬似的な多人数レビューで、検討の過程を軽やかに残しつつ、結論を ADR / Spec に昇格させて仕様の正本を堅く保つ。

## インストール

### 推奨導線

配布時の標準導線は **Skills CLI** を推奨。
`claude skill add` はローカル開発・動作確認向けとして扱う。

### Skills CLI（推奨）

[vercel-labs/skills](https://github.com/vercel-labs/skills) を使うと、複数エージェント環境へ導入しやすい。

```bash
# プロジェクトローカル
npx skills add s-soya2421/nanj-dev-bu

# グローバル（全プロジェクトで有効）
npx skills add -g s-soya2421/nanj-dev-bu
```

### Claude Code ローカル開発

```bash
claude skill add /path/to/skills/nanj-dev-bu
```

### Plugin Marketplace

Claude Code の Plugin Marketplace 経由で使う場合:

```bash
claude plugin marketplace add s-soya2421/nanj-dev-bu
claude plugin install nanj-dev-bu@nanj-dev-bu-plugins
```

> Plugin 経由でインストールした場合、スキル呼び出しは `/nanj-dev-bu:<skill>` の形式になる。

### 手動インストール

```bash
# 個人用（全プロジェクトで有効）
git clone <this-repo> /tmp/nanj-dev-bu
cp -r /tmp/nanj-dev-bu/skills/nanj-dev-bu ~/.claude/skills/

# リポジトリ同梱（チーム配布）
cp -r skills/nanj-dev-bu <target-repo>/.claude/skills/
```

## 発動条件

Claude Code が以下のような依頼を受けたとき、自動で読み込まれる：

- 「いいね機能どう作る？スレ立てて検討して」
- 「認証方式の比較スレ作って」
- 「この設計判断 ADR にしたい」

## 構成

```text
nanj-dev-bu/
  SKILL.md          # 索引（Claude が最初に読む）
  core/             # 思想・口調・禁止事項・正本ルール
  handles/          # 登場ハンドルのカタログ
  threads/          # スレッドテンプレ・進行ルール・実例
  adr/              # ADR テンプレ・昇格ポリシー
  specs/            # Spec ポリシー
  setup/            # 初期化手順
```

## 注意事項

本プロジェクトは掲示板文化にインスパイアされた個人プロジェクトであり、特定の掲示板・コミュニティとは無関係です。
何かご意見ありましたら、Issue にて遠慮なくコメントください。

## ライセンス

MIT
