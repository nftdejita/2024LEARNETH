トークン標準は、コントラクトが準拠するために必要な機能を教えてくれます。これらの機能がどのように実装されるかは開発者次第です。このコントラクトでは、OpenZeppelinのERC20トークンコントラクト実装を使用します（4行目）。この場合、OpenZeppelinコントラクトのバージョン4.4.0をインポートします。

実装がどのようなものかをよりよく理解するために、よく文書化された<a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/ERC20.sol" target="_blank">ERC20コントラクト</a>を参照してください。ERC20標準で指定されている機能に加えて、このコントラクトは追加の機能も提供します。

次に、インポートしたOpenZeppelin ERC20トークンコントラクト実装から機能を継承する`MyToken`というコントラクトを作成します（6行目）。

このコントラクトはERC20トークン標準のオプション関数`name()`と`symbol()`を実装し、デプロイ時にそれらの値を設定できるコンストラクタを持っています（7行目）。
この場合、デフォルト値を使用します。トークンの名前はコントラクトと同じく`"MyToken"`とし、シンボルは`"MTK"`とします。

次に、デプロイ時にトークンを作成するための継承された`_mint`関数を使用します（8行目）。パラメータ内には、トークンを受け取るアカウントのアドレスと作成されるトークンの量を指定します。
この場合、コントラクトをデプロイするアカウントがトークンを受け取り、トークンの量を`decimals()`の乗数として1000000に設定します。ERC20トークン標準のオプション関数`decimals()`は実装され、デフォルト値の18に設定されています。これにより、小数点以下18桁の1000000トークンが作成されます。

## ⭐️ 課題
1. コントラクトの名前を`EduCoin`に変更します。
2. トークンの名前を`EduCoin`に変更します。
3. トークンのシンボルを`EDC`に変更します。
4. 鋳造されるトークンの量を1000000から1000に変更します。
