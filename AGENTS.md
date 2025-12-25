# AGENTS.md - 除夜の鐘シューティング 2025

## 🎯 プロジェクト概要

宇宙空間を舞台に、お坊さんがハンマーを投げて除夜の鐘を打つシューティングゲーム。
純粋な HTML/CSS/JavaScript で実装し、GitHub Pages で公開する。

## 👥 2-Agent ワークフロー

### PM（Cursor）の役割
- 機能の企画・要件定義
- コードレビュー
- 本番デプロイの承認
- `/handoff-to-claude` でタスクを依頼

### Impl（Claude Code）の役割
- 実装・コーディング
- テスト・動作確認
- `/handoff-to-cursor` で完了報告

## 📋 マーカー凡例

| マーカー | 状態 | 説明 |
|---------|------|------|
| `cc:TODO` | 未着手 | Claude Code が実行予定 |
| `cc:WIP` | 作業中 | Claude Code が実装中 |
| `cc:完了` | 完了 | 実装完了 |
| `cc:blocked` | ブロック中 | 依存タスク待ち |
| `pm:依頼中` | PM から依頼 | Cursor から依頼されたタスク |
| `pm:確認済` | PM 確認済み | Cursor がレビュー完了 |

## 🛠 技術スタック

- **フロントエンド**: HTML5 / CSS3 / JavaScript (ES6+)
- **描画**: Canvas API
- **デプロイ**: GitHub Pages
- **フレームワーク**: なし（Vanilla JS）

## 📁 ファイル構成

```
/
├── index.html        # ゲーム本体（HTML + CSS + JS 一体）
├── README.md         # プロジェクト説明
├── AGENTS.md         # このファイル
├── CLAUDE.md         # Claude Code 設定
├── Plans.md          # タスク管理
└── .claude/          # Claude Code 設定ディレクトリ
```

## 🔄 開発フロー

1. **Cursor** で機能を相談・計画
2. `/handoff-to-claude` で Claude Code にタスク依頼
3. **Claude Code** が実装
4. `/handoff-to-cursor` で完了報告
5. **Cursor** がレビュー・承認
6. 本番デプロイ
