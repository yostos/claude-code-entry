# セルフハンズオン 仕様書

## 環境準備

Claude Code と関連ツールの環境を整える。

### やること

1. Git for Windows をインストールする
2. Git Bash を起動する
3. Claude Code をインストールする（PowerShell を使用）
4. Claude Code を Git Bash で起動して動作を確認する
5. 作業ディレクトリを作成する
6. VS Code でフォルダを開く
7. Node.js をインストールする
8. textlint / markdownlint / pandoc をインストールする

※ Claude Code は Git Bash（Git for Windows に付属）上で動作する。インストールのみ PowerShell を使用する。

### 学ぶこと

- Claude Code の起動方法と基本的な対話の仕方
- Claude Code を使って必要なツールをインストールする方法

### Claude Code での作業

- Claude Code を起動して応答を確認する
- Claude Code で各ツールをインストールする

---

## 構想

学習者が Claude Code と対話しながら、文書の目的・読者・伝えたいことを整理する。

### やること

- 手持ちの素材（ネタ）を `input/` フォルダに集め、`input/index.md` で各資料の意味を記述する
- どんな文書を書くのかを明確にする（RFP とは何か、どういう文書か）
- 誰に向けて書くのかを明確にする（この RFP の読み手は誰か）
- 何のために書くのかを明確にする（この RFP で達成したいことは何か）

### 学ぶこと

- インプット資料を整理し、index を作成して Claude Code に連携する方法
- 自明に思えることでも Claude Code と一緒に言語化し、文書として残すことの価値
- 構想で決めたことが後続フェーズ（仕様・執筆）での判断基準＝制約になること

### Claude Code での作業

- `input/` フォルダの資料を Claude Code に読み込ませる
- `docs/concept.md` を作成する
- 文書の位置づけを `CLAUDE.md` に記録する

---

## 仕様

構想で決めた制約をもとに、RFP の文書要件と構成を決める。

### やること

0. システムの RFP に関する情報源を調べる
1. システムの RFP に必要な構成要素を調査する
2. 文書要件としてまとめる — 文書要件項目とその定義を記載する
3. 構成を決める — 文書要件項目の取捨選択と並び順を決める
4. 文書作成ツールとフォーマットを選択する — 今回は Markdown で執筆し、pandoc で HTML に変換する

### 学ぶこと

- 自分が知らないこと（システム RFP の標準的な構成）を Claude Code を使って調べ、整理する方法
- 構想で決めた制約が、取捨選択の判断基準として実際に機能すること

### Claude Code での作業

- `docs/requirements.md` を作成する
- 文書の位置づけを `CLAUDE.md` に記録する
- 文書作成ツール（pandoc）の情報を `CLAUDE.md` に記録する

---

## 執筆

仕様で決めた構成に従って、RFP の本文を書く。

### やること

1. 文書にする — セクションごとに下書きを生成し、確認・修正する
2. HTML に変換して中間確認する
3. 文書レビューを行う（バグ出し）
4. 文書を改修する（バグ取り）

### 学ぶこと

- Claude Code で執筆しながら、エディタで確認していく方法
- Magi（カスタムエージェント）を使った複数観点からのレビュー方法
- レビュー指摘事項を Claude Code で改修する方法

### Claude Code での作業

- Claude Code で `src/` に RFP を執筆する
- Magi でレビューする

---

## 校正

Claude Code を通じて校正ツールを実行し、文書の品質をチェック・修正する。

### やること

1. markdownlint を実行して Markdown の書式をチェックする
2. textlint を実行して日本語の文章品質をチェックする
3. 指摘事項を修正する
4. 再チェックして指摘がなくなるまで繰り返す

### 学ぶこと

- Claude Code を通じて校正ツール（textlint / markdownlint）を実行する方法
- ツールごとの役割の違い（textlint = 日本語品質、markdownlint = 書式）
- 指摘を受け入れるかどうかは自分で判断すること

### Claude Code での作業

- Claude Code で textlint を実行する
- Claude Code で markdownlint を実行する
- 指摘事項を Claude Code で修正する

---

## リリース

最終成果物を出力し、完成させる。

### やること

1. pandoc で HTML に最終変換する
2. 変換結果を確認する
3. 成果物として完成させる

### 学ぶこと

- Claude Code で最終成果物を出力する方法

### Claude Code での作業

- Claude Code で pandoc を実行し HTML を出力する

---

## 研修資料の要件

- フォーマット: Markdown（Marp でスライドにレンダリング）
- ファイル構成: 全体で 1 ファイル（`handson.md`、プロジェクトルートに配置）
- 図版: 使用しない
- 構成: フェーズごとにセクション区切りスライドを設ける（環境準備 / 構想 / 仕様 / 執筆 / 校正 / リリース）
- 言語: 日本語
- 対象読者: 非エンジニア（技術用語には説明を添える）
- 出力形式: HTML（`marp --html` で生成）

### Marp 仕様

#### Frontmatter

```yaml
---
marp: true
theme: gaia
paginate: true
size: 4:3
header: "非エンジニア向け Claude Code 入門"
footer: "© 2026 Toshiyuki Yoshida (@yostos)"
---
```

#### スライド分割ルール

- スライドの区切りは `---`（水平線）で行う
- 1 スライドに詰め込みすぎない（目安: 見出し + 箇条書き 5〜7 項目以内）
- コードブロックを含むスライドは、コードを短く保つ（5 行以内を目安）

#### セクション区切りスライド

各フェーズの先頭に、セクションタイトルのみのスライドを置く。Marp の `<!-- _class: lead -->` ディレクティブを使い、中央寄せの大きな見出しにする。

```markdown
---

<!-- _class: lead -->

# 構想する

Claude Code と対話しながらアイデアを整理する

---
```

#### タイトルスライド

先頭スライドは `<!-- _class: lead -->` を使い、ページ番号・ヘッダー・フッターを非表示にする。

```markdown
---
marp: true
theme: gaia
paginate: true
size: 4:3
header: "非エンジニア向け Claude Code 入門"
footer: "© 2026 Toshiyuki Yoshida (@yostos)"
---

<!-- _class: lead -->
<!-- _paginate: false -->
<!-- _header: "" -->
<!-- _footer: "" -->

# 非エンジニア向け Claude Code 入門

**Claude Code で学ぶ構想からリリースまで**

セルフハンズオン

---
```

#### スライド内の記法ルール

- 見出しレベル: スライドタイトルは `#` または `##` を使用する
- 箇条書き: `-` を使用する（`*` は使わない）
- 強調: 重要語句は `**太字**` で示す
- コードブロック: コマンドや入力例は ` ``` ` で囲む（言語指定あり）
- 補足説明: `> ` 引用ブロックで「ポイント」や「ヒント」を示す

#### ビルドコマンド

```bash
# HTML に変換（ブラウザで閲覧）
npx @marp-team/marp-cli handson.md -o handson.html

# プレビュー（ライブリロード付き）
npx @marp-team/marp-cli handson.md --preview
```
