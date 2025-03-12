---
title: 【初心者にやさしい】Dartで理解する「オブジェクト指向型プログラミングの4つの柱」
tags:
  - Dart
  - オブジェクト指向
  - クラス
  - Flutter
  - 初心者エンジニア応援
private: false
updated_at: '2022-07-25T21:52:31+09:00'
id: a3bd3a00fed45a0cc65d
organization_url_name: null
slide: false
ignorePublish: false
---
# 本記事の目的
　特にプログラミング初心者の方は、「__オブジェクト指向型プログラミングとは？__」と聞かれても、一言で説明するのは難しいのではないでしょうか。かく言う私もその一人です。実際に様々な書籍やサイトを見てみても、異なる説明が数多く見受けられます。
　しかし、オブジェクト指向型プログラミングというモノ自体を一言で言い表すのは難しくても、 __実際にどのようなことができるのかということは理解することは十分にできると思います。__
　そこで今回は、「__オブジェクト指向型プログラミングの4つの柱__」と題して、「__オブジェクト指向型プログラミングでどのようなことが出来るのか__」ということをわかりやすく説明してみたいと思います。

# 本記事の内容
　本記事では、まず「__オブジェクト指向型プログラミング__」というものをざっくりと説明した後に、「__大切な4つの柱__」について解説します。尚、イメージを掴みやすくするため、オブジェクト指向型言語である「__Dart__」を使用したアプリ開発を例に説明させていただきます。

# ざっくりと理解する「オブジェクト指向型プログラミング」
　__オブジェクト指向型プログラミング__ とは、「__役割ごとに分割されたモノ(= Object)を一つ一つ組み合わせることで、一つの複雑で大きな処理を実行できるモノを作り上げる__」という考えに基づいて行うプログラミングのことを指します。
　現実の世界でイメージするならば、「 __飛行機の組み立て__ 」をイメージしていただけると分かりやすいと思います。飛行機には、「エンジン」、「右翼」、「左翼」、「胴体」などなど、ありとあらゆるパーツが組み合わさることで飛行機が出来上がり、「飛行する」という大きなタスクを実行できるようになっています。これはまさに「__オブジェクト指向型の設計__」と呼べるのではないでしょうか。
![オブジェクト指向(飛行機の例).png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/4ddbca1a-1a4e-0363-72c4-ffd2b9ef5759.png)
　このように、オブジェクト指向型プログラミングでは、「__すべてのことを一箇所でまとめてやる__」のではなく、「__役割ごとに分解して作業をし、最終的に一つに組み合わせる__」という手法を用いていきます。
　こちらのやり方であれば、複雑なプログラミングになったとしても効率的かつ安全に開発していけますよね。
　では、このオブジェクト指向型プログラミングを実現するために、具体的にどうすればいいのかを理解するために、「__オブジェクト指向型プログラミングの4つの柱__」を一つ一つ見ていくことにしましょう。
![オブジェクト指向型プログラミングの4つの柱.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/e9a417f9-bd8c-775b-a633-817830e0a18d.png)

# 柱その1： 抽象化(Abstraction)
　抽象化とは、簡単にいうと「__役割分担__」です。例えば、レストランでの従業員の仕事をイメージしてください。
![非抽象化.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/2d45cb25-cad7-298b-9d20-3ad58fcbf787.png)
　もし上の写真のように、一人の従業員しかおらず、その人一人であらゆる仕事を一手に引き受けて行わなければならないとしたらどうでしょう。結果は見えていますね。「__すべてのことに手が回らず、ミスが多発し、ミスの原因がどこにあるのかも分かりずらいので改善も難しい__」という負の連鎖に陥ることが予想されます。
![抽象化の実践.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/5b403f45-c9e0-ff32-0b4f-d586e2a27135.png)
　一方、上の写真のように「__役割分担__」を行ったらどうでしょうか。それぞれが自分の役割だけに集中することで、それぞれの業務の質が上がります。そして明確な役割分担をしていることにより、もしミスが起きたとき、どこに原因があるのかを特定しやすくなります。そうすることで早期改善を図ることが出来るようになるのです。
　この時、お互いの仕事内容を細かく理解する必要はありません。例えば、「__調理__」の人は、「__受付__」の人の仕事内容について、「__受付業務をする人__」と理解すればいいので、細かい仕事内容はブラックボックス状態でもいいわけです。これが「__抽象化__」です。今回の例でいえば、 __他の人は受付の人のことを「受付業務をする人」と抽象的に理解しておけばよく、あとは自分自身の役割に専念して受付業務は任せておけば良い__ のです。
　
　これをプログラミングに当てはめて考えると、「__メインのクラスに数多くの記述を行なって複雑にするのではなく、役割ごとに別々のサブクラスに切り出し、メインの方では、サブクラスにある変数やメソッドを呼び出す記述を書くのみにする__」という手法をとっていくことが必要になります。実際の例で見てみましょう。
　今回掲載するのは、Dartを用いて開発されたFlutterというフレームワークを使用して、「電卓アプリケーション」を実装した時のコードになります。大まかに内容を説明すると、「home.dart」というファイルで画面(UI)に関するコードを書いており、「logic.dart：というファイルで内部の計算ロジックに関するコードを書いています。後ほど「mysql.dart」というファイルも登場しますが、こちらはDBに関するコードを書いております。

