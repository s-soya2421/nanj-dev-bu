# Release Checklist

配布前に最低限このチェックを通す。

## 1. 安全性

- [ ] スレッド例・テンプレートに API キー、個人情報、内部 URL などの実データが含まれていない
- [ ] 実運用ログを載せる場合、識別子・メールアドレス・ID をマスキングしている
- [ ] `core/forbidden.md` の禁止事項が README と矛盾していない

## 2. 誤解防止

- [ ] スレッドテンプレートに `Review Mode: synthetic-multi-handle (single-model)` がある
- [ ] 「擬似多人数レビューであり実在の合議ログではない」注記がある
- [ ] 文体プロファイル (`casual-light` / `business`) の使い分けが記載されている

## 3. 運用移植性

- [ ] タイムスタンプ規則が `<TZ>` 形式になっている
- [ ] 必要に応じて UTC 併記ルールがある
- [ ] 固定パス前提ではなく、既存リポジトリ向けパスマッピング手順がある

## 4. 配布導線

- [ ] 推奨インストール導線を1つ明示している（Skills CLI 推奨など）
- [ ] 代替導線（`claude skill add` / plugin）は補助導線として説明している
- [ ] ルート README と skill README のインストール手順が矛盾していない

## 5. ライセンス・メタデータ

- [ ] ルート `LICENSE` と README のライセンス表記が一致している
- [ ] `SKILL.md` の `metadata.version` と配布物のバージョン表記が一致している
- [ ] plugin 配布する場合は `.claude-plugin/plugin.json` の `name/version/description` を更新している

## 6. 最終確認

- [ ] サンプルスレッドの末尾に「結論」「次アクション」がある
- [ ] `specs/ > docs/adr/ > history/threads/` の優先順位が一貫している
- [ ] 変更内容を `CHANGELOG` またはリリースノートに要約した
