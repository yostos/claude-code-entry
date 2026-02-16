# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project: claude-code-entry

非エンジニア向け Claude Code セルフハンズオンの資料リポジトリ。テーマは「AIと共に文書を構想からリリースまで仕上げる」。

ハンズオン資料自体を、教える工程（構想 → 仕様 → 執筆 → 校正 → リリース）に従って作成する自己言及的なアプローチを取る。

## Structure

```
docs/
  concept.md        # コンセプト（構想フェーズの成果物）
  requirements.md   # 仕様書（仕様フェーズの成果物）
  steps/            # 各ステップの資料（執筆フェーズで作成）
```

## Writing Conventions

- すべての文書は日本語 Markdown で記述する
- 校正には textlint と markdownlint を使用する
- 対象読者は非エンジニアであるため、技術用語には説明を添える