lib/home.dart
```dart
// ignore_for_file: prefer_const_constructors
import 'package:flutter/material.dart';
import 'package:font_awesome_flutter/font_awesome_flutter.dart';
import 'constants.dart';
import 'logic.dart';
import 'mysql.dart';
import 'history_page.dart';

class MyHomePage extends StatefulWidget {
  final String userId;
  final String username;

  const MyHomePage({Key? key, required this.userId, required this.username})
      : super(key: key);

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  // 画面上に表示する内容を格納する変数
  String text = "";

  String txtResult = "0";

  final MySQL _mysql = MySQL(); // MySQLクラスのインスタンスを作成

  final Logic _logic = Logic(); // Logicクラスのインスタンス作成

  @override
  void initState() {
    super.initState();
    // _mysql.dbConnect();
  }

  // ボタンをウィジェット化
  Widget button(String text, Color colorButton, Color colorText) {
    return Expanded(
      flex: (text == "0") ? 2 : 1,
      child: Padding(
        padding: const EdgeInsets.all(3.0),
        child: SizedBox(
          height: double.infinity,
          child: ElevatedButton(
            onPressed: () {
              setState(() {
                switch (text) {
                  case "AC":
                    _logic.clearNum(text);
                    break;
                  case "+/-":
                    _logic.invertNum(text);
                    break;
                  case "Del":
                    _logic.deleteOnesPlace();
                    break;
                  case "÷":
                    _logic.halfwayCalculation(text);
                    break;
                  case "×":
                    _logic.halfwayCalculation(text);
                    break;
                  case "-":
                    _logic.halfwayCalculation(text);
                    break;
                  case "+":
                    _logic.halfwayCalculation(text);
                    break;
                  case "=":
                    _logic.finalCalculation();
                    try {
                      _mysql.manipulateCalcDB(
                          _logic.formula, _logic.displayedNumber, widget.userId);
                    } catch (e) {
                      txtResult = e.toString();
                    }
                    _logic.formula = "";
                    break;
                  default:
                    _logic.input(text);
                    break;
                }
                txtResult = _logic.text;
              });
            },
            style: ElevatedButton.styleFrom(
              primary: colorButton,
              onPrimary: colorText,
              shape: RoundedRectangleBorder(
                borderRadius: BorderRadius.circular(10.0),
              ),
            ),
            child: Text(
              text,
              textAlign: TextAlign.center,
              style: TextStyle(
                fontFamily: font,
                fontWeight: FontWeight.bold,
                fontSize: 30.0,
              ),
            ),
          ),
        ),
      ),
    );
  }

// 以下画面描画のコード省略
```
lib/logic.dart
```dart
import 'dart:math' as math;
import 'package:intl/intl.dart' as intl;
import 'package:audioplayers/audioplayers.dart';

class Logic {
  String _text = "0";

  get text => _text;

  // 画面に出力できる最大値
  static const MAX_DEGIT = 9;

  // 値を表示する変数
  double displayedNumber = 0;

  // 現在値を格納する変数
  double _setCurrentNumber = 0;

  //掛け算・割り算の結果を保持する変数
  double _temporaryNumber = 0;

  //掛け算・割り算の結果を保持する変数
  double _previousValue = 0;

  //掛け算・割り算の演算子を記録しておく変数
  String _multiDivOperator = "";

  //足し算・引き算の演算子を記録しておく変数
  String _addSubOperator = "";

  // 小数点ボタンが押されたかどうかを示すbool値
  bool _decimalFlag = false;

  // "."が押された後の数値の数をカウントする変数
  int _numAfterPoint = 0;

  //桁区切り実装用
  intl.NumberFormat formatter = intl.NumberFormat('#,###.########', 'en_US');

  // 画面上部に出力するメッセージ
  String cheeringMessage = "";

  // String型に変換したdisplayedNumber
  String displayedNumberAsString = "";

  // データベースに保存する計算式の部分を格納するリスト
  String formula = "";

  bool audioPlayed = false;

  AudioCache _cache = AudioCache(fixedPlayer: AudioPlayer());
  AudioPlayer? _player;

  //画面上の数値をオールクリアするメソッド
  void clearNum(text) {
    _text = text;
    _text = "0";
    displayedNumber = 0;
    _setCurrentNumber = 0;
    _previousValue = 0;
    _temporaryNumber = 0;
    _multiDivOperator = "";
    _addSubOperator = "";
    _decimalFlag = false;
    cheeringMessage = "All Clear!";
    _numAfterPoint = 0;
    formula = "";
  }

  // 一の位の数値を削除していくメソッド
  void deleteOnesPlace() {
    String displayedNumberAsString = displayedNumber.toString();
    // double型を文字列に変えたため、整数も小数もデフォルトで文字数が「3」になる
    if (displayedNumberAsString.length > 3) {
      // 単なる整数値の時（例：24.0)
      if (displayedNumberAsString[displayedNumberAsString.length - 1] == "0") {
        displayedNumberAsString = displayedNumberAsString.substring(
            0, displayedNumberAsString.length - 3);
      } else {
        displayedNumberAsString = displayedNumberAsString.substring(
            0, displayedNumberAsString.length - 1);
      }
      // 小数点数で、「.000~」となるときは、double型に変換すると一気に「0.0」まで戻ってしまう
      if (displayedNumberAsString != "-") {
        displayedNumber = double.parse(displayedNumberAsString);
      }
      _numAfterPoint--;
      _decimalFlag = false;

      _text = getDisplayText(displayedNumber);
    }
  }
}

// 以下、コード省略
```
　「home.dart」では主に画面描画に関する記述を行なっており、内部のロジックに関するコードは「logic.dart」という別ファイルに切り出しています。そして、注目すべきは、「home.dart」の中盤から出てくる「_logic.clearNum」や「_logic.deleteOnesPlace」のような記述です。これはhome.dartにおいて、別ファイルにあるLogicクラスのインスタンスを作成し、メソッドを呼び出す記述になっています。__この時、コードの読み手はそのメソッドの細かい内容を知らずとも、「ここで〇〇をするメソッドを呼び出しているんだな」と抽象的な理解をすることができます。そしてその細かい内容を確認するときは、「logic.dart」の方を見に行けばいいことになります。__
　もしこの時、ロジック部分を別ファイルに切り出さずにhome.dartにそのまま記述していたらどうでしょう。ただでさえ、コード量が多いのにさらに量が増し、可読性が落ちますね。エラーが起きたらどこを見ればよいのかも分かりづらいですね。
　だからこそ、役割ごとに分けることで可読性が向上し、エラーが発生したときはどのファイルを確認すればよいかも明確になります。
　一目で理解しやすいコードはその分保守性も高まりますので、ぜひこの抽象化を実践してみてください。

