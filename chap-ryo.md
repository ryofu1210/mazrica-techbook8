# ITエンジニアのためのリモートワークマニュアル - VTRyo

この章を執筆したVTRyoです。マツリカではAWSとKubernetesによるサービス基盤開発やSREとしての役割を主に担当しつつ、
採用コンテンツ執筆やエンジニア広報業務も兼務しています。

私のこれらの業務を支えているのは、マツリカの"自由な働き方"です。
リモートワーク・フルフレックスによって、私は場所や時間に縛られることなく、自由に働けています。

　

総務省の定義では、テレワークという呼称で以下のように記載されています（以降もリモートワークと表記します）。

> テレワークとは、ICTを活用した時間や場所を有効に活用できる柔軟な働き方である。
> 在宅勤務、サテライトオフィス勤務、モバイルワークの3形態がある。働き方改革実現の切り札とも言われており、ワークライフバランスの実現 、人口減少時代における労働力人口の確保、地域の活性化などへの寄与、企業にとっては効率化や従業員のアウトプットへのプラスの効果も期待されている。

場所に囚われず働くことができる制度は、さまざまな背景を持った人たちにとって良い制度です。
しかし、残念なことに総務省が令和元年に実施した通信利用動向調査では、企業のリモートワークの導入率は19.1%という結果が出ています[^1]。

この普及率では導入する企業側や、リモートワークをする労働者としてもどのようにリモートワークしていけば良いのかわからないことも多いでしょう。

　

そこでこの章では、マツリカでリモートワークしてきた経験を元に『リモートワークするための技術』について執筆しています。

## 想定読者

* リモートワークのできる組織に所属するのでこれから始める人
* リモートワークってどんな風にやるのか知りたい人

## 免責事項

本章に記載された内容は、自社の環境に基づいた情報の提供のみを目的としています。したがって、本書を用いた開発、運用は、必ずご自身の責任と判断によって行ってください。
これらの情報による開発、運用の結果について、著者はいかなる責任も負いません。

また、このITエンジニアのためのリモートワークマニュアルでは、次のことについては記載しません。

* VPN設定や専用ソフトなど、リモートワークするまでに必要な設定
* リモートワーク導入までの流れ





[^1]: https://www.soumu.go.jp/johotsusintokei/whitepaper/ja/r01/html/nd124210.html

## マツリカのリモートワーク

マツリカのリモートワークは、さきほど引用した『在宅勤務』『サテライトオフィス』『モバイルワーク』の3形態どれも可能です。
在宅勤務やモバイルワークは言わずもがな、サテライトオフィスの契約もマツリカがしており、社員・アルバイト関係なく使用できます[^2]。

つまり私たちは、PCとネットワークさえ繋がっていれば世界中のどこからでも仕事することが可能です。
2020年2月時点で、マツリカで働くメンバーの居住地は日本だけでなくアジアやヨーロッパにも広がっています。

　

さて話題を変え、具体的に私自身の環境におけるリモートワークのメリットをご紹介しましょう（デメリットは別途記載）。

※私は都内近郊に住む20代既婚男性です。

* 満員電車に乗らなくて済む
* 通勤時間を別のことに当てられる
* 家に誰も居ないので静か
* 家の用事と仕事が並行できる
* 服などの外行きの準備が必要ない

都内にある会社へ通う人は避けられないであろう満員電車に乗ることは滅多になくなりました。
これにより、仕事開始時の体力と精神状態は良くなったと感じています。台風や大雪による公共交通トラブルに巻き込まれることはほとんどありません。

それは、私がITエンジニアというリモートワークしやすい職業だからでしょうか？
そうともいい切れません。マツリカでは営業職もWeb商談できる場合は実施しています。
完全フルリモート状態というのは難しいにしろ、たとえば午前中は自宅で作業するなど、できないことはない状態になっていると思います。










[^2]: マツリカが契約したコワーキングスペースに限ります

## リモートワークをはじめよう

## リモートワーク適正チェック

## リモートワークの心理的抵抗を考えてみよう

オフィスで働く方式を、ここでは便宜上『オフィスワーク』と表記します。

　

オフィスワークという従来の組織での働き方に慣れていると、
リモートワークを始める際『これまでオフィスワークでできたことができないのではないか』と考えがちです。

そこで『リモートワーク＝特殊』だという感覚から来る、心理的抵抗から考えてみましょう。
　

たとえば、はじめてリモートワークする際に生じる戸惑いで次のようなものが生じたとします。

