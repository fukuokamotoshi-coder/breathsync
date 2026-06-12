# BreathSync セットアップガイド

## ファイル構成

```
breathsync/
  index.html      メインアプリ（SPA）
  manifest.json   PWA設定
  sw.js           オフライン対応 Service Worker
  icon-192.png    アプリアイコン（要作成）
  icon-512.png    アプリアイコン（要作成）
  SETUP.md        このファイル
```

---

## ステップ 1 — Supabase（リアルタイム人数）

1. https://supabase.com でアカウント作成（無料）
2. 「New project」を作成
3. 左メニュー「Project Settings → API」を開く
4. 以下の値をコピーして `index.html` の先頭に貼る：

```html
window.SUPABASE_URL  = 'https://xxxx.supabase.co';      // Project URL
window.SUPABASE_KEY  = 'eyJ...';                         // anon public key
```

> Supabase Realtime の Presence 機能を使うため、追加のテーブル作成は不要です。

---

## ステップ 2 — Stripe（Pro プラン課金）

1. https://stripe.com/jp でアカウント作成
2. ダッシュボード → 「商品カタログ」→「商品を追加」
   - 商品名: BreathSync Pro
   - 月額プラン: ¥480/月（繰り返し請求）
   - 年額プラン: ¥3,800/年（繰り返し請求）
3. 各プランの「決済リンク」を作成してURLをコピー
4. `index.html` 先頭に貼る：

```html
window.STRIPE_LINK_MONTHLY = 'https://buy.stripe.com/xxxxx';
window.STRIPE_LINK_YEARLY  = 'https://buy.stripe.com/yyyyy';
```

### Webhook（課金成功後に Pro 解放）
本格運用では Supabase Edge Function + Stripe Webhook で
課金ユーザーのフラグを管理することを推奨します。
簡易版では Stripe Customer Portal のみで十分です。

---

## ステップ 3 — アイコン作成

Canva（無料）などで 512×512px の PNG を作成し
`icon-192.png`（192×192px）と `icon-512.png`（512×512px）として保存。

---

## ステップ 4 — GitHub Pages でデプロイ

```bash
cd breathsync

git init
git add .
git commit -m "feat: initial BreathSync release"
git branch -M main
git remote add origin https://github.com/<ユーザー名>/breathsync.git
git push -u origin main
```

GitHubリポジトリ → Settings → Pages → Source を
`main` ブランチ / `/ (root)` に設定 → Save

数分後に公開: `https://<ユーザー名>.github.io/breathsync/`

### カスタムドメインを使う場合
1. お名前.com などで取得（例: breathsync.app）
2. Pages の「Custom domain」に入力
3. DNS に CNAME レコードを追加: `<ユーザー名>.github.io`

---

## 収益化ロードマップ

| フェーズ | 施策 | 目安月収 |
|---------|------|---------|
| 0〜3ヶ月 | 無料公開・SNS拡散・ProductHunt投稿 | ¥0 |
| 3〜6ヶ月 | Stripe Pro プラン導入（¥480/月） | ¥5〜50万 |
| 6〜12ヶ月 | 法人向けチームプラン（¥5,000/月〜） | ¥50〜200万 |
| 1年〜 | 白ラベル提供・APIライセンス | 応相談 |

---

## ProductHunt 投稿チェックリスト

- [ ] アプリの英語版を用意（`/en` ルート）
- [ ] スクリーンショット 3〜5枚（1270×952px）
- [ ] 60秒デモ動画
- [ ] ハンターに依頼（フォロワー多い人）
- [ ] 投稿日：火〜木曜の 午前0時（PST）

---

## お問い合わせ

設定でつまずいたら Claude Code に相談してください。