::: note warn
掲載したコードにもまだまだリファクタリングの余地があります。あくまで抽象化の一例としてのコードなので、細かい部分へのご指摘はご遠慮願います🙇‍♂️
:::

# 柱その2： カプセル化(Encapsulation)
　カプセル化とは、簡単に言うと、「__不干渉__」です。
　こちらもレストランでの業務をイメージしてください。
![干渉.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/59729ccc-7e1f-896a-af53-4a2794872d98.png)
　もし、 __「配膳」の人が「調理」の人に文句を言い出したらどうでしょうか。__ 「配膳」の人は明らかに自分の役割の外に出てしまっています。それぞれの役割に集中することで、やるべきことを明確にしていくことが必要なのに、 __自分の役割外のことにまで口を出してしまっては元も子もありません。こうなると、役割が不明確になり、やがて不具合が起きてしまうでしょう。__
![カプセル化実践.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/0c936c2b-874f-2e5d-5267-ae8a5b9024e8.png)
　では、どうすればよいのか。
　__「調理」の人と「配膳」の人との間に壁を作り、互いに干渉しないようにしてしまいましょう。__ レストランで調理ゾーンと配膳ゾーンの間に壁があるのはこういうことなのかもしれませんね。こうすることで、お互いの役割に集中できるようになります。 __この不干渉によってお互いの役目がシンプルになり、ミスの減少にもつながっていきます。__

