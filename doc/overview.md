# 1.　概要
<img src="../image/string_course.002.jpeg" width="500px">
<p>本コースでは、言語処理技術をScalaで開発するための事前知識としての文字列処理について学習します。</p>
<p>まずは、リテラルについて紹介します。 Scalaには文字や文字列に関するリテラルがたくさんあります。 文字リテラル、文字列リテラル、生文字リテラルなどです。 エスケープシーケンスやUnicodeシーケンスなどについても触れます。</p>

<p>次に、コードポイントやサロゲートペアについて紹介します。 Scalaで適切に文字を扱うためには、１文字に対してChar型１つでは不十分な場合があります。 適切に文字を扱うためにはコードポイントやサロゲートペアについて学び、Stringとコードポイント配列への相互変換方法やStringのコードポイント数を取得する方法などについて紹介します。</p>

<p>型変換では、Boolean、Int、FloatといったJavaでいうプリミティブ型にあたるScalaの型とStringとの相互変換方法について紹介します。</p>

<p>ミュータビリティでは、immutableクラスであるStringを扱うmutableクラス、StringBuilder、StringBufferなどについて紹介します。</p>

フォーマットでは、文字列のフォーマットやテンプレートに値を埋める処理について紹介します。ScalaだけではなくC言語など他の言語で`printf`という関数・メソッドが存在しますが、もし`printf`を使ったことがある方は、第一引数に"%s"や"%d"、"%f"といった記号を含めた文字列を渡しておき、第二引数以降に対応する値や変数を渡す機構に馴染みがあるかもしれません。この機構のことをフォーマットと呼び、`printf`の"f"はフォーマットを意味します。

<p>正規表現は、文字列が特定のパターンにマッチしたかどうかを調べたり、マッチした場合、その文字列を別の文字列に削除する、置き換える、あるいは取り出すといった処理が簡単かつ柔軟に書くことができます。正規表現の使い方について紹介します。</p>

<p>文字列操作では、Stringクラスのメソッドやフォーマット、正規表現など文字列を操作する方法を処理の目的別にどのようなときにどの方法を使用するのかまとめます。</p>

<p>文字の正規化ですが、日本語のテキストを処理する際、例えばカタカナの半角の「ｶ」と全角の「カ」、あるいは「ガ」と「カ」＋濁点「゛」のように一般的に同じ文字を指すがプログラム上では一致しない文字が存在します。このような字種による揺れが存在すると、文字列の一致を見たいときに問題が発生します。文字列の一致を見る前に、前処理として一方の表記に揃えておくことで不一致の問題を防ぐことができます。これを文字の正規化と呼び、具体的な方法について紹介します。</p>

<p>最後にオプションというScalaにある<a href="http://docs.oracle.com/javase/jp/8/api/java/lang/NullPointerException.html" target="_blank">NullPointerException</a>を排除するために役に立つ機構について紹介します。</p>

<p>本コースは言語処理技術を開発するための事前知識としての文字列処理を学習します。言語処理技術であってウェブアプリケーション開発ではないので、ウェブに関する文字列処理については載せません。ウェブに関する文字列処理とは、例えば、URLに日本語文字を載せると%でエスケープされるのは何？（<a href="https://docs.oracle.com/javase/jp/8/docs/api/java/net/URLEncoder.html" target="_blank">java.net.URLEncoder</a>/<a href="https://docs.oracle.com/javase/jp/8/docs/api/java/net/URLDecoder.html" target="_blank">java.net.URLDecoder</a>使おう）とか、formで外部からサーバに文字列を送信する際のセキュリティ問題について（SQLインジェクションとかCSRFトークンとかはとりあえず長く使われているウェブアプリケーションフレームワーク使おう。私は<a href="http://liftweb.net/" target="_blank">Lift</a>を気に入っていますが、<a href="https://www.playframework.com/" target="_blank">Play 2</a>とか<a href="https://projects.spring.io/spring-framework/" target="_blank">Spring MVC</a>とか<a href="http://www.scalatra.org/" target="_blank">Scalatra</a>の方が人気がありそうです。<a href="http://www.slideshare.net/mraible/comparing-jvm-web-frameworks-devoxx-france-2013?next_slideshow=1" target="_blank">Comparing JVM Web Frameworks</a>）とか、HTMLをパースするにはどうしたらいいの？（<a href="http://jsoup.org/" target="_blank">jsoup</a>）とか、JSONをパースするにはどうしたらいいの？（<a href="https://github.com/google/gson" target="_blank">google-gson</a>）とか、YAMLをパースするにはどうしたらいいの？（<a href="https://bitbucket.org/asomov/snakeyaml" target="_blank">SnakeYAML</a>）とか、OpenLinkedDateを使うにはどうしたらいいの？（RDF、SPARQLなどセマンティックウェブ）とか、&amp;amp;、&amp;lt;、&amp;gt;、&amp;copy;、&amp;quot;などHTMLやXMLの特殊文字の変換はどうしたらいいの？（Apache Commons Langの<a href="https://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/StringEscapeUtils.html" target="_blank">StringEscapeUtils</a>）とか、WikipediaのデータをHTMLに変換するにはどうしたらいいの？（<a href="https://code.google.com/p/gwtwiki/" target="_blank">Bliki</a>）とか、HTMLのタグの中でテキストを含むタグはどれですか？とか、PDFからテキストを抽出するにはどうしたらいいの？とか、BingやTwitterなどで検索するにはどうしたらいいの？（BASIC認証、OAuth認証、OpenID認証など）とか、そういったことは本コースの対象にはしておりません。</p>
