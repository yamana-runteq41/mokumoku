# README

## 環境構築
```
$ bundle install --without=production
$ bin/rails db:setup
$ yarn install
$ bin/webpack
$ bin/rails s
```

## 事業をエンジニアリングしよう提案編の回答は以下に記述してください

【選択した事業側の課題】
直近一年間で、2回以上もくもく会に参加してくれた人は利用者全体の1%のみ。もくもく会で気の合う仲間を見つけられなかったのではないか？

【提案内容】
参加者のレベル別（具体的には、エンジニア経験年数別）でもくもく会を開催できるようにする。
→
① エンジニア経験の長いユーザーは、似たレベルのユーザーが多い場で知識共有ができるようになる。それによってもくもく会の価値が高まり再参加を見込めるようになる。エンジニア経験の浅いユーザーは、参加する際の心理的ハードルが下がることで、継続的な参加がしやすくなる。
② 運営側は、年数別の選択肢を設けることにより、必然的に経験年数の浅い人が初めて参加することを見込めるようにもなる。

【実装方針】
・もくもく会作成時に参加対象者の指定を必須にする。あらかじめ「3年未満」、「4〜9年」、「10年以上」、「全員」といった選択肢（タグ）を作成しておき、セレクトボックスによってその選択ができるようにする。イベント作成者は、自分が該当する年数か全員かのどちらかを選択した上でイベントを作成する。
・ヘッダーにある検索フォームで、上記で作成した選択肢（タグ）による絞り込み検索ができるようにする。その際、あらかじめすべての選択肢を並べて表示させておき、ユーザーがそのうちの1つを押下すれば該当するイベントの絞り込みができるようにする。このようにタグをあらかじめ表示させておくことによって、そもそもそのような分類でイベントが開催されているという情報を、ユーザーに即座に与えることができる。
・イベント一覧画面に表示されるイベント概要（現在はタイトル, 内容, 開催地, 開催日時, 作成者が表示されている部分）に、参加対象のタグも表示させる