　では、これもプログラミングにおいてどのように実践していくのか。
　まず、以下のコードを見てください。同じく電卓アプリを実装した時のコードです。

lib/home.dart(画面描画に関するコードファイル)
```dart
// ignore_for_file: prefer_const_constructors
import 'package:flutter/material.dart';
import 'package:font_awesome_flutter/font_awesome_flutter.dart';
import 'constants.dart';
import 'logic.dart';
import 'mysql.dart';
import 'history_page.dart';

class MyHomePage extends StatefulWidget {
  final String userId;
  final String username;

  const MyHomePage({Key? key, required this.userId, required this.username})
      : super(key: key);

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  // 画面上に表示する内容を格納する変数
  String text = "";

  String txtResult = "0";

  final MySQL _mysql = MySQL(); // MySQLクラスのインスタンスを作成

  final Logic _logic = Logic(); // Logicクラスのインスタンス作成

  @override
  void initState() {
    super.initState();
    _mysql.dbConnect();
　　　　　　 // mysql.dartファイルで値を変更するべきところをhome.dartで値変更を行なってしまっている
    _mysql.dbConnectExec = true;
  }

// 以下、画面描画の記述を省略
```
lib/mysql.dart(DBに関するコードファイル)
```dart
import 'dart:async';
import 'package:mysql1/mysql1.dart';
import 'package:flutter_dotenv/flutter_dotenv.dart';

class MySQL {
  String sql = "";
  List<String> resultLists = [];
  List<String> formulaLists = [];
  List<String> userList = [];
  // ignore: prefer_typing_uninitialized_variables
  var conn;

  // dbConnectメソッドが実行されたかどうかを判断するbool値
  bool dbConnectExec = false;

  Future dbConnect() async {
    await dotenv.load();
    // Open a connection
    conn = await MySqlConnection.connect(ConnectionSettings(
      host: (dotenv.env['HOST1']).toString(),
      port: int.parse(dotenv.get('PORT')),
      user: (dotenv.env['USER']).toString(),
      db: (dotenv.env['DB']).toString(),
      password: (dotenv.env['PASSWORD']).toString(),
    ));

    // 本来この位置で「dbConnectExec = true」とするべき
  }

// 以下DBに関する記述省略
```
　上記は、home.dartファイルからmysql.dartファイルにある __dbConnect()__ というメソッドを呼び出す部分を抜き出したものになっています。
　ここで注目していただきたいのが、mysql.dartで定義されている
```dart
bool dbConnectExec = false;
```
という変数をhome.dart側で操作しているという点です。home.dartにおいて以下の記述でそれを実践しています。
```dart
_mysql.dbConnect();
_mysql.dbConnectExec = true;
```
　これはまさに「__干渉__」してしまっている状態になります。本来であれば、DBに関する記述はすべてmysql.dartにまとめるべきですので、当然「_mysql.dbConnectExec = true;」という記述をmysql.dartのdbConnect()というメソッドに含めるべきです。このように役割を無視して記述を行うと、誤って値変更をしてしまい思わぬエラーを引き起こす可能性があるので、以下のコードのように役割分担をして、互いに干渉させないようにしていきましょう。

