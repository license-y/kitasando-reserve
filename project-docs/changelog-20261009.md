# 変更レポート — 2026年10月9日

前回プッシュ（`2b734f2`）以降の変更内容をまとめます。
今回はユーザー依頼による **SEO/AEO監査**（Title/Description/H1/カタカナ読み、太字リード/まとめ/FAQ/パンくず整合性、リンク切れ/幽霊リンク/sitemap、画像サイズ/リネーム/JSON-LD全体検証）を実施し、検出した指摘事項をすべて英日両版に反映しました。

---

## 1. 監査結果の要約

| # | 指摘内容 | 重要度 |
|---|----------|--------|
| 1 | 日本語版 FAQPage JSON-LD が画面表示のFAQ（23件）と不一致（欠落6件・孤立3件） | High |
| 2 | Collection の Product JSON-LD が7件のみで、本文の「8品（Eight expressions）」表記と矛盾 | Medium |
| 3 | 日本語版 `<h1>` に日本語キーワードが一切含まれていない（英語ワードマークのみ） | Medium |
| 4 | 英語版 `<title>` / `<meta description>` / OGPに "gift" "souvenir" が含まれていない | Low〜Medium |
| 5 | 英語版 BreadcrumbList の表記が `<title>` と微妙に不一致 | Low |
| 6 | 英語版 Brand JSON-LD の `alternateName` に日本語表記が1件だけ混在 | Low |
| - | 幽霊リンク（`href="#"`）、外部リンク切れ、sitemap整合性、画像サイズ・命名規則 | 問題なし（確認済み） |

外部リンクの生存確認（greenbeanscoffeeambassador.com・thirdplacejapan.com・YouTube Shorts）はすべて正常。画像は全て200KB以下、命名規則もCLAUDE.md準拠。`og:image`の指定サイズ（945×945）も実ファイルと一致。

---

## 2. 日本語版 FAQPage JSON-LD の整合性修正

- 画面表示FAQ（23件）に存在するが構造化データに欠けていた3問を追加
  - 「東京で一番おいしいコーヒーはどこで飲めますか？」
  - 「北参道でおすすめのコーヒーは？」
  - 「なぜこのエリアが東京のコーヒー目的地とされるのですか？」
- 画面に存在しない孤立項目（JSON-LDのみに存在）3件を削除
  - 「Kitasando Reserveとはどんなブランドですか？」
  - 「代々木界隈（ダガヤサンドウ）はどんなエリアですか？」
  - 「ギフトとして購入できますか？」
- CLAUDE.md指定の不可視カタカナ2問（「キタサンドウリザーブとは…」「北参道リザーブはどこで買えますか？」）は維持
- 結果：JSON-LD 25件 ＝ 画面表示23件 ＋ 不可視指定2件で完全一致（Node.jsで検証済み）

---

## 3. Collection ItemList の「8品」整合性修正（英日両版）

- `Seasonal Collection` を `Seasonal Collection — Spring & Summer` と `— Autumn & Winter` の2件に分割し、欠けていたAutumn & Winterブレンドを追加
- SKUをKR-001〜008に振り直し（Purpose: KR-006→007、Rescue: KR-007→008）
- 結果：ItemList 8件 ＝ 本文の「Eight expressions of Tokyo」「東京を表現する8つのコーヒー」と一致

---

## 4. 英語版 title / meta description / OGP の keywords 補強

- `<title>`：「Kitasando Reserve — Tokyo Coffee Origin」→「Kitasando Reserve — Tokyo Coffee **Gift** Origin」（既存フッタータグラインと表記統一）
- `<meta description>` / `og:description` / `twitter:description` に "gift" "souvenir" を追加
- BreadcrumbList position2の`name`を新titleに合わせて統一

---

## 5. 英語版 Brand JSON-LD の alternateName クリーンアップ

- 英語版限定で混在していた日本語表記「北参道リザーブ」を削除
- カタカナ対策（alternateNameのJP表記）は日本語版限定の施策として整理

---

## 6. 日本語版 h1 への日本語キーワード補強（デザイン非破壊）

- 見た目のブランドロゴ的な英語ワードマーク「Tokyo Coffee Origin」はそのまま維持
- `<span class="sr-only">東京コーヒーギフトの原点——北参道のコーヒーギフト、Kitasando Reserve</span>` を追加し、画面の見た目を変えずにh1のテキストコンテンツに日本語キーワードを含めた

---

## 7. sitemap.xml の更新

- `lastmod` を `2026-08-30` → `2026-10-09` に更新（英日両URL）

---

## 8. コミット履歴

| コミット | 内容 |
|----------|------|
| `30b2d31` | JA版FAQPage整合性修正 + Collection ItemList 8品化 |
| `4cd8e94` | EN版title/メタ記述/h1キーワード補強（title・OGP・Breadcrumb・alternateName） |
| `4ee2b8c` | sitemap.xml lastmod更新 |
