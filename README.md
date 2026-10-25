# ボドゲOnline（オリジナルボードゲーム）

男気じゃんけん旅アプリ（v316）から移した自作ゲーム3つと、新作 WYRDSTONE のアプリです。

- 完成品：四季の巡り／LEMNISCATE
- 開発中：どんぐり戦争／WYRDSTONE
- WYRDSTONE を遊ぶには、Supabase の SQL Editor で `schema.sql` をもう一度 Run（wd_games テーブルが増えます。何回実行しても大丈夫）
- 置き場所は アプリの 設定 →「ゲームの置き場所」でいつでも入れ替えられます

## 公開までの手順

### 1. Supabase
1. 新しいプロジェクトを作る
2. 左メニュー **SQL Editor** → `schema.sql` の中身を全部貼り付けて **Run**
3. **Project Settings → API（Data API）** で次の2つをコピー
   - Project URL（`https://xxxx.supabase.co`）
   - Publishable key（`sb_publishable_…`）

### 2. 接続先を入れる（どちらか）
- **おすすめ**：`index.html` の上のほうにある
  `const CFG_URL = "";` と `const CFG_KEY = "";` の `""` の中に貼る
  （みんなのスマホで入力不要になる）
- もしくは、公開後にアプリを開くと出る入力画面に貼る（その端末だけに保存）

### 3. GitHub Pages
1. 新しいリポジトリを作る（Public）
2. このフォルダのファイルを全部アップロード
   `index.html` `sw.js` `manifest.json` `icon-192.png` `icon-512.png` `apple-touch-icon.png`
   （`schema.sql` と `README.md` は上げても上げなくてもOK）
3. Settings → Pages → Branch を `main` / `(root)` にして Save
4. 数分後に `https://ユーザー名.github.io/リポジトリ名/` で開ける

### 4. 最初に開いたら
1. 「プレイヤーを登録する」からメンバーを登録
2. 右上で「自分」を選ぶ
3. 遊ぶ

## メモ
- データ（過去の対戦）は移していません。ゲームの中身（ルール・画面・CPU）はそのままです
- プッシュ通知は今は無し（自分の番になると、アプリを開いていれば振動します）
- 画面を更新したら `sw.js` の `CACHE` の番号（gamelab-v41）を上げると、スマホに確実に反映されます
