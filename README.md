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
- **Canopy 版と同じ中身**（社内 Wiki リンク・Internal Transfer Portal・社内サポート・Step 1／4／5）が入っています。社内リンクには
  「社内」ラベルが付いていて、Amazon ネットワークの外では開けません。**スマホでは Amazon Enterprise Access（AEA）アプリで開く**
  （リンクを長押し → リンクをコピー → AEA のアドレス欄に貼る）。PC なら社内ネットワーク／VPN 上のブラウザでそのまま開けます
- 社内情報を含むので、この `index.html` は**暗号化した状態でだけ**置くこと。平文のプレビュー（`_work/gh_preview_full.html`）は絶対にアップロードしない
- Canopy 版だけにある機能: 「更新」ボタン（求人・資格価格・社内 Wiki の最新化）、学習ログのサーバー保存（PC とスマホで共有）。
  GitHub 版の Step 1 右上の「Canopy 版（自動更新）」からいつでも飛べます
- フォント: Ember Modern Display Standard（英数）／メイリオ（和文）。ロゴは Simple Icons（CC0）、求人リンクは各社の公式採用サイト

## 4. 作り直し・確認
- `scripts/15_build_github_pack.py --password-file _work/gh_password.txt` が `github_pack/index.html`（暗号化）と `AWS_GitHUB.zip`（アップロード用 3 点）を作る。
  `--mode public` を付けると旧・社内情報を除いた版になる
- 作成時の監査結果（社内リンク件数・残存絵文字・セクション一覧）は `_work/gh_audit.json`