lib/home.dart
```dart
// ignore_for_file: prefer_const_constructors
import 'package:flutter/material.dart';
import 'package:font_awesome_flutter/font_awesome_flutter.dart';
import 'constants.dart';
import 'logic.dart';
import 'mysql.dart';
import 'history_page.dart';

class MyHomePage extends StatefulWidget {
  final String userId;
  final String username;

  const MyHomePage({Key? key, required this.userId, required this.username})
      : super(key: key);

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  // 画面上に表示する内容を格納する変数
  String text = "";

  String txtResult = "0";

  final MySQL _mysql = MySQL(); // MySQLクラスのインスタンスを作成

  final Logic _logic = Logic(); // Logicクラスのインスタンス作成

  @override
  void initState() {
    super.initState();
     // メソッドを呼び出すのみにする
    _mysql.dbConnect();
  }

// 以下、画面描画の記述を省略
```
lib/mysql.dart
```dart
import 'dart:async';
import 'package:mysql1/mysql1.dart';
import 'package:flutter_dotenv/flutter_dotenv.dart';

class MySQL {
  String sql = "";
  List<String> resultLists = [];
  List<String> formulaLists = [];
  List<String> userList = [];
  // ignore: prefer_typing_uninitialized_variables
  var conn;

  // dbConnectメソッドが実行されたかどうかを判断するbool値
  bool _dbConnectExec = false;

  Future dbConnect() async {
    await dotenv.load();
    // Open a connection
    conn = await MySqlConnection.connect(ConnectionSettings(
      host: (dotenv.env['HOST1']).toString(),
      port: int.parse(dotenv.get('PORT')),
      user: (dotenv.env['USER']).toString(),
      db: (dotenv.env['DB']).toString(),
      password: (dotenv.env['PASSWORD']).toString(),
    ));
    
    //DBに関する変数の値変更はここで行う
    _dbConnectExec = true;
  }

// 以下DBに関する記述省略
```
　ちなみに先ほどとは違い、「_dbConnectExec」の様に変数名の前に「_」をつけています。この様に変数名の前にアンダースコアをつけることで、その変数を「プライベート変数」として定義できます。こうすることで、この変数にはそのクラス外からはアクセスできない様になります。これで「__カプセル化__」がより一層実践できました。

# 柱その3： 継承(Inheritance)
　継承とは、そのままの意味であり、「__ある特定の要素を受け継いで利用していくこと__」を言います。
　お馴染みのレストランでの業務をイメージしてみましょう。
![継承.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/2ef17a9b-023b-c756-ca5b-89e1f9c83050.png)
　もし、「料理」の人の中に、「料理長」と「焼き菓子のシェフ」がいた場合、焼き菓子のシェフの担当する内容の一部はおそらく料理長も担当できることでしょう。つまり、 __料理長と焼き菓子のシェフのできることに重複があります。__
　この場合、焼き菓子のシェフは __一から自分の力でノウハウを蓄積していくよりも、料理長にノウハウを教わってそれを実践して行った方が手間がかからず、効率的にスキルを習得できるはず__ です。

　プログラミングにおいても、このような継承は、「__クラスの継承__」として利用することができます。クラスとは「__設計図__」であり、「__プロパティ__」と「__メソッド__」が定義されています。そんなとき、もし新たなクラスを作りたいとなったら、元々あるクラスの一部のプロパティやメソッドが使えるならば、 __一から書き直すよりも、「継承します！」ということを宣言する記述をしてしまった方が効率的__ ですね。
　このようにして、プログラミングにおいても「継承」を利用していくことができます。実際のコードで見てみましょう。
　今回はブラウザ上でDartが使用できる「Dart Pad」を使用してご説明します。
![ノーマルなクラス.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/8f39948b-a2d8-0e97-25ab-db26d0a407d8.png)
　まず、「__Car__」というクラスがあり、mainメソッドからCarクラスのインスタンスを作成して、プロパティやメソッドを呼び出しています。
![クラスの継承.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/814a1a2e-b2e5-a884-1b36-6fabae1d8aa1.png)
　ここでもし、「__ElectricCar__」という別のクラスを作ろうとなったとき、「Car」クラスのプロパティやメソッドを使用したいならば、「__extends Car__」のように記述することで、Carクラスの内容を受け継いで使用できるようになります。上の写真では、mainメソッドでElectricCarクラスのインスタンスを作成して、Carクラスのdriveメソッドを呼び出したところ、しっかりと「wheels turn」と結果を出力できていますね。これはElectricCarクラスがCarクラスの内容を受け継ぐことができていることを示しています。
![クラスの継承プラスアルファ.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/71432328-ab1f-f829-45a6-8f6a56929c13.png)
　もちろん上の写真のようにCarクラスの内容を受け継いだ上で、自分のクラス独自のプロパティやメソッドを作成することもできます。 __継承できる部分は一から書き直す必要がないように継承し、独自の部分は記述する__ というようにして、可読性を向上させていきましょう。

