# JDD (Jyu-So-Shi(origin Ju-Dung-A-Ri) Driven Development/呪詛駆動開発)

![JDD_Logo](https://github.com/Lee-WonJun/JDD-Description/assets/10369528/e63b4e5a-b6a4-4357-807c-767df9193fa5)

JDDは、コード作成よりも言い訳を事前に考えて、数多くのバグを養成できる開発方法論だ。

JDDは以下の重要な価値観に従う。

```
我々は

- 他人が使う技術より、自分のものを

- CleanなコードよりはTrickyなものを

- バグFixよりは言い訳を

- 面倒よりは気楽を

価値があると思う。この言葉、左側のものは面倒で、右側のものは便利であるため、より高い価値を持つということだ。
```

呪詛師として実践するためには休むことなく険しい道（どう）だが、着実に努力しなければならない。
重要なことは、関連するカッコいい用語を言い出しながら、実際の問題に対する答えを回避することだ。着実な練習が必要だ。

# JDDのためのガイドライン

## JDDのための心構え

JDDの基礎となる心構えを常に心に留めよう。

### 真のリーダー

眠ったり...いや、真のリーダーは部下をいじめません。

```
- 誰かがPRをしたこと自体が見事。
LGTM（Looks Good To Me）。

- 誰かがPRを飛ばすと自動的にLGTMを飛ばすCI/CDを活用しよう

- 同僚にはビジネスロジックの重要性を、企画者には開発の難しさを逆説しよう。
その間にman/monthだけを軸内させる。
誰が何と言ったら、「プロジェクト管理」と言おう。

- 昔のやり方にこだわりましょう。
誰が何と言ったら、「ビジネス中心の開発」と言おう

- メンテナンス性は考えないようにしましょう。
誰が何と言ったら、「MVP（Minimum Viable Product）」と言おう
```

### 防御的プログラミング

防御的プログラミングはエンジニアの基本的な素養だ。

```
- 防御的プログラミングをしよう。
コードを書くことで防御しないで、あなたに入ってくるタスクを防御しよう。

- 作業量が多いか？
ただ、特定のテストケースだけ回れるように書いて、残りは「高度化」作業でやると言おう。
「高度化」作業の前に離職しよう。

- 「実装の可能性」とはいうのは他人ではなく結局コードを書く俺が決めることだ。
気楽に企画者にそれは実装不可能だと言おう。
```

## 実績重心回避

よく働くふりをしながら楽な生活をするために実績重心に行動しなければならない。

### マルチスレッド

並行性は難しく、実績が目立たない。

```
- マルチスレッド環境での可変変数の使用によるエラーは時々発生する。
時々発生することに比べて使用はとても楽。
誰が何と言えばそんなことないと言えば良い。

- やむを得ずマルチスレッドタスクが渡されたら、プログラミング言語を愚痴ってこのタスクがなんで難しいのか説明しよう。
ああ、この言語はActorモデルが貧弱で...
CSP（Communicating Sequential Processes）実装体がないので...
STM（Software Transactional Memory）がサポートしていないので...
悪口を言うほど締め切り期間が延びる。

- 非同期フロー内で同期関数を密かに書いてもよい。
後でボトルネックを探すタスク+非同期に改善する追加タスク工数まで一緒に貰える。
```

### 文書化

我々の本分を忘れないようにしよう。

```
- コメントは絶対に作成しないことにしよう。
誰が何て言ってもクリーンコードを言い出しましょう。もちろんそうだとしてもコードがreadableではない。

- 我々はエンジニアだ。
どんな理由があっても文書作成は禁物。
誰かが何か言ったら「コードがすなわち文書」。

- 履歴は必要ない。
既往は咎めず。

- 引き付きのための文書は必要ない。
誰が何と言えば俺のコードは読めばすぐ理解できるよと言おう。
未練なく脱出しよう。

- GPTの発展速度はすごい。
文書が要る人がしたらもうすぐAIが全部作ってくれるよって言おう。
```

### チーム開発

単語からもう目眩がする。

```
- Disagree and Never Commit

- 複数人で同時に同じコードを作成しないといけなければ何とかして分けて作業した後マージしようとしよう。
相手も一つのタスクを一緒にくっついて作業するなんて考えてない。

- ブランチのマージ（Merge）中conflictが起こりそうな時点で休みを取るのは必須だ。

- ブランチのマージ（Merge）中conflictが起きたらoursを覚えろ。
俺のブランチが優先だ。
相手が修正した内容を考慮する必要はない。

- ペアーコーディングは意外と大丈夫だ。
自分がコードを書く時は頭をちょっと空かして良くて、他の人がコードを書く時は打ち間違いくらいだけ見つけてあげれば十分だ。
一番のメリットは書かれたコードに対して責任が減るってことだ。

- どんな作業か別に知らせたくなければコミットメッセージは`chore: trivial`としましょう。変態じゃなければこんなコミットを読もうとする人はいないだろう。

- PRをマージ（Merge）する時はSquash mergeを最大限活用して作業中に入った自分がしたバカなことを隠そう。
誰が何と言えば「コミットログを簡略に維持するため」と言おう。

- コミットを分ける時はタスクや機能単位ではなく自分が一気に直した分を基準にしよう。
どうせマージされたら全てSquashされてちゃんと見えない。

- PR Descriptionはタスク管理ツールのtaskリンクだけissueとして入れてあげよう。
もちろんリンクを辿っても説明みたいなもんってないです。

- チーム開発にコミュニケーションスキルは必須だ。
「領域展開口だけの人」で相手を混乱させてPRに自分の怠惰が討論履歴として残らないように対話を誘導しよう。

- 承諾より容赦が簡単だ。
何とか早くマージ（Merge）しないといけない。

- 同僚のコードでエラーや打ち間違い、簡単なミス（重複したへん、チームコードルール、Lintなど）を見つけても共有するな。
同僚があなたが和を守ってることをほのかに気づかせよう。
同僚も自分のミスに目を閉じてくれるはずです。

- コミット（Commit）数が少ないほどコードに天才性が表す。
コミット数が多いって言うのはその間何も考えずコードを書いたってことだ。
コードを修正する度にgit resetコマンドを適切に活用してmasterブランチにforce pushしましょう。コミット履歴には自分だけ残る。
つまり、天才性を独りで占めることができる。

- 分からない技術を勉強しないようにしよう。
同僚が整理した文書だけさりげなく読んでみよう。
結局技術を使わないといけない場合は同僚の時間を奪って一緒にやってほしいって言おう。
誰か何て言えば「チームワーク」と言おう。

- コードレビュー（Code Review）はしないようにしよう。
自分のコードが議論の余地も無く正解。
誰かレビューを頼むとミスのフリをしてマージ(Merge）しなきゃいけない。

- pushを間違った時はreset --hardを愛用しよう。
誰が何て言えばrevertはコミット履歴が汚くなるって言おう。
```

### Protection

```
- PRは非効率的だ。
すぐmasterブランチにマージしよう。

- repository rule設定は開発を遅くする主犯だ。
全ての権限をOnにしとこ。

- サーバーの全てのportはOnにしとこ。
誰かが脆弱だと言ったらIPブラックリストを管理すると答えよう。

- CICDが失敗してもマージしよう。

- API keyは publicに載せても問題ない。
どうせ誰も見ない。
```

## 何でもプログラミング

世界は０と1から成り立ってると言える。だから何をするだろうが自分がするのは「プログラミング」ってわけだ。

(下記はto be continue...)
### モダンプログラミング

モダンは現在だ。つまり今自分が使ってる技術がすなわちモダンな技術だ。

```
- 例外処理をしないようにしよう。
誰が何て言えば「Let it crash戦略」だと言おう。

- 言語のFeatureを最大限使わないようにしよう。
誰が何て言えばメンテナンスのため誰でも理解できるように書いたと言い張ったら良い。

- 言語のFeatureを最大限活用しよう。
誰が何て言えばモダンプログラミングだと言えば良い。

- 依存性が複雑になっていたら、「パターン」だと言おう。

- チェーイニング（Chaining）が一つでもあれば、Fluent API スタイル

- チェイニングが一つもなければ、ディミーター法則

- 関数だけ呼び出す関数があれば、ミニー言語でDSLを実装したと言おう

- データを渡す関数があれば、Data-Driven Progirammingだと言おう

- 関数のパラーメーターが多くすぎると？
誰が何て言えばより「純粋」に書いたと言おう

- ラムダ関数だけで構成しよう。誰が何て言えば高階関数関数型プログラミングと言おう。

- パターンを全く使わないようにしよう。
誰が何て言えば「単純性の原則」だと言おう。

- Map-Reduce-Filterみたいな高階関数は一切使わないようにしよう。
誰が何て言えばこれも同じく単純性の原則だと言おう。
Keep it simple, Stupid!

- アノテーションみたいなmeta dataを数十個はつけよう。
誰が何て言えばメタプログラミング記法だと言おう。

- OOP(Object-Oriented Programming)で開発する人々の間ではFPパターン（Functional Programming)を積極的に活用しよう。
ライブラリまで使うとさらに良い。
Maybeクラスを作るのは基本中基本。
誰が何て言えば「これが最近のスタイルです」

- FPで開発する人々の間ではOOPパターンと可変変数を積極的に活用しよう。
誰が何て言えば「FPは実用的ではない」

- 俺のコードより長いと冗長（verbose）、俺のコードより短いと難解（esoteric）

- コールバックヘルを読んでこれ何って言われたらCPS(Continuation Passing Style）だと答えよう。

- 全てのif文は三項演算子で書こう。誰がなんていえば、「あ、ifは文で三項は式ですからね」

- リストコンプリヘンション、オプショナルチェイニング、リアクティブなどを使って誇りを持って言いましょう「モナディックに解決したと」、
それは何と聞かれたら「モナドの呪いのせいで説明が難しい」まで言うのまでやらないと。

- 二つ以上実行されるサービスがあればMSA（Micro-Service Architecture）だ。
テストを回してくれるスクリプトだけ別にあってもMSAだ。
そこに言語が違うとpolyglotまでしたと言える。
```

### 言語

俺の言語が優越だ。

```
- 言語論争には言ったもん勝ちの文章がある「言語は道具だ」

- TypeScript、 CoffeeScript, ClojureScriptなどJSのスーパーセットは一切使わないようにしよう。
誰が何て言えばJSはそもそもそう設計された言語でそれが根本だと言いましょう。

- 何個かの言語はわざわざ自分が文句を言う必要がない。
wtfjs / golang.sucksなど他の人の文句を引用しよう。
```

### 設計

どのように設計しても回るには回る。

```
- クラス、インターフェース、イーナム、メンバーなど構造設計に対してこうだこうだ言っても、ADT(Algebraic Data Type)合型がどうだ掛型がどうだ

- クラスの機能があまりにも少ないと、「あ、それはレコードで書こうとしました。」

- 継承が合成より楽だ。
誰がなんて言えばOOP(Object-Oriented Programming)には当たり前に継承を使うのがあってると言えば良い。

- nullは10億ドルの価値がある。
何でも曖昧だったらnullを返そう。

- ObjectやAnyはポリモーフィズムの極義だ。
何でも曖昧だったらObjectタイプを返そう、Objectタイプを返す関数でnullをリ返すようにするのがベスト
```

### テスト

正直テストコードを書くのは面白くない

```
- テストコードを全く作成しないようにしよう。
誰がなんて言えばreplでテストが終わったと言おう。

- テストがどの場合は成功してどの場合は失敗したら、「attribute基盤テスト」を作成したからそうだと言おう。

- テストコードがなくても、コードがちゃんと動作するってことを自分でちゃんと説明できると言おう。
誰かがテストコードを求めるなら「俺のコードは複雑すぎてテストができない」と言おう

- テストが失敗したら、テストを削除しよう
```

### パーフォマンス最適化

CPU性能は自分の実力と違って日々発展する。

```
- DTO/VO変換は使わないようにしよう。
誰がなんて言えばパーフォマンス最適化だと言おう

- DTO/VOはもちろん何のModelも作らない。
みんなMap(Dictionary）　data structureを使おう。
誰がなんて言えばData Oriented Programmingだと言おう。
もちろんValidationみたいなものはしない。

- DBはその時必要なフィールドを追加しよう。
正規化とか規則は考えもしないようにしよう。
誰がなんて言えばこれも同じくパーフォマンス最適化

- パターンとかアーキテクチャーは使わないようにしよう。
クラスにも分けるな。
Nのfor文とif文で順次的に書こう。
誰がなんて言えばこれは本当にパーフォマンス最適化だと言おう。

- パーフォマンス最適化はどんな状況でも禁物、誰がなんて言えば最近は「コンパイラー」に任せるのがトレンドだと言おう。
```

## ヒューマンオート(Human Automation)

俺が楽になるためにはタスクを最大限自動化しないといけない。

どうせ誰かはそのタスクを担うはず。

これはつまり、それをやる人が自分じゃなければ自動化（Human Automation）を達成したってことだ。

### バックエンド

バックエンドはモダンビズネスの核心だ。変なとこに力使うな

```
- それはフロントエンドがすべきだと言おう。
- それは元々バックエンドがフロントエンドより忙しいと言おう。
- それはDBAがすべきだと言おう。
- それはDevOpsエンジニアがすべきだと言おう。
- それは企画チームでまず企画すべきだと言おう。
- それは運営チームにまず確認をもらうべきだと言おう。
- それはChatGPTにまず確認をもらうべきだと言おう。
```

### フロントエンド

フロントエンドはユーザーが向かい合う初印象だ。変なとこに力使うな

```
- それはバックエンドがすべきだと言おう。
- それは元々フロントエンドがバックエンドより忙しいと言おう。
- それはアプリエンジニアがすべきだと言おう。
- それはパブリッシャーがすべきだと言おう。
- それはデザイナーがすべきだと言おう。
- それはユーザーがすべきだと言おう。
- それはバグじゃなくてイースターエッグって言おう。
- それはデザインが元々そうだと言おう。
```

### DBA

DBMS 개발자를 믿자

```
- N+1 문제가 자동으로 해결되지 않는 이 세상이 이상한 거다. 개발자는 신경 쓰지 말자.

- fetch join + paging 문제가 자동으로 해결되지 않는 이 세상이 이상한 거다. 개발자는 신경 쓰지 말자.

- slow query 문제가 자동으로 해결되지 않는 이 세상이 이상한 거다. 개발자는 신경 쓰지 말자.

- SQL / ORM 등에서 힘겹게 쿼링하는것보다 그냥 다 불러와서 map/reduce/filter 쓰는 게 더 편하다.

- 정규화는 할 필요 없이 테이블 하나로도 충분하다. 누군가 뭐라 하면 join 비용의 절감이라고 하자.
```

### 머신러닝

요즘 기계는 대충 가르쳐도 알아서 잘 배운다.

```
- 데이터 하나가 소중한 시점에 Validation set 에 떼줄 데이터 따위 없다. 죄다 학습에 넣어버리자.

- 오버피팅이 일어나면 오히려 좋다. 누군가 딴지를 걸면 "실험 환경에서는 성능이 좋았는데요."라고 말하자.

- 성능이 너무 낮으면 데이터가 부족하기 때문이라고 하자.

- 모델이 너무 크다면 딥러닝이 원래 그런 거라고 하자.

- 모델이 너무 작다면 모델 최적화의 결과라고 하자. 최적화의 부작용으로 성능이 조금 떨어질 수 있다는 점도 곁들여주면 좋다.

- training 이 너무 오래 걸린다고 하면, 더 좋은 GPU 를 쓰면 된다고 하면서 NVIDIA DGX A100 같은 것을 보여주자.

- inference 가 너무 오래 걸린다고 하면, 더 좋은 GPU 를 쓰면 된다고 하면서 NVIDIA V100 같은 것을 보여주자.

- Productization 은 DevOps, MLOps 엔지니어의 역할이다. 모델 리서처는 신경 쓰지 말자.

- Seed값 고정을 피해라. 이로써 성능이 생각보다 안 나와도 Randomness 탓을 하며 시간을 벌 수 있다.
```

### 기획

IT 서비스 기획자는 서비스에 계획 및 로드맵 수립 + 협의를 주도하고 프로젝트를 관리한다. 모두 개발자에게 맡기면 된다.

```
- 그건 개발자가 알아서 해야 할 일이라고 해라.

- 그건 개발자의 실력이 부족해서 그런 거라고 해라.

- 잘못된 기획을 해도 그거는 개발자들이 알아서 잘 만들면 된다고 해라.

- 기획이 변경되어도 그거는 개발자들이 알아서 잘 만들면 된다고 해라.

- 내 일정은 소중하지만 전체 일정은 관심이 없다 나만 야근 안 하면 된다.

- 그냥 PPT 를 빨리 찍어서 개발자와 디자이너에게 업무 요청을 하고 설명해주고 손 털면 끝이다. 이후에 질문들은 바쁘다고 최대한 피하던가 휴가를 사용하자.

- 위에서 이 기획안으로 진행해야 한다고 결정했다고만 말해라.

- 위에서 결과물을 가지고 쪼면 개발자들이 퍼포먼스가 안 나온다고 말해라.

```

## その他

この文書...正直もうやりすぎたな...

```
- 그날 배운 기술은 그날 회사 프로젝트에 적용해라. 누가 뭐라고 하면 그날 배운 지식을 자랑하면 된다

- 기술 스택을 공부하지 말고, 해당 기술 스택의 단점 리스트만 공부해라. 누가 해당 기술 스택을 물어보면, 단점을 들먹이자

- 도커같이 가상화가 조금이라도 들어간 건 사용하지 말아라. 누가 뭐라고 하면 네이티브 환경에서의 확인이 필요하다고 해라

- 간단한 기능만 짜놓고 열심히 하는 척 게으름 피우자. 누가 뭐라고 하면 '린Lean'하게
```

# Reference

驚くと思うけど結構たくさん参考した

- [유지보수하기 어렵게 코딩하는 방법: 평생 개발자로 먹고 살 수 있다](https://www.hanbit.co.kr/store/books/look.php?p_code=E2375873090)
- [애자일 선언](https://agilemanifesto.org/iso/ko/manifesto.html)
- [프로그래밍의 정석](http://www.yes24.com/Product/Goods/55254076)
- [7가지 동시성 모델](http://www.yes24.com/Product/Goods/29331038)
- [폴리글랏 프로그래밍](http://www.yes24.com/Product/Goods/12204890)
- [클린 코드](http://www.yes24.com/Product/Goods/11681152)
- [클린 아키텍쳐](http://www.yes24.com/Product/Goods/77283734)
- [클로저 프로그래밍의 즐거움](http://www.yes24.com/Product/Goods/24555451)
- [프로그래밍 스칼라](http://www.yes24.com/Product/Goods/27767797)
- [FSharp Fun and Profit 블로그](https://fsharpforfunandprofit.com/)
- [로버트 C 마틴 블로그](https://blog.cleancoder.com/)
- [마틴파울러 블로그](https://martinfowler.com/)
- [wtfjs](https://github.com/denysdovhan/wtfjs) / [golang suck](http://www.golang.sucks/)
- [코딩 호러의 이펙티브 프로그래밍](http://www.yes24.com/Product/Goods/8611802)
- [Data Oriented Programming](https://www.manning.com/books/data-oriented-programming)
- [Amazon, 2016 Letter to Shareholders](https://www.aboutamazon.com/news/company-news/2016-letter-to-shareholders)
- 그 외 언젠가 한 번쯤 읽어본 책들 다수
- 그 외 언젠가 한 번쯤 읽어볼 책들 다수
- 나무위키

# Contributing

もっと良いくちばし方法を知っていればPRを投げてください。

# License

JDDは何の制約もないです。
ただ、責任も取りません。
