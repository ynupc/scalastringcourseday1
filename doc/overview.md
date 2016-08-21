# 1.　概要
<p>言語処理技術を開発する前に文字列処理技術を詳細に勉強することが望ましいです。 文字列処理は簡単なようで落とし穴がたくさんあります。 文字列処理技術の勉強が足りないと、文字化けや原因がよくわからないExceptionが発生したりします。 また、車輪の再発明をしてしまい、開発に余計に時間がかかったりバグが発生するリスクを高めてしまったりすることも考えられます。 さらに、処理に無駄に時間がかかったり、メモリを無駄に多く使用したりするプログラムを書いてしまうかもしれません。 文字列処理を始めることは簡単ですが、正しく・楽に・効率的な処理を書くためには実はとても深い知識が必要とされます。 そこで、そのような落とし穴に落ちてしまわないために必要な深い知識を網羅的に学べるような教材作りを目指しています。 さらに、一般的な言語処理技術は、文字列を字句解析（形態素解析）にかけますが、その字句解析にかける前の処理（文字の正規化、特殊文字のエスケープ、表記揺れや誤字脱字に対する語の正規化、顔文字の取り扱い、文分割、文の正規化、引用符による文の構造解析など）も大切です。 しかし、泥臭いだけの単純作業になるため一般に研究として扱われておらず、その重要性が見落とされがちです。 前処理の重要性を示すもののひとつとして、　<a href="https://sites.google.com/site/nlp2016ws/program" target="_blank">NLP2016ワークショップ「論文に書かない（書けない）自然言語処理」</a>で、須藤克仁さんが「論文に書けなかった特許翻訳データの前処理」という題名で特許機械翻訳のタスクでの前処理の問題と丁寧に前処理をすると精度が上がったという発表をされていました。 特許文書のように比較的丁寧に記述されている文書であっても前処理が重要であると報告されました。 前処理を丁寧に書くためにも文字列処理技術を詳細に勉強する必要があります。 言語処理技術の開発を始める前に、開発中にエラー・バグが起こらないように、起こったときにうまく対処できるように、楽に効率的な処理が書けるように、そして字句解析前の前処理が丁寧に書けるようになるために、本教材を通して文字列処理のスペシャリストを目指しましょう。</p>
<img src="../image/string_course.002.jpeg" width="500px">
<p>さて、本コースでは、言語処理技術をScalaで開発するための事前知識としての文字列処理についてDay 1（概要と環境設定の本回）からDay 7までの７回に分けて学習します。全ての回で一般的な文字列処理について学べますが、サンプルコードは日本語の文字列処理を中心に紹介します。特にDay6とDay7では、日本語の文字列処理のための著者が作成したプログラムも提供します。それでは、学習する内容についてざっと紹介します。（いずれライブラリ化して提供できるかもしれません。）</p>
<p>まずは、リテラルについて紹介します。 Scalaには文字や文字列に関するリテラルがたくさんあります。 文字リテラル、文字列リテラル、生文字リテラルなどです。 エスケープシーケンスやUnicodeシーケンスなどについても触れます。（Day 2）</p>

<p>次に、コードポイントやサロゲートペアについて紹介します。 Scalaで適切に文字を扱うためには、１文字に対してChar型１つでは不十分な場合があります。 適切に文字を扱うためにはコードポイントやサロゲートペアについて学び、Stringとコードポイント配列への相互変換方法やStringのコードポイント数を取得する方法などについて紹介します。（Day 3）</p>

<p>型変換では、Boolean、Int、FloatといったJavaでいうプリミティブ型にあたるScalaの型とStringとの相互変換方法について紹介します。（Day 4）</p>

<p>ミュータビリティでは、イミュータブルクラスであるStringを扱うミュータブルクラス、StringBuilder、StringBufferなどについて紹介します。（Day 5）</p>

フォーマットでは、文字列のフォーマットやテンプレートに値を埋める処理について紹介します。ScalaだけではなくC言語など他の言語で`printf`という関数・メソッドが存在しますが、もし`printf`を使ったことがある方は、第一引数に"%s"や"%d"、"%f"といった記号を含めた文字列を渡しておき、第二引数以降に対応する値や変数を渡す機構に馴染みがあるかもしれません。この機構のことをprintfスタイルのフォーマットと呼び、`printf`の"f"はフォーマットを意味します。