# 柱その4： ポリモーフィズム(Polymorphism)
　ポリモーフィズムとは、簡単に言うと「__独自解釈__」です。
　同じくレストランでの業務をイメージしましょう。
![ポリモーフィズム.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/5851b5b5-4059-d309-36f5-528a3b93f287.png)
　例えば、「焼き菓子のシェフ」が「料理長」から技術として「ソース作りのノウハウ」を受け継いだとします。このとき、 __技術的には全く同じものを受け継いだとしても、もしかしたらその技術に対する解釈の仕方はそれぞれで違っているかもしれません。__ もしかしたら料理長は、他にも多くの仕事をこなさなければならないため、「__ソース作りはなるべく手早く__」と考えているかもしれません。一方焼き菓子のシェフは、「__ソース作りは慎重にじっくりと__」と考えているかもしれません。この場合、焼き菓子のシェフは __受け継いだモノを独自に解釈し直して利用している__ と言うことができます。これが __ポリモーフィズム__ です。
　プログラミングに当てはめて言えば、「__親クラスから継承したプロパティやメソッドを独自にカスタマイズし直して使用する__」という様になります。

　こちらも実際のコードで見てみましょう。
![ポリモーフィズムの実践.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/599bd17f-f484-b75b-e905-dbe6c499b91b.png)
　写真一番下で作成した __LevitatingCarクラス__ はCarクラスを継承しています。つまり、Carクラスの「__numberOfSeat__」と「__driveメソッド__」がそのまま使用できるわけです。しかし、ここで、 __driveメソッドの内容を独自にカスタマイズして使用したいとなった場合は、Dartでは「@override」という記述を加えて新しくdriveメソッドの内容を定義してあげれば、独自のメソッドとして使用できる様になります。__
![ポリモーフィズムプラスアルファ.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2375287/c01de0e4-95f8-cae6-6639-b430f1c5214b.png)
　また、上の写真のコードでは、少し難しいですが、「@override」で独自にカスタマイズするのに加えて、Carクラスの元々のdriveメソッドも呼び出しています。「__super__」という記述がそれを可能にしています。
　このように、継承したものを独自にカスタマイズして利用していくことで、効率的かつ柔軟なコーディングを行っていける様になります。

# まとめ
　今回はオブジェクト指向型プログラミングではどのようなことが大切で、どのようなことができるのかを具体例を用いて分かりやすく説明することに努めました。例えとして用いたレストラン業務に関して、かなり偏見で解釈してしまっている部分が多く見受けられますが、その点に関しては何卒ご容赦ください。
　とにかく、 __オブジェクト指向型プログラミングを実践することで、コードの可読性と保守性が向上し、効率的かつ安全な開発へと進んでいくことができるようになる__ ということを理解していただけたのであれば幸いです。
　今回掲載したコードもかなりリファクタリングの余地がありますし、私自身も完全には理解しきれていない部分もありますので、今後も手を動かしながらしっかりと理解していきたいと思います。

# 参考資料
・[Dart Pad ~ブラウザ上でDartが使える便利ツール~](https://dartpad.dev/?id)
・[Flutter公式](https://flutter.dev/)
・[Flutter Bootcamp With dart ~Udemy講座~](https://www.udemy.com/course/flutter-bootcamp-with-dart/)
・リーダブルコード~より良いコードを書くためのシンプルで実践的なテクニック
・コンピュータはなぜ動くのか~知っておきたいハードウェア&ソフトウェアの基礎知識






