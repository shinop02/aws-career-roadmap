# AWS Career Road Map（自分専用・暗号化版）

このフォルダの `index.html` は **AES-256-GCM で暗号化された 1 枚の HTML** です。開くとパスワード入力画面が出て、
正しいパスワードを入れるとブラウザの中だけで復号して表示します（どこにも送信しません）。
GitHub にそのまま置いても中身は読めません。パスワードは **専用のもの**（会社のパスワードとは別）を使ってください。

## 1. アップロード手順（GitHub を初めて使う人向け）

1. [github.com](https://github.com/) で **Sign up** → メールで無料アカウントを作る（2 分）
2. 右上の **＋** → **New repository**
3. Repository name に `aws-career-roadmap`、**Private を選ぶ**（ここが大事。Public にしない）→ **Create repository**
4. 作られたページの中ほど「uploading an existing file」を押す
5. このフォルダの **`index.html` と `.nojekyll` の 2 つ**をドラッグ＆ドロップ → 下の **Commit changes**
6. 画面上部 **Settings** → 左の **Pages** → Source を **Deploy from a branch**、Branch を **main / (root)** にして **Save**
7. 1〜2 分待つと同じページに `https://<あなたのID>.github.io/aws-career-roadmap/` と出る。開いてパスワードを入れる

スマホのホーム画面に追加しておくとアプリのように開けます（Safari: 共有 → ホーム画面に追加／Chrome: ⋮ → ホーム画面に追加）。

### 注意: Private リポジトリの GitHub Pages
- 無料アカウントでは Private リポジトリの Pages は**公開 URL** になります（URL を知っていれば誰でも開ける）。中身は暗号化してあるので
  パスワードが無ければ読めませんが、URL は人に教えないでください
- GitHub Pro（有料）にすると Private Pages を「リポジトリの閲覧者だけ」に制限できます。必要になったらそこで切り替え
- Pages を使わず、ファイルを **PC にダウンロードしてダブルクリック**でも同じように開けます（スマホならファイルアプリから）

## 2. 更新のしかた
- 元の HTML を直したら `scripts/15_build_github_pack.py` をもう一度実行 → 新しい `index.html` をリポジトリで **Add file → Upload files** で上書き
- 学習ログは端末（ブラウザ）に保存されます。別端末へ移すときは「JSON 書き出し」→ もう一方で「JSON 取り込み」

## 3. 中身について
- 社内情報（Wiki リンク・社内制度・昇進プロセス・ポジション詳細）は**この版には入っていません**（公開サービスに置くため機械的に除去）。
  それらは Canopy 版（社内ネットワーク専用）にだけあります
- フォント: Ember Modern Display Standard（英数）／メイリオ（和文）。ロゴは Simple Icons（CC0）、求人リンクは各社の公式採用サイト

## 4. 中身が気になるときの確認
`scripts/15_build_github_pack.py` は作成時に「社内ホストへのリンク 0 件・禁止語 0 件」を機械チェックして、結果を `github_pack/audit.json` に書きます。
