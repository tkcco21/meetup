
## JSで機械学習はじめよう（http://bit.ly/2FDqHss）
- https://emojiscavengerhunt.withgoogle.com/ja/
- https://landing.google.co.jp/tegaki/
- https://tushuhei.github.io/tfjs-tutorial/


## The Road to Worker
- https://addaleax.net/workers-nodefest/#1
おそらく、マルチスレッドの話

## JavaScript Class Features: A case study TC39(https://github.com/tc39)
jsの仕様を決めてる人の話
- プライベートとして#使える
- class name extends HTMLElemnt {}の書き方
- weakmap(=> map), weakset(<=> set), static

## Navi: painless routing for React(https://github.com/frontarm)
- reactで作ってもmetaが必要。シェアやクローラーのため
- ReactDOMServer.renderToString(HTMLを文字列にするやつ)
- navi(https://github.com/frontarm/navi)
- react-navi(https://github.com/frontarm/navi)
- navi-scripts(https://github.com/frontarm/navi)

## Reactにおけるパフォーマンスチューニング(http://maxmellon.github.io/)
Ricruit technologiesのエンジニア（AirSHFT作ってる）
- 処理の75％くらいがscripting(9000ms, rendiringは1000ms) => 3000msに改善（全体で3.6s）
- 真因の特定
- scriptingの内訳
- 関数のコールスタックの調査
- React内部でされてることの調査
- window.parformance.mark()で計測したい処理を挟む
- React16からuser timing Apiが実装、開発環境ではdevツールを見ればおｋ
- redux-action-timing-middleware => actionとcomponentの関係性がわかる
- 改善のアプローチ、処理時間の削減と処理を減らす
- 処理時間の削減 => 無駄なレンダリングを発生させない
- 処理を減らす => 関数の削除、再計算しない
- reconcilation 仮想DOMレベルの比較（component単位）shouldComponentsUpdateがtrueのときのみ実行
- 木構造の削減 画面の見えない部分は不必要（react-virtualizedいいよ。画面に近づいてからマウント）
- componentの粒度を小さく
- 継続的にやるために、習慣的に計測・記録する


## 実践GraphQL for クライアント側
query languege
- 実践GraphQL for クライアント側（https://speakerdeck.com/ryota0624/shi-jian-graphql-for-kuraiantoce）


## React + Apollo Client (GraphQL) により変化するアプリケーション設計
- スライド（https://speakerdeck.com/vwxyutarooo/react-plus-apollo-client-graphql-niyoribian-hua-suruapurikesiyonshe-ji?slide=11）
- https://blog.apollographql.com/reducing-our-redux-code-with-react-apollo-5091b9de9c2a
- Moving from Redux to GraphQL(https://speakerdeck.com/shrutikapoor08/moving-from-redux-to-graphql)
- メルカリはredux => GraphQLに移行してる
- RestfulAPIの置き換え？
- Apollo
- Apollo engine + VScode = やばい
- Apollo Client
- React Apollo
- Mutation(restfulでいうPOST)
- Apollo Link State
- Fluxに替われる？


## 貢献できるOSSの見つけ方 -完結編-
- OSS貢献超入門（https://www.slideshare.net/shigemk2/oss-78585757）



## 関連で見たいページ
- Apollo Client + React 入門（https://qiita.com/seya/items/e1d8e77352239c4c4897）
- How GraphQL Replaces Redux（https://hackernoon.com/how-graphql-replaces-redux-3fff8289221d）
- meteorjs（https://www.google.co.jp/search?rlz=1C5CHFA_enJP790JP790&q=meteorjs&nirf=meteor&sa=X&ved=0ahUKEwjAv_Xb--neAhUBxrwKHX-DCsEQ8BYIKigB&biw=1680&bih=917）
- ReactのHOC（https://qiita.com/numanomanu/items/2b66d8b2887d44f857dc）
- State of SEO for SPA 2018（https://speakerdeck.com/kazuyaseki/state-of-seo-for-spa-2018）
- JavaScript ASTを始める最初の一歩（https://efcl.info/2016/03/06/ast-first-step/）
- Webフロントエンド パフォーマンス改善ハンドブックを公開しました - dwango on GitHub（https://dwango.github.io/articles/web-frontend-performance-handbook/）
- リクルートテクノロジーズ　エンジニアコース新人研修の内容を公開します（2018年度版）（https://recruit-tech.co.jp/blog/2018/07/23/rtech_bootcamp_2018/）


## LT
### おまいらちゃんとリソース解放してますか（https://speakerdeck.com/shimataro/remember-to-close-resources）
nodeでのコネクション開放
ORＭであればいけてる
npmのon-finishedでもいける


### NodeとIoTの相性はいいらしい
ラインボットとか
マイコンボードはobniz


### 宇宙の話を例に挙げての失敗について
autoprefixerとかpostcssの作者
宇宙の話


### power-assert（https://speakerdeck.com/twada/from-library-to-tool-power-assert-as-a-general-purpose-assertion-enhancement-tool）
Evoleve slowly + easy to learn to write
互換性を伴って改良していく
v2
メンテナブルかつユーザー拡大の間
モダンブラウザのみ


### npmの選び方


### スクーシュ作った話
Googleで開発されてるウェブサービス
スクーシュのGitHubのプルリクみてみる
netlify
バージョン２めちゃめちゃいいかも
iframeEmbed対応
切り取りフイルター
複数枚対応

