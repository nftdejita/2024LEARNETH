Axelar Gatewayは、スマートコントラクトをAxelarエコシステムに接続するためのエントリポイントです。適切な関数をGatewayでトリガーすると、トランザクションはソースチェーンからAxelarネットワークを経由してデスティネーションチェーンへとインターチェーントランザクションの旅を開始します。Axelarに接続された各チェーンには、相互作用できるデプロイされたゲートウェイコントラクトがあります。

以下は、慣れておくべき二つの重要な関数です。

## callContract()

この関数は、ソースチェーンからデスティネーションチェーンへのメッセージを伴うインターチェーントランザクションをトリガーします。これには次の三つのパラメータが必要です：

1. `destinationChain`: デスティネーションチェーンの名前
2. `destinationContractAddress`: このトランザクションが実行されるデスティネーションチェーン上のアドレス
3. `payload`: 送信されるメッセージ

最初の二つのパラメータは直感的です。トランザクションを送るチェーンの名前と、そのチェーン上で実行するアドレスから構成されています。最後のパラメータはペイロードです。このペイロードはデスティネーションチェーンに送信される一般的なメッセージを表します。このメッセージは、デスティネーションチェーン上でさまざまな方法で使用できます。例えば、デスティネーションチェーン上の別の関数のパラメータとして使用されるデータを送信したり、関数のシグネチャをメッセージとして送信し、それがデスティネーションチェーンで実行されたりするなど、さまざまな用途があります。

## callContractWithToken()

この関数は、ソースチェーンからデスティネーションチェーンへのメッセージとファンジブルトークンを伴うインターチェーントランザクションをトリガーします。これには次の五つのパラメータが必要です：

1. `destinationChain`: デスティネーションチェーンの名前
2. `destinationContractAddress`: このトランザクションが実行されるデスティネーションチェーン上のアドレス
3. `payload`: 送信されるメッセージ
4. `symbol`: 送信されるトークンのシンボル
5. `amount`: 送信されるトークンの量

最初の三つのパラメータは`callContract()`と同じです。最後の二つのパラメータは、メッセージと一緒に送信されるトークンに関連するものです。これらは送信されるトークンのシンボルとその量です。
