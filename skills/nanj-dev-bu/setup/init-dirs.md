# 初期化手順

この skill を初めて使うリポジトリでは、以下のディレクトリ構成を作成する。
以下は**デフォルト**であり、既存構成がある場合はマッピングして運用してよい。

## 必要なディレクトリ

```text
specs/
  features/
docs/
  adr/
history/
  threads/
```

## 作成コマンド

```bash
mkdir -p specs/features docs/adr history/threads
```

## 初回確認

skill が発動したとき、まず以下を確認する：

1. 上記3ディレクトリが存在するか
2. 存在しない場合、ユーザーに「このリポジトリに `specs/` `docs/adr/` `history/threads/` を作ってよいか」を確認する
3. 既存ディレクトリがある場合、命名や構成が衝突していないか確認する

## 既存リポジトリとの統合

既に `docs/` や `specs/` が別用途で使われている場合：

- 勝手に上書きしない
- ユーザーに既存構成を尊重するか、本 skill の構成に寄せるかを確認する
- 既存の ADR がある場合、ナンバリング規則を引き継ぐ

### 推奨: パスマッピングの明文化

リポジトリ側で以下を1回決め、以後はその設定を優先する。

```yaml
thread_dir: history/threads
adr_dir: docs/adr
spec_dir: specs/features
```

もし既存構成に合わせるなら、例:

```yaml
thread_dir: docs/decisions/threads
adr_dir: architecture/adr
spec_dir: product/specs
```

## .gitignore

掲示板スレッドは Git 管理に含めることを推奨する。
検討過程ごとリポジトリに残すのが本 skill の目的のため、`history/` を `.gitignore` に入れない。
ただし機密情報を含むログはコミット前に必ずマスキングする。
