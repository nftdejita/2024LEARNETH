このセクションでは、関数の動作を変更する方法と、コントラクトの初期化コードを実行する方法について学びます。

### 関数修飾子
*関数修飾子*は、関数の動作を変更するために使用されます。例えば、条件をチェックして関数の実行を制限したり、入力を検証したりします。

このコントラクトの最初の部分は、コントラクトの所有権の変更に関するものです。このコントラクトにおける所有権は、`address`型のステート変数`owner`の値で表されます（7行目）。

関数`changeOwner`（33行目）は、この所有権を変更できます。この関数は、`address`型の入力パラメータを取り、その値をステート変数`owner`に割り当てます。

しかし、この関数はすべての条件下で単純に実行されるわけではなく、`onlyOwner`と`validAddress`の2つの修飾子を持っています。

まず`onlyOwner`（18行目）を見てみましょう。
関数修飾子は`modifier`キーワードと一意の名前で定義され、パラメータを持つこともできます。

修飾子内で使用されるアンダースコア`_`（23行目）は、修飾された関数の本体で実行されるコードの残りを表します。
修飾子の中でアンダースコアの前に配置されたコードは、修飾された関数の本体のコードの前に実行されます。アンダースコアの後に配置されたコードは、修飾された関数の本体のコードの後に実行されます。

この場合、`require`関数（19行目）は、コントラクトを実行しているアドレスが変数`owner`に格納されている値と同じであるかをチェックします。同じであれば、残りのコードが実行され、そうでなければエラーがスローされます。

`assert`と`require`については、<a href="https://docs.soliditylang.org/en/latest/control-structures.html#error-handling-assert-require-revert-and-exceptions" target="_blank">Solidityのドキュメント</a>で詳しく学ぶことができます。これらは条件をチェックし、条件が満たされない場合にエラーをスローするために使用されます。

`validAddress`修飾子（28行目）は、`address`型のパラメータを持ち、提供されたアドレスが有効であるかをチェックします。有効であれば、コードの実行を続行します。

### コンストラクタ
コンストラクタ関数は、コントラクトの作成時に実行されます。これを使用してコントラクトの初期化コードを実行できます。コンストラクタはパラメータを持つことができ、コントラクトのデプロイ前に特定の初期化値がわからない場合に特に便利です。

コンストラクタは`constructor`キーワードを使用して宣言します。このコントラクトのコンストラクタ（11行目）は、コントラクトの作成時に所有者変数の初期値を設定します。

<a href="https://www.youtube.com/watch?v=b6FBWsz7VaI" target="_blank">関数修飾子のビデオチュートリアルを見る</a>。

## ⭐️ 課題
1. 新しい関数`increaseX`をコントラクトに作成します。この関数は`uint`型の入力パラメータ`y`を取り、その入力パラメータの値だけ変数`x`の値を増加させます。
2. 関数修飾子を使って引数`y`がゼロより大きい事を保障します。
3. 同様に関数修飾子を使ってステート変数`x`に引数`y`を加算します。
5. `increaseX`関数の本体は空であることを確認します。

ヒント: 関数修飾子は`biggerThan0`と`increaseXbyY`を使用します。