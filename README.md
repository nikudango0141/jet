# 2D ENGINE SANDBOX

ブラウザで動作するドット絵風のエンジン建築サンドボックスです。TypeScript、Phaser 3、Viteで構成しています。

## ゲームを開く

[2D ENGINE SANDBOX をプレイ](https://nikudango0141.github.io/jet/)

## 起動

```sh
npm install
npm run dev
```

## GitHub Pages

`.github/workflows/pages.yml` がビルドしてGitHub Pagesへ公開します。リポジトリ設定の Pages で公開元を「GitHub Actions」にしてください。

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
