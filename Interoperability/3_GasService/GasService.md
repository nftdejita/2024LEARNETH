Axelar Gas Serviceは、インターチェーントランザクションのガス料金を支払うための非常に便利なツールです。これにより、ソースチェーンのトークンでトランザクションのコストを支払うことができ、エンドユーザー（および開発者）の体験が大幅に向上します。例えば、ソースチェーンがEthereumでデスティネーションチェーンがPolygonの場合、ガスサービスはトランザクションの完全な支払いをETHで受け取り、Polygonデスティネーションチェーンでの実行に必要なMATICは不要です。

以下は、ガスサービスに関して慣れておくべき二つの重要な関数です。

## payNativeGasForContractCall()

この関数は、インターチェーントランザクションの全体のガス料金をソースチェーンのネイティブトークンで支払うことを可能にします。これには次の五つのパラメータが必要です：

1. `sender`: 支払いを行うアドレス
2. `destinationAddress`: トランザクションが送信されるデスティネーションチェーン上のアドレス
3. `destinationChain`: トランザクションが送信されるデスティネーションの名前
4. `payload`: 送信されるメッセージ
5. `refundAddress`: このトランザクションに過剰なガスが送信された場合に返金されるアドレス

これらのパラメータは、Gatewayコントラクトの`callContract()`関数で必要とされるパラメータと重なります。Gatewayセクションで説明されていない二つのパラメータは`sender`と`refundAddress`です。`sender`はトランザクションの支払いを行うアドレスで、`refundAddress`はガスサービスに送られた余剰資金を受け取るアドレスです。

## payNativeGasForContractCallWithToken()

この関数は、トークン転送を含むインターチェーントランザクションの全体のガス料金をソースチェーンのネイティブトークンで支払うことを可能にします。これには次の七つのパラメータが必要です：

1. `sender`: 支払いを行うアドレス
2. `destinationAddress`: トランザクションが送信されるデスティネーションチェーン上のアドレス
3. `destinationChain`: トランザクションが送信されるデスティネーションの名前
4. `payload`: 送信されるメッセージ
5. `symbol`: 送信されたトークンのシンボル
6. `amount`: 送信されたトークンの量
7. `refundAddress`: このトランザクションに過剰なガスが送信された場合に返金されるアドレス

この関数は最初の関数とほぼ同じですが、メッセージとトークン転送のトランザクション（GMPトランザクション）に使用されます。その結果、GasServiceは送信されるトークンの`symbol`と`amount`も知る必要があります。
