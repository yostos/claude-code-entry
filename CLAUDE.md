# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project: claude-code-entry

**jrnl Project Tag:** claude-code-entry

非エンジニア向け Claude Code セルフハンズオンの資料リポジトリ。テーマは「AIと共に文書を構想からリリースまで仕上げる」。

ハンズオン資料自体を、教える工程（構想 → 仕様 → 執筆 → 校正 → リリース）に従って作成する自己言及的なアプローチを取る。

## Structure

```
handson.md            # Marp スライド（成果物）
docs/
  concept.md          # コンセプト（構想フェーズの成果物）
  requirements.md     # 仕様書（仕様フェーズの成果物）
```

## Writing Conventions

- すべての文書は日本語 Markdown で記述する
- 校正には textlint と markdownlint を使用する
- 対象読者は非エンジニアであるため、技術用語には説明を添える

## Slide Writing Rules

- 各スライドで一番伝えたいメッセージを最初に書く
- 説明的な文章で太字を使わない
- 箇条書きは 5〜7 項目以内に収める
