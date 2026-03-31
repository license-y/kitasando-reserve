# 変更レポート — 2026年3月31日

前回プッシュ（`e2e850c`）以降の変更内容をまとめます。

---

## 1. Hero セクション

- メインビジュアルのサブタイトルを刷新
  - 旧：`The premium coffee label crafted by Green Beans Coffee — a specialty roastery in Kitasando, Tokyo.`
  - 新：`Tokyo's specialty coffee gift — crafted by Green Beans Coffee in Kitasando.`
  - 「ギフト」訴求とブランド説明を1行に統合
- `[ Tokyo Coffee Gift ]` バッジを追加（ゴールドボーダーのラベル形式）

---

## 2. Story セクション

- 「Why This District」ブロックを新たに追加（4ブロック構成に拡充）
  - Dagayasando / 北参道エリアが東京コーヒーの聖地である理由を説明
  - 鳩森八幡神社・明治神宮・新宿御苑のパワースポットとしての役割を記述
  - 画像：オーナー提供の3枚を縦スタックで表示（`assets/images/district/1〜3.jpg`）
- Story 全体のレイアウトをL/R/L/R交互配置に整理
- 各ブロックの写真をオーナー提供のローカル写真に差し替え
  - `silence.jpg`：「Where Silence Meets Sensibility」
  - `tokyo.jpg`：「The City That Refines Everything」
- 最終段落の文章を修正
  - 旧：「Kitasando Reserve is not a place — it is a name given to a coffee...」（否定形から始まる表現）
  - 新：「Kitasando Reserve is a name chosen with intention...」（肯定形に変更）

---

## 3. Visit セクション

- 本文を修正（「場所」と誤読させる表現を解消）
  - 旧：「Kitasando Reserve is not merely a place to drink coffee...」
  - 新：「Kitasando Reserve beans are brewed at Green Beans Coffee...」
- 末尾に「and to bring a piece of Tokyo home.」を追加（ギフト文脈の補足）

---

## 4. Collection セクション

- 商品数を6品→8品に変更（4×2グリッド、4+4の対称レイアウト）
  - Seasonal を「Spring」と「Summer」の2品に分割
  - Social Blend を新たに追加
- 全商品の画像をUnsplashからオーナー提供のパッケージ写真に差し替え
  - `assets/images/collection/` フォルダーに格納（1〜8命名）
- サブコピー変更：「Six expressions...」→「Eight expressions of Tokyo, each crafted to be carried home. The specialty coffee gift from Kitasando.」
- コレクション下部のテキスト変更：「Available at Green Beans Coffee...」→「Tokyo Coffee Gift — roasted in Kitasando, carried home from Tokyo.」

---

## 5. Find Us セクション（旧 Access）

- 情報を全面的に更新・整理
  - 店舗名「Green Beans Coffee / Home of Kitasando Reserve」を明示
  - 出口番号を修正（2番出口 → 1番出口）
  - 道順を追加（Exit 1 → turn left → RC Apartment building on your left）
  - Instagramの記述を削除
  - 支払い方法を詳細化（Visa / Mastercard / Amex / JCB / Suica / PayPay / WeChat Pay / Alipay）
  - Googleマップボタンを地図の下に配置
  - テキストエリアとマップの比率を 3:2 に変更
  - 最下部に全幅の注記を追加（Kitasando Coffeeとの混同防止）

---

## 6. FAQ セクション

- 4問を新たに追加（計10問→14問）
  - Q11：「How is Kitasando Reserve different from Kitasando Coffee?」（Kitasando Coffeeとの違い）
  - Q12：「What makes Kitasando Reserve different?」（差別化要因）
  - Q13：「What is the relationship between Kitasando Reserve and Green Beans Coffee?」（関係性）
  - Q14：「Why is this area considered a Tokyo coffee destination?」（聖地の理由）
- 各回答に「In short:」の1行要約を追加（AEO / AI検索最適化対応）
- 既存回答の「Kitasando Reserve = 場所・カフェ」的な表現を修正（全問）
- `café` 表記をサイト全体で統一（アクセント付きに統一）

---

## 7. ファイル・フォルダー整理

| 変更内容 | 詳細 |
|----------|------|
| フォルダー追加 | `public/assets/images/collection/`（パッケージ写真8枚） |
| フォルダー追加 | `public/assets/images/district/`（旧 `Place/` からリネーム・小文字化） |
| 追加画像 | `district/1.jpg` `2.jpg` `3.jpg`（Why This District セクション用） |
| 追加画像 | `district/silence.jpg`（Why Kitasando セクション用） |
| 追加画像 | `district/tokyo.jpg`（Why Tokyo セクション用） |
| 追加資料 | `project-docs/Kitasando Reserve20260331_聖地である理由.txt` |
