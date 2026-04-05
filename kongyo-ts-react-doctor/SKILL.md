---
name: kongyo-ts-react-doctor
description: React/TypeScript プロジェクトで react-doctor を実行し、セキュリティ、パフォーマンス、正しさ、設計上の問題候補を点検する。React の変更後、レビュー前、バグ修正後、品質確認時に使う。診断結果は参考情報として扱い、修正は必ずコード文脈に照らして吟味する。
---

## React Doctor

`react-doctor` で React コードベースを診断する。

### 実行

```bash
npx -y react-doctor@latest . --verbose
```

### 方針

- リポジトリルートで実行する。
- 指摘は自動適用せず、重要度とコード文脈を確認してから対応する。
- 修正後は再実行し、指摘内容とスコアの変化を確認する。

