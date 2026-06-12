# Google Play 配信ガイド

## 全体の流れ

```
あなた: ① デベロッパー登録（$25・本人確認あり・数日かかることも）← 今すぐ開始
Claude: ② Androidパッケージ(.aab)生成のサポート
あなた: ③ Play Console にアップロード
Claude: ④ assetlinks.json をサイトに配置
あなた: ⑤ ストア情報を貼り付けて審査提出（掲載文は下に用意済み）
```

---

## ① デベロッパー登録（あなたの作業・今すぐ開始推奨）

1. https://play.google.com/console に Google アカウントでログイン
2. 「アカウントを作成」→ 個人 を選択
3. 登録料 **$25（約¥3,800・1回きり）** をカードで支払い
4. **本人確認**（運転免許証などの身分証アップロード）
   - ⚠️ 承認まで数時間〜数日かかります。先に始めてください。

> 📌 個人情報はGoogleにのみ提出されます。ストアの「デベロッパー名」は
> ニックネーム可（例: Fuu Team）。住所等の公開設定に注意。

---

## ② Androidパッケージの生成（登録完了後にClaude と一緒に）

**PWABuilder**（Microsoft製・無料）を使うのが最も簡単：

1. https://www.pwabuilder.com を開く
2. URL欄に `https://fukuokamotoshi-coder.github.io/breathsync/` を入力 → Start
3. 「Package For Stores」→ Android → **Generate Package**
4. ダウンロードされるzipに入っているもの：
   - `signed.aab` ← Play Console にアップロードするファイル
   - `assetlinks.json` ← Claudeに渡してください（サイトに配置します）
   - `signing-key-info` ← **絶対に失くさないこと**（更新時に必要）

---

## ③〜⑤ アップロードと審査

1. Play Console → 「アプリを作成」
   - アプリ名: Fuu
   - 言語: 日本語 / 無料 / アプリ
2. 「製品版」→ .aab をアップロード
3. ストア掲載情報に下の文章をコピペ
4. スクリーンショット: スマホでアプリを開いて2枚以上撮影
   （電源＋音量下ボタン同時押し）
5. 審査提出 → 通常1〜7日で公開

---

## ストア掲載文（コピペ用）

### アプリ名（30字以内）
```
Fuu - 世界と一緒に深呼吸
```

### 簡単な説明（80字以内）
```
今この瞬間、世界中の誰かと一緒に深呼吸。登録不要・完全無料のマインドフルネス呼吸アプリ。
```

### 詳細な説明（4000字以内）
```
🌍 今、世界の誰かと一緒に呼吸しよう

Fuu は「ひとりじゃない深呼吸」を体験できる、まったく新しいウェルネスアプリです。アプリを開くと、今この瞬間に世界中で何人が一緒に呼吸しているかがリアルタイムで表示されます。

✨ 特徴

◆ リアルタイム同時呼吸
「いま23人が一緒に呼吸中」— 数字はすべて本物。孤独な夜も、誰かとつながっている安心感を。

◆ 科学的な呼吸法
・4-7-8呼吸（リラックス・入眠に）
・ボックス呼吸（集中力アップに）
・リラックス呼吸（initial・いつでも）

◆ 8種類のサウンド + マイ音楽
雨音・波・森・バイノーラルビートなどを端末内で生成。お気に入りの音楽ファイルをBGMにすることも。

◆ 写真と呼吸
大切な人の写真、思い出の風景を見ながら深呼吸。写真は端末から出ません。

◆ フレンド機能
6文字のコードを交換するだけ。友達がオンラインになったら一緒に呼吸できます。

◆ 続けたくなる仕組み
毎日のログインボーナス「しずく」、連続日数ストリーク、実績バッジ、週間チャレンジ。マスコットの「フウ」があなたを応援します。

🔒 プライバシー第一
・アカウント登録不要
・呼吸の記録・写真・音楽はすべて端末内のみに保存
・広告なし・トラッキングなし
・完全無料（すべての機能が使えます）

毎日3分、世界と一緒に深呼吸。心を整える新しい習慣を始めましょう。
```

### English (for global listing)
```
Short: Breathe with someone, somewhere, right now. Free mindful breathing app. No signup.

Full: Fuu shows you how many people around the world are breathing
with you in real time. Science-backed patterns (4-7-8, box breathing),
8 generative soundscapes plus your own music, photo breathing, friend codes,
daily bonuses and a cheering mascot called Fuu. No account, no ads,
everything free, all personal data stays on your device.
```

### その他の設定
| 項目 | 値 |
|------|-----|
| カテゴリ | 健康＆フィットネス |
| 対象年齢 | 3歳以上（全年齢） |
| プライバシーポリシー | https://fukuokamotoshi-coder.github.io/breathsync/privacy.html |
| 広告の有無 | なし |
| アプリ内購入 | なし（Stripe導入後は「あり」に変更） |
| データ収集の申告 | 「収集しない」（在席情報は匿名・セッション中のみ） |

### 用意済みの素材
| 素材 | ファイル |
|------|---------|
| アイコン 512×512 | `icon-512.png` |
| フィーチャーグラフィック 1024×500 | `feature-graphic.png` |
| スクリーンショット | スマホで撮影（2枚以上） |
