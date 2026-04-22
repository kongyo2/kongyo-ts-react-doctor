# kongyo-ts-react-doctor

TypeScript React プロジェクトを [`react-doctor`](https://www.npmjs.com/package/react-doctor) で診断するための Claude Code プラグインです。診断結果を鵜呑みにせず、コード文脈に照らして必要な修正だけを行うことを目的とした skill `kongyo-ts-react-doctor` を収録しています。

React の変更後、レビュー前、バグ修正後、品質確認時に呼び出してください。

## 収録スキル

| Skill | 用途 |
|---|---|
| `kongyo-ts-react-doctor` | リポジトリルートで `npx -y react-doctor@latest . --verbose` をそのまま実行し、正常完了／不完全実行を切り分けた上で、確度と重要度の高い指摘だけをコード文脈と突き合わせて修正する |

skill の詳細は [`kongyo-ts-react-doctor/SKILL.md`](./kongyo-ts-react-doctor/SKILL.md) を参照してください。

## インストール

### Claude Code のマーケットプレイスから導入

Claude Code は [プラグインマーケットプレイス経由でプラグインを配布](https://code.claude.com/docs/en/discover-plugins.md) できます。本リポジトリは `.claude-plugin/marketplace.json` を含むため、そのままマーケットプレイスとして追加できます。

Claude Code を起動して次のコマンドを実行してください。

```shell
/plugin marketplace add kongyo2/kongyo-ts-react-doctor
/plugin install kongyo-ts-react-doctor@kongyo-ts-react-doctor
```

対話的に選びたい場合は、マーケットプレイス追加後に `/plugin` を開き、**Discover** タブから `kongyo-ts-react-doctor` を選択してインストールできます。インストール後に skill を反映するには `/reload-plugins` を実行してください。

### vercel-labs/skills の `npx skills` CLI から導入

[vercel-labs/skills](https://github.com/vercel-labs/skills) が提供する `npx skills` CLI を使うと、Claude Code に限らず OpenCode / Codex / Cursor など多数のエージェントに同じ skill を配ることができます。

```shell
# GitHub shorthand（推奨）
npx skills add kongyo2/kongyo-ts-react-doctor

# 完全な GitHub URL を指定する場合
npx skills add https://github.com/kongyo2/kongyo-ts-react-doctor
```

## 使い方

インストール後、skill は description の trigger に該当する作業をすると自動的に読み込まれます。明示的に呼び出したいときは会話で名前を挙げるだけで十分です。

```
kongyo-ts-react-doctor を使って、この React プロジェクトを診断して。
```

典型的な出番:

- React コンポーネントや hook を変更した直後の品質チェック
- PR レビュー前に dead code / lint / score をまとめて確認したいとき
- バグ修正後に回帰が残っていないか機械的に拾いたいとき
- `No issues detected` と出たときに、本当に完全実行だったのかを切り分けたいとき

## ライセンス

[MIT](./LICENSE)
