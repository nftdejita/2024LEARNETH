# オフセットを見つける ;)

では、少し異なる例を見てみましょう：

- `notSimpleStore.sol`をコンパイルします。
- `notSoSimpleStore`コントラクトをデプロイします。
- デプロイが成功したことを確認します。成功しない場合は、コンストラクタで**正しい入力タイプ**を使用したか確認してください。
- 成功した作成トランザクションで**デバッグ**ボタンをクリックしてデバッガに移動します。
- calldataからコピーするオフセットを表す`CODECOPY`のパラメータの値を見つけます。

覚えておいてください：*codecopy(t, f, s)* - **s**バイトを**f**位置のコードから**t**位置のメモリにコピーします。

**スタック**を見てみると、2番目の要素が次のようになっているはずです：
0x0000000000000000000000000000000000000000000000000000000000000083

これが、codecopyの入力パラメータの**f**です。

### オペコードの動作について、いくつか学んだことがあるといいですね！
