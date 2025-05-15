# 画像モザイク加工ツール

[![GitHub Repository](https://img.shields.io/badge/GitHub-Repository-blue?logo=github)](https://github.com/noricha-vr/mosaic)

**公開URL:** [https://mosaic.kojin.works/](https://mosaic.kojin.works/)

![alt text](images/mosaic.png)

## 概要

ブラウザ上で動作するシンプルな画像モザイク加工ツールです。ローカルの画像ファイルを読み込み、マウスやタッチ操作で直感的に指定した範囲にモザイクを適用することができます。

## 機能

- **画像読み込み:**
    - ファイル選択ダイアログ
    - ドラッグ＆ドロップ
- **モザイク加工:**
    - マウスドラッグまたはタッチ操作による描画
    - ブラシサイズ（適用範囲）の調整
    - モザイク粒度の調整
- **操作履歴:**
    - Undo（元に戻す）
    - Redo（やり直す）
    - 最大20ステップまで履歴を保持
- **画像出力:**
    - 加工後の画像をPNG形式でダウンロード
- **その他:**
    - レスポンシブデザイン対応
    - モダンなUI（Tailwind CSS使用）

## 使い方

1.  **画像を開く:**
    - 「画像を選択」ボタンをクリックし、加工したい画像ファイルを選択します。
    - または、画面中央の点線エリアに画像ファイルを直接ドラッグ＆ドロップします。
2.  **設定調整:**
    - 上部の「ブラシサイズ」スライダーを動かして、モザイクをかける範囲の太さを調整します。
    - 「モザイク粒度」スライダーで、モザイクの粗さを調整します。
3.  **モザイク加工:**
    - 画像の上でマウスをドラッグするか、指でなぞると、その軌跡に沿ってモザイクが適用されます。
4.  **操作の取り消し/やり直し:**
    - <i class="fa-solid fa-rotate-left"></i> (元に戻す) ボタンで直前の操作を取り消せます。
    - <i class="fa-solid fa-rotate-right"></i> (やり直す) ボタンで取り消した操作を再度実行できます。
5.  **ダウンロード:**
    - <i class="fa-solid fa-download"></i> (ダウンロード) ボタンをクリックすると、現在表示されている加工後の画像が `mosaic_image.png` というファイル名でダウンロードされます。

## 技術スタック

-   HTML5
-   CSS3
    -   [Tailwind CSS](https://tailwindcss.com/)
-   JavaScript (ES6+, Vanilla JS)
-   [Font Awesome](https://fontawesome.com/) (アイコン)

## 実行方法

`index.html` ファイルをお使いのウェブブラウザで開くだけで利用できます。サーバーサイドの処理や特別なビルド手順は不要です。

## デプロイ方法 (Cloudflare Pages)

このプロジェクトは Cloudflare Pages にデプロイできます。

1.  **Wrangler CLI のインストール (未導入の場合):**
    ```bash
    npm install -g wrangler
    # または yarn global add wrangler
    ```
2.  **Cloudflare アカウントへのログイン:**
    ```bash
    wrangler login
    ```
    ブラウザが開き、認証を求められます。
3.  **デプロイ:**
    プロジェクトのルートディレクトリで以下のコマンドを実行します。
    ```bash
    wrangler pages deploy . --project-name mosaic
    ```
    -   `.` はデプロイするディレクトリ（現在のディレクトリ）を指定します。
    -   `--project-name mosaic` で Cloudflare Pages 上のプロジェクト名を指定します。初回デプロイ時にこの名前でプロジェクトが作成されます（存在しない場合）。

    **注意:** GitHub リポジトリと連携している場合、指定したブランチ (例: `main`) への `git push` で自動的にデプロイが実行されます。手動での `wrangler pages deploy` は通常不要になります。
