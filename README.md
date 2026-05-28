# イクラ — Vercelデプロイ手順

## 1. GitHubにプッシュ

```bash
git init
git add .
git commit -m "initial commit"
git remote add origin https://github.com/YOUR_NAME/ikura.git
git push -u origin main
```

## 2. Vercelにインポート

1. vercel.com にログイン
2. 「Add New Project」→ GitHubリポジトリを選択
3. 「Deploy」

## 3. 環境変数を設定（重要）

Vercelダッシュボード → プロジェクト → Settings → Environment Variables

| Key | Value |
|---|---|
| STRIPE_SECRET_KEY | sk_test_xxxxx（Stripeの秘密鍵） |
| STRIPE_PRICE_ID | price_1TbzvUD1O6XcEaklmhyF4EoO |
| NEXT_PUBLIC_BASE_URL | https://your-app.vercel.app |

## 4. 再デプロイ

環境変数設定後、Vercelダッシュボードから「Redeploy」

## Stripeの秘密鍵の場所

Stripeダッシュボード → 開発者 → APIキー → 秘密鍵（sk_test_...）
※ 公開可能キー（pk_test_...）ではなく秘密鍵を使う

## テスト用カード番号

| カード番号 | 結果 |
|---|---|
| 4242 4242 4242 4242 | 成功 |
| 4000 0000 0000 0002 | 失敗 |

有効期限：任意の未来の日付
CVC：任意の3桁