* 困り事について聞きたいけど、そばにいるわけじゃないので聞けない
* コーディングなど

どうしてすぐに聞けないのでしょうか。相談者が近くにいないからでしょうか？
たとえ同じオフィスで働いていたとしても、近くの人が席に常にいるとは限りません。
お手洗いに立っているかもしれないし、会議中かもしれません。

もし相談者の時間を取るならば、あらかじめ予定を確保しておいたほうが無難と考えます。
リモートワークでも同じように、がっつり相談したいときはあらかじめ相手の予定を確保しておけば問題ないでしょう。

また、小さな相談事でもコミュニケーションツール（マツリカではSlack）上に書き込んでおけば誰かが反応してくれるかもしれません。
もしリモートワークをする先の組織でテキストコミュニケーションがあまり発達していない場合は


## 仕事の進め方

さて、あなたはついにリモートワークを始めることになりました。
気になるのは、どのように仕事を進めればよいのかということです。

　

ここで一度、前提を整理しておきます。

* 所属している組織にとってリモートワークが特別ではないこと
* 場所や労働時間の要素で評価されないこと
* オフラインだけで意思決定がされないこと（たとえば喫煙所で物事が決まるなどです）
* リモートワークする場所は作業者の自宅

「この前提のある組織自体が珍しいだろ！」という意見はごもっともですが、
これらの条件が揃っていない時点で組織側はリモートワークする準備ができていません。
自身の組織体制、文化を振り返ってみましょう。

### 進捗共有

かつてオフィスに集まって働く形式の会社に所属していたときは、始業時間過ぎにホワイトボード前で朝会が行われていました。
デイリースクラムかもしれないし、ただの進捗共有会かもしれません。この種類はとくに問いませんが、とにかく進捗共有は開発フロー上どうしても必要となります。

マツリカでも、この進捗共有は存在します。
現在マツリカプロダクトチーム（製品開発に関わるチーム）でもっとも多い進捗共有方法は『オンライン朝会』です。
理由は明白で、各プロジェクトごとに1人以上確実に地方リモートワーカーが在籍しているため、オンラインでの実施が必須となっています。
今の所『オンライン朝会』以外でリアルタイムに進捗共有する手段が見当たらないから、という現実でもあります。

この朝会では各プロジェクトチームによってさまざまな観点で進捗共有を行っていると思われます。
例として、私が所属していたプロジェクトの進捗共有観点をご紹介します。

* オンライン朝会までの進捗共有。どこまでタスクが進んだのかというシンプルなもの
* 相談事。進めているタスクにおいてなにか困りごとはあるのか

です。おや？これはオフライン・オンラインで大きな差はありませんね？

お気づきかと思いますが、場所がどこであれ基本的にやることはオフラインとなんら変わりはありません。
もし上記の観点以外にも実施内容があるならば、それをオンラインで実施するだけのことです。

マツリカではタスク管理をJIRAで管理しています。
このツールは組織によって異なってもなんら問題はなく、PCの画面を共有しながら進捗共有をしましょう。

余談ですが、最近ではオンラインで編集できる共同オンラインホワイトボードツール[^3]も存在します。

[^3]: 『miro』https://miro.com/

### 相談事

タスク消化中、困り事が発生したらどうすればいいでしょう。
リモートワークでは、隣に同僚や先輩・上司がいるわけではありません。

たとえば、はじめてリモートワークする際に生じる戸惑いは次のようなものが生じたとします。

* すぐに聞きたいけど聞けない
* ペアプロのように人が近くに必要な場合困る

まずは『リモートワーク＝特殊』だと思っている働き方から来る、心理的抵抗から考えてみましょう。

どうしてすぐに聞けないのでしょうか。隣りにいるわけではないからですか？
たとえ同じオフィスで働いていたとしても、隣の人が席に常にいるとは限りませんよね。
同様に、リモートワークでも相手が常に席に


ポイントは、自分が相談したいときだけではなく相手も同じ事を考えている場合もあるということです。


### リモートワーク初心者がぶつかるあるある事

* インターネット環境が悪くスムーズなコミュニケーションを取れずイライラ
* テキストコミュニケーションの難しさでイライラ
* 通勤時にしていたルーティーンができない


## 快適なリモートワークを実現しよう

### 自己管理編

スイッチの入れ方はそれぞれ
集中力
メリハリ
### 自宅作業

・設備投資
・ツール

### 外での作業

### 食事

・自炊

### 健康・休息



## 会社側がしておくといいリモートワーカーへの配慮

## 付録: みんなのリモートワーク事情
