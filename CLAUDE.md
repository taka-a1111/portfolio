# CLAUDE.md — インフォサクセス ポートフォリオ 制作ルール

このリポジトリは、フリーランス「インフォサクセス」のポートフォリオサイトです。
本番URL: https://infosuccess.vercel.app/ （旧URL portfolio-seven-pink-94.vercel.app からは308リダイレクト）
mainにpushするとVercelが自動デプロイします。

## 絶対に守るルール

1. **index.html のファイル名を変更しない**（Vercelのトップページ認識に必須。小文字厳守）
2. **実データを1文字も改変しない**。以下は原文ママ厳守：
   - SEO順位実績（閉店祝い 花=1位 など8キーワード）、内部施策の順位変動6件
   - HanaPrime事例の数値（120記事 / 18ヶ月 / 月3万PV→20万PV / 1位獲得率15%）
   - クラウドワークス実績（245点採用 / ¥110,000 / 各ランキング順位と年月 / 6,600回+）
   - 執筆実績5本のURL、プロフィール数値（2011年〜 / 2016年独立 / 15年 / SEO検定1級）
3. **制作実績は本番公開済みの6件のみ**。`.vercel.app` のデモURLを掲載に追加しない
   （mizukamikougei.com / athlix2026.com / russia-suisan.com / legends1999.net / salonde-kids.net / breakthrough-co.jp/cosmos/）
4. **クライアントの社名をテキストに書かない**。業種＋地域表記を維持する（例:「建具製作・内装施工会社｜三重県伊勢市」）
5. **BUILD_TAGを毎回更新する**。形式は `YYYY-MM-DD` + 英小文字（同日2回目は b, c...）。
   埋め込み場所は2箇所: `<head>` 直下のHTMLコメント と フッター最下部の表示。index.html と thanks.html の両方を揃える
6. **絵文字・矢印文字（→ ↗）を使わない**。矢印はインラインSVG（class="ar" / viewBox="0 0 24 24"）で統一
7. フォーム設定を壊さない: action=formsubmit.co/believe.myself999@gmail.com、
   _next=https://infosuccess.vercel.app/thanks.html、ハニーポット input[name="_honey"] を維持

## デザイン原則（v3 エディトリアル様式）

- **角丸・ドロップシャドウ禁止**。1pxヘアライン罫線（--line: #d9cdb9）で組む
- 配色トークン: --sumi:#191411 / --paper:#f8f4ec / --beni:#a92e51 / --kin:#9d7a2c / --dark:#181310
- 書体: 見出し=Shippori Mincho / 本文=Zen Kaku Gothic New / 英字=Cormorant Garamond(italic) / データ=JetBrains Mono
- シグネチャーは「点線リーダーの実績台帳」様式（.lg-row / .trow / .awr）。新要素もこの様式に合わせる
- セクションは「左レール（番号+英字ラベル）＋右本文」の2カラムグリッド（.sec-g）
- prefers-reduced-motion 対応を壊さない。overflow-x:hidden をbodyに維持

## 品質チェック（コミット前に必ず）

- HTMLタグの閉じ忘れ・ID重複・リンク切れアンカーがないこと
- モバイル幅（@media 980px / 600px）でレイアウト崩れがないこと
- 変更は指示された箇所のみ。「ついで改善」をしない。提案がある場合は実装せずPR説明文に書く

## 作業の流れ

1. 指示された変更を実装（上記ルール遵守）
2. BUILD_TAGを更新（index.html / thanks.html 両方）
3. コミットメッセージは日本語で変更内容を要約し、末尾にBUILD_TAGを記載
