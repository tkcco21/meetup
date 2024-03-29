モダンフロントエンド勉強会 〜進化し続けるUXとDX〜

> 今回は、【UXとDXの向上】をテーマに、ラクスル ・freee・サイボウズから、ディスカッション形式で以下のようなお話しをさせていただきます！


# モダンフロントエンド勉強会（2019/07/23）
https://techplay.jp/event/740712

## freee株式会社
### 規模
- JS 1000ファイル以上
- SCSS 365ファイル以上

- 枯れてる技術を使う、長いものには巻かれろスタイル
- フォームであればformic
- スクロールであればreact-virtual
- 新しい技術はエンジニアの目が輝く
- コミュニティのプラクティスが習熟しているものを選ぶ

### パフォーマンス
- そこまで気にしてない
- 仮想DOMのレンダリングを気にするくらい、正しく使う
- SQLのチューニング

### 品質担保
- スナップショットテストは導入が楽（storyshot storybookで使える）
- メンテナンスコストが高いテストはあえて入れない
- lint/flow、タイプカバレッジ
- 法律の影響で中身が変わるし、専門知識が必要で、それを持ってる人たちと協働

### ワークフローで工夫してること
- ライブコーディング的な感じ
- Webアプリケーションエンジニアとしてフロントエンドバックエンド両方触る
- 専門がなくなる
- なので、ライブコーディングをしてる
- インプットの方法

### フロントエンドが働きやすい環境
- フロントエンドがUI/UXについての意見を言いやすい環境

### フロントエンドエンジニアに期待してること
- 業務アプリに必要な入出力が正確にできるか
- 静的解析をちゃんとする

webpackで死んでる依存モジュールの導入

---

## ラクスル
- デメリットはビジネスサイドの人たちとのやり取り（タグマネとか）
- 何を諦めて何を残すかで議論になる

### パフォーマンス
- キャッシュ・jsのminify
- pcメイン
- この点においてはあんまり意識高くない
- APIをノンブロッキング、フロントエンドのポーリングが多いのでそこの見せ方
- プリフェッチ

### 品質担保
- 型管理
- e2eのテスト
- 最近はテストカフェ、書きすぎると際限がなくなる
- circleCIは入れてる
- eslint, prettierは入れてる
- IEでの対応・確認も確実にやる
- QAチームなし、PMがQAをやってる（議論にはなるけど、採用が難しい）

### ワークフローで工夫してること
- モブプログラミング
- 1スクラムに2人のフロントエンドを入れて、インプットアウトプットがちゃんとできるように

### フロントエンドが働きやすい環境
- サーバーとフロントが戦うとサーバー側が大体勝つ（笑）
- フロントエンドが多数派になるように
- サーバーサイドに意見できるように
- デザイナーとのディスカッションが多いので、そこのコミュニケーションを取る

### フロントエンドエンジニアに期待してること
- リアル産業、立体的なUXが多いのでそれの対応
- UI/UXにこだわりを持つこと
- プログラム自体のライフサイクルが長い（4年、5年は当たり前）それに適した書き方・マインド

---

## サイボウズ

- 新しい技術を入れる際にはメリットデメリットがわかればいい
- フロントエンドではReactが枯れている

### パフォーマンス
- パフォーマンスはそんなにクリティカルじゃない
- サーバーサイドの負荷がネック
- 去年くらいから、パフォーマンスの定義や対応策、勉強会、現サービスのスピードの測定
- USにも展開していて、ネット環境は日本より悪いので、ファイルの圧縮は頑張ってる
- インフラのAWSに変えようとしているので、トリップタイムが気になる

### 品質担保
- circleCI, jenkins
- QAとのやり取り、テストの設計もする、けっこう協働してる
- テストピラミット、スモールなテストを増やしてる

### ワークフローで工夫してること
- 一番のユーザーは自社で、その環境にまずデプロイ
- 自動デプロイ
- ちょい前にスクラムが流行ってた
- 今はモブプログラミング（個人の成長があまり。。適材適所的になる）
- wework

### フロントエンドが働きやすい環境
- プロダクト自体がUI/UXに重きをおいてる

### フロントエンドエンジニアに期待してること
- 気合ではやらず、ちゃんと技術で対応できるか
- eslintのプラグインを作ったりもする
- 使ってないCSSの削除なんかもちゃんと技術でやる
- OSSでの貢献、自然にアウトプットができる

renovate


