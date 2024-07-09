Ethereumネットワーク上でのトランザクションを通じてコードを実行するには、トランザクション手数料としてEtherを支払う必要があります。トランザクションを実行するために支払わなければならない手数料の額は、そのトランザクションの実行にかかる*ガス*の量に依存します。

### ガス
*ガス*は、Ethereumネットワーク上で特定の操作を実行するために必要な計算努力の量を測定する単位です。

### ガス価格
Ethereumを動かすための*ガス*は、時々車を動かすためのガスに例えられます。車が消費するガスの量はほとんど同じですが、ガスに対して支払う価格は市場によって異なります。

同様に、トランザクションが必要とする*ガス*の量は、それに関連する計算作業が同じであれば常に同じです。しかし、トランザクションの送信者が支払う意思のある*ガス*の価格は送信者次第です。ガス価格が高いトランザクションはより速く処理されますが、ガス価格が非常に低いトランザクションは処理されないこともあります。

トランザクションを送信する際、送信者はトランザクションの実行時に*ガス*手数料（gas_price * gas）を支払わなければなりません。実行が完了した後にガスが残っていれば、送信者は払い戻されます。

*ガス*価格はgweiで示されます。

### ガスリミット
トランザクションを送信する際、送信者は支払う意思のあるガスの最大量を指定します。リミットが低すぎると、トランザクションが完了する前にガスが不足し、行われた変更が元に戻される可能性があります。この場合、ガスは消費され、払い戻されません。

<a href="https://ethereum.org/en/developers/docs/gas/" target="_blank">ethereum.org</a>でガスについての詳細を学んでください。

<a href="https://www.youtube.com/watch?v=oTS9uxU6cAM" target="_blank">ガスとガス価格に関するビデオチュートリアルを見る</a>。

## ⭐️ 課題
`Gas`コントラクトに`cost`という名前の新しい`public`なステート変数を`uint`型で作成します。コントラクトのデプロイにかかるガスコストの値を、新しい変数に格納します。

ヒント: Remixのターミナルでトランザクションの詳細を確認でき、ガスコストも含まれています。Remixプラグイン*Gas Profiler*を使用して、トランザクションのガスコストを確認することもできます。
