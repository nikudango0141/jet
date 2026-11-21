# 2D ENGINE SANDBOX

ブラウザで動作するドット絵風のエンジン建築サンドボックスです。TypeScript、Phaser 3、Viteで構成しています。

## 起動

```sh
npm install
npm run dev
```

## GitHub Pages

GitHub Pagesのデプロイ元をGitHub Actionsに設定し、以下のワークフローが自動でビルド・公開します。

```yaml
name: Deploy to GitHub Pages
on:
  push:
    branches: [main]
  workflow_dispatch:
permissions:
  contents: read
  pages: write
  id-token: write
concurrency:
  group: pages
  cancel-in-progress: true
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 20
          cache: npm
      - run: npm install
      - run: npm run build
      - uses: actions/upload-pages-artifact@v3
        with:
          path: dist
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - id: deployment
        uses: actions/deploy-pages@v4
```

## 操作

- 左クリック/ドラッグ: 選択中のパーツを配置
- 右クリック: セル上のパーツを削除
- ホイール: ズーム
- 中クリック、またはSpaceを押しながらドラッグ: パン
- R: 選択パーツを回転
- Ctrl+Z / Ctrl+Y: 元に戻す / やり直す
- Ctrl+C / Ctrl+V: 選択パーツを複製
- Delete: 選択パーツを削除

マップはブラウザのLocalStorageに保存します。シミュレーションは部品列を使ったゲーム用の抽象モデルで、現実の機械設計や運転の用途には適しません。

