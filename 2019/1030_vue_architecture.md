# Vue.jsアーキテクチャリング勉強会 in 株式会社クラウドワークス

## イベント概要

- 複数人でも耐えられるコンポーネント設計
- 階層が深くなったときのコンポーネント設計
などなど

## 登壇者
- CBcoud（遠藤 拓弥さん） - 「Vue × Vuex のアーキテクチャ完全に理解した」
- BASE（松原 佑介さん） - 「BASEにおける Vueコンポーネント設計の現在」
- プレイド（大平 和史さん） - 「Vue.js設計地図 〜設計概念の依存関係からフロントエンド設計を見つめ直す〜」
- スタディスト（笹木 信吾さん） - 「TeachmeBizを支えるフロントエンドのアーキテクチャと品質担保」

---

## Vue × Vuex のアーキテクチャ完全に理解した
CBcoud（遠藤 拓弥さん）  
[発表資料](https://speakerdeck.com/entaku/vue-vuex-falseakitekutiyawan-quan-nili-jie-sita)

「PickGo」 軽貨物の配送マッチングプラットフォーム

### 利用技術
- Vue
- Nuxt
- ElementUI

Nuxt使えばだいたい揃う。下記が追加したフォルダ
- utils
- lib_source
- components配下
- api

### Vue/Vuex アーキテクチャ
**pages**  
actionsの呼び出し  
gettersでの値の取得  
mapGetters、mapActionsを使う

#### 失敗したこと（なにか起こったわけではないけど）
**Stateを直接参照**  
stateで見るものと、gettersで見るものの混在  
情報の一意性が保てなくなる

**Actionを通さないMutationの処理**  
更新処理はActionsに寄せる

### デザイン
Atmic Designを採用  
Atmic Designはデザインからの発想なので、フロントエンドの開発での設計ではない

**Atoms**  
element-uiコンポーネントそのものか、それをラップしたものを入れる

**Molecules**  
一つ以上のAtoms

**Organisms**  
**Template**  

**Pages**  
Storeへのアクセス（State/Actions）が唯一可能なコンポーネント  


#### Atmic Designで失敗したこと
- ElementUIを使っているのにUIをカスタマイズ
- Templateを入れずにPagesが肥大化
- 階層が深すぎてemit地獄

そもそもElementUI使っているのに、こんなにガッチリしたAtmic Designにする必要はあるのかな？？

### TypeScript導入したい
静的型付け

---

## BASEにおける Vueコンポーネント設計の現在
BASE（松原 佑介さん）  
[発表資料](https://speakerdeck.com/simezi9/baseniokeru-vuekonponentoshe-ji-falsexian-zai)

- jQuery => Vue.js + TypeScript
- SPAではなくMPA
- 内製のUIコンポーネントライブラリの作成

### コンポーネント
**Container**  
Atmic DesignでのPagesに相当  
API通信（Actions?）, Storeへのアクセスができる唯一のコンポーネント  
Presentational ComponentやContainer Componentを束ねる役割  
多少のUIを持ってもいい

**Presentational**  
Atmic DesignでのTemplates/Organismsに相当  
与えられたものを表示するだけのコンポーネント  
再利用性は考えない

**Common Presentation**  
Atmic DesignでのTemplates/Organisms/Moleculesに相当  
頻出するもデザインのパターンを定義  
使い回すコンポーネント  
ヘッダー、パンくずなど

**Atom（UIライブラリ）**  
Atmic DesignでのMolecules/Atomsに相当  
サービス全体で流用できるもの  
局所的に上書きできるようにするためScoped CSS / CSS Modulesを使わない  
コンポーネント外と関わるスタイルは指定しない

### Storybook
- サンドボックス的な性質、エンジニア向けのガイド
- カタログ、どのようなコンポーネントがあるのか網羅的に

来るイベント、渡せるプロップス実装に必要な情報も必ず載せる

コンポーネントごとにREADMEを用意  
※ @storybook/addon-notes

Containerはstorybookに載せない、粒度の小さいコンポーネントほど重要

### 個別コンポーネントの実装
フロントエンドの性質として、ライフサイクルが短い

共通化よりも、コンポーネントの責務の分離が重要
- スタイル・マークアップ・スクリプトは外に影響しないように作れる
- 疎結合を優先、コードの重複を恐れない

### 実装のtips
**props**  
propsでObjectやArrayを方に指定することはなるべく避ける  
Stateと同じ形であればいいと思う。。複雑な配列・オブジェクトを指定しない。

**event**  
イベント名にカラフルな語彙を使わない  
{イベントの動詞}:{イベントの対象}

イベントのpayloadをオブジェクトにする => 分割代入で受け取る  
=> プロパティが増えたときに受け取りやすい  
ROROパターン（Receive an object, return as object)）

**style**  
classで処理の渋滞をさせない => aria・data属性でスタイルを指定する

下記の記事がこの登壇者が書いたもの  
[属性セレクタでVue.jsのstyleを整理する](https://qiita.com/simezi9/items/ff9c79c222c49940a553)

**scoped-slot**  
顕著な例だと、モーダルが作りやすい（Vuetifyのモーダルでもやってる）  
[Vue Thin Modal](https://github.com/ktsn/vue-thin-modal) がいい感じらしい

**scoped-slotあとで調べる。。。**

---

## Vue.js設計地図 〜設計概念の依存関係からフロントエンド設計を見つめ直す〜
プレイド（大平 和史さん）

[発表資料](https://speakerdeck.com/taihey/vue-dot-jsshe-ji-di-tu-she-ji-gai-nian-falseyi-cun-guan-xi-karahurontoendoshe-ji-wojian-tumezhi-su)

↓の記事の解説  
https://tech.plaid.co.jp/architecture_frontend_modeling/


**Nuxt 動的ルーティングと同じパターン。要検索**

---

## TeachmeBizを支えるフロントエンドのアーキテクチャと品質担保
スタディスト（笹木 信吾さん）

[発表資料](https://www.slideshare.net/shingosasaki3/teachmebiz-188542240?ref=https://cw-engineers.connpass.com/event/146975/presentation/)

### Vuexでの状態管理（画面駆動Vuex => ドメイン駆動Vuex）

画面駆動Vuexと命名した開発手法をとっていた
- 画面ごとの開発？状態管理
- emit地獄はない
- 開発の初速は早い

画面の総数は開発規模に比例して多くなる => 考えることが多くなりすぎて破綻

ドメイン駆動Vuexに手法を変更  
[「ドメイン駆動Vuex」についてはこちら](https://medium.com/studist-dev/ddd-vuex-c47055f6c1ba)

**フロントエンドの主役はUI/UX**  
コンポーネントとビジネスロジックの分離  
つまり、UIとStoreとAPIを完全に分離

UI => 取得してきたものを表示、状態を変更する指示出し => テスタビリティの向上  
Store => APIにリクエスト、State（状態の保持、画面の状態は持たない）、値の整形

Storeのモジュールはリソース単位で分割

- コンポーネントをまたいで使いまわしたいデータは、大半がAPIから取得したもの
- コンポーネント内で完結できるものはdataに保持
- 多少のバケツリレーは受け入れたほうがテスタビリティが上がる
- ただ、抜け道は用意している（フラッシュメッセージ・モーダル...）
  - 独自プラグインとして作成・使用
  - グローバルな情報になるので多くはしない、けどこれ使うやつはそんなに多くないはず

ここまでの詳細は↓の記事  
[Vueと共に走ったフロントエンドリプレイス１年間](https://speakerdeck.com/komiyamast/vuetogong-nizou-tutahurontoentorihureisu1nian-jian)

### コンポーネントの分割
Atmic Designを採用
- Pages Storeの参照可  => ページ
- Organisms Storeの参照可  => Moleculesをまとめたもの
- Molecules  => Atomsをまとめたもの
- Atoms  => 最小単位

### コンポーネントの品質管理
- propsの組み合わせ
- 多言語対応
- APIに依存するもの

**Storybookの力を借りる**  
多言語表示やルーティングはStoryBookで実現（実質テスト）  
- knobsでロケールの切り替えで多言語の表示（カタログ化）
- モックを使って、画面遷移・画面内切り替えもできるように
- ステークホルダーとの共有にも使える

### テストコードに書くこと
対象は下記が主
- Vue/Vuexから分離したピュアロジック
- Vueコンポーネント
- VuexのStore

- コンポーネントのテスト => 振る舞い・デザイン
- Storeのテスト => action/mutation/getter

**振る舞い**  
vue-test-utilsを使ってる  
対象はOrganismsだけ

**デザイン**
[Storycap](https://github.com/reg-viz/storycap)と[reg-suit](https://github.com/reg-viz/reg-suit)を使っての、ビジュアルスナップショットテスト


テスタビリティを重視してる
