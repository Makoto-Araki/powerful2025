# powerful2025 Shopifyテーマのカスタマイズ記録

## 目的
- Shopifyテーマのカスタマイズ記録を取り、顧客からのカスタマイズ案件に備える。エンジニア向けの説明のため注意。

## 開発履歴
| 日付       | バージョン | 説明                                                               |
| ---------- | --------- | ------------------------------------------------------------------ |
| 2026/04/18 | 0.8.0     | 商品一覧のタグやバッジをIF文から配列で管理する                         |
| 2026/04/12 | 0.7.0     | 商品タグを下記の複数作成して、対応したバッジを最大で２個まで表示         |
| 2026/04/11 | 0.6.0     | 商品にnewタグが付与されていたらNew(英語)や新商品(日本語)のバッジ表示    |
| 2026/04/08 | 0.5.0     | 管理画面で商品一覧の接頭辞を自由入力可能にする                         |
| 2026/04/05 | 0.4.0     | 管理画面で商品一覧の接頭辞に★の付与の可否を設定                       |
| 2026/04/05 | 0.3.0     | 商品一覧の接頭辞に★を付与                                           |
| 2026/04/04 | 0.2.0     | バッジの角丸を四角に変更                                             |
| 2026/04/04 | 0.1.0     | README作成                                                         |

## 開発環境
- Windows11
- WSL(Ubuntu)
- Shopify Cli
- VSCode
- Git

## 開発手順
### 開発手順1 (ローカルリポジトリ)
- Github上でIssue作成しておくこと
- Shopify上でテーマ複製を行い、編集用(edit)と保存用(backup)を作成しておくこと
- WSL上で作業を行う

```bash
## 開発用ブランチ作成
$ git checkout -b feature/*******

## 開発用ブランチ確認
$ git branch

## ログイン
$ shopify auth login

## テーマの一覧 ※テーマIDを確認
$ shopify theme list --store powerful2025.myshopify.com

## 過去のプレビュー用テーマの削除
$ shopify theme delete --theme テーマID --store powerful2025.myshopify.com

## 編集用テーマのプル
$ shopify theme pull --theme テーマID --store powerful2025.myshopify.com

## テーマのカスタマイズ作業
$ code .

## 作業終了後に編集用テーマをプレビュー
$ shopify theme dev --theme テーマID --store powerful2025.myshopify.com

## 修正済のテーマをShopifyにプッシュして顧客に修正済のテーマを確認してもらう
$ shopify theme push --theme テーマID --store powerful2025.myshopify.com

## ログアウト
$ shopify auth logout

## ステージング移行
$ git add .

## コミット ※11はissue番号
$ git commit -m "feature/*******(#11)"

## プッシュ
$ git push origin feature/*******
```

### 開発手順2 (リモートリポジトリ)
- PR作成
- Mainブランチにマージ
- 開発用ブランチ削除

### 開発手順3 (ローカルリポジトリ)
```bash
## ブランチ切替
$ git checkout main

## ブランチ確認
$ git branch

## リモートリポジトリからプル
$ git pull origin main

## 開発用ブランチ削除
$ git branch -d feature/*******
```
