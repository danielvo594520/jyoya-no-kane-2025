# 2-Agent ワークフロールール

## 役割分担

### PM（Cursor）
- 機能の企画・要件定義
- タスクの作成・優先度設定
- コードレビュー
- 本番デプロイの承認

### Impl（Claude Code）
- 実装・コーディング
- テスト・動作確認
- staging 環境へのデプロイ
- 技術的な提案

## ハンドオフルール

### Cursor → Claude Code
1. Plans.md にタスクを追加（`pm:依頼中`）
2. 完了条件を明記
3. `/handoff-to-claude` を実行

### Claude Code → Cursor
1. 実装完了後、タスクを `cc:完了` に更新
2. 変更内容のサマリーを作成
3. `/handoff-to-cursor` を実行

## マーカー運用

| マーカー | 状態 | 担当 |
|---------|------|------|
| `cc:TODO` | 未着手 | Claude Code |
| `cc:WIP` | 作業中 | Claude Code |
| `cc:完了` | 実装完了 | Claude Code |
| `cc:blocked` | ブロック中 | - |
| `pm:依頼中` | 依頼済み | Cursor |
| `pm:確認済` | レビュー完了 | Cursor |

---

*claude-code-harness v1.0*
