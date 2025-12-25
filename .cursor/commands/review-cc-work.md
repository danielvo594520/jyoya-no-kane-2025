# /review-cc-work - Claude Code の作業をレビュー

Claude Code（Impl）が完了したタスクをレビューします。

## レビュー手順

### 1. 変更内容の確認
```bash
git diff
git status
```

### 2. 動作確認
```bash
python -m http.server 8000
# または
npx serve .
```

ブラウザで http://localhost:8000 を開いて確認。

### 3. コードレビュー
- [ ] 要件を満たしているか
- [ ] コーディング規約に従っているか
- [ ] パフォーマンス上の問題はないか
- [ ] セキュリティ上の問題はないか

### 4. レビュー結果

**承認の場合:**
- Plans.md のタスクを `cc:完了` → `pm:確認済` に更新
- 必要に応じてコミット

**修正依頼の場合:**
- 具体的な修正点を記載
- `/handoff-to-claude` で再依頼

---

まず `git diff` と `git status` で変更内容を確認してください。