<p>正規表現は、文字列が特定のパターンにマッチしたかどうかを調べたり、マッチした場合、その文字列を別の文字列に削除する、置き換える、あるいは取り出すといった処理が簡単かつ柔軟に書くことができます。正規表現の使い方について紹介します。（Day 6）</p>

<p>文字列操作では、Stringクラスのメソッドやフォーマット、正規表現など文字列を操作する方法を処理の目的別にどのようなときにどの方法を使用するのかまとめます。(Day 6)</p>

<p>文字の正規化ですが、日本語のテキストを処理する際、例えばカタカナの半角の「ｶ」と全角の「カ」、あるいは「ガ」と「カ」＋濁点「゛」のように一般的に同じ文字を指すがプログラム上では一致しない文字が存在します。このような字種による揺れが存在すると、文字列の一致を見たいときに問題が発生します。文字列の一致を見る前に、前処理として一方の表記に揃えておくことで不一致の問題を防ぐことができます。これを文字の正規化と呼び、具体的な方法について紹介します。（Day 7）</p>

<p>最後にオプションというScalaにある<a href="http://docs.oracle.com/javase/jp/8/api/java/lang/NullPointerException.html" target="_blank">NullPointerException</a>を排除するために役に立つ機構について紹介します。（Day 7）</p>

<!--<p>本コースは言語処理技術を開発するための事前知識としての文字列処理を学習しますが、ウェブに関する文字列処理については載せていません。ウェブに関する文字列処理とは、例えば、URLに日本語文字を載せると%でエスケープされるのは何？（<a href="https://docs.oracle.com/javase/jp/8/docs/api/java/net/URLEncoder.html" target="_blank">java.net.URLEncoder</a>/<a href="https://docs.oracle.com/javase/jp/8/docs/api/java/net/URLDecoder.html" target="_blank">java.net.URLDecoder</a>使おう）とか、formで外部からサーバに文字列を送信する際のセキュリティ問題について（SQLインジェクションとかCSRFトークンとかの問題はとりあえず長く使われているウェブアプリケーションフレームワーク使おう。私は<a href="http://liftweb.net/" target="_blank">Lift</a>を気に入っていますが、<a href="https://www.playframework.com/" target="_blank">Play 2</a>とか<a href="https://projects.spring.io/spring-framework/" target="_blank">Spring MVC</a>とか<a href="http://www.scalatra.org/" target="_blank">Scalatra</a>の方が人気がありそうです。<a href="http://www.slideshare.net/mraible/comparing-jvm-web-frameworks-devoxx-france-2013?next_slideshow=1" target="_blank">Comparing JVM Web Frameworks</a>）とか、HTMLをパースするにはどうしたらいいの？（<a href="http://jsoup.org/" target="_blank">jsoup</a>）とか、JSONをパースするにはどうしたらいいの？（<a href="https://github.com/google/gson" target="_blank">google-gson</a>）とか、YAMLをパースするにはどうしたらいいの？（<a href="https://bitbucket.org/asomov/snakeyaml" target="_blank">SnakeYAML</a>）とか、Linked Open Dateを使うにはどうしたらいいの？（RDF、SPARQLなどセマンティックウェブ）とか、&amp;amp;、&amp;lt;、&amp;gt;、&amp;copy;、&amp;quot;などHTMLやXMLの特殊文字の変換はどうしたらいいの？（Apache Commons Langの<a href="https://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/StringEscapeUtils.html" target="_blank">StringEscapeUtils</a>）とか、WikipediaのデータをHTMLに変換するにはどうしたらいいの？（<a href="https://code.google.com/p/gwtwiki/" target="_blank">Bliki</a>）とか、HTMLのタグの中でテキストを含むタグはどれ？とか、PDFからテキストを抽出するにはどうしたらいいの？とか、BingやTwitterなどで検索するにはどうしたらいいの？（BASIC認証、OAuth認証、OpenID認証など）とか、そういったことは本コースの対象にはしてはおりません。ウェブに絡めて言語処理技術を開発するためには、上記のようにさらに広い知識が必要になるでしょう。ウェブに関する文字列処理ができるようになりたいとしても、本コースは文字列処理の基礎として学習する価値は十分にあるはずです。</p>-->
