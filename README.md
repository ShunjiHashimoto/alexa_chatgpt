# alexa_chatgpt
アレクサとchatgpt使って雑談
https://twitter.com/23232871hashimo/status/1632344063965036544?s=20  
## 設定
### Alexa Developer Console
アレクサにスキルを登録します。  
スキルの作成方法は[公式ドキュメント](https://developer.amazon.com/ja-JP/docs/alexa/devconsole/about-the-developer-console.html)を参考にしてください  
下記は、設定方法の補足です。  
- 呼び出し名  
「先輩」と設定  
![invocation](https://github.com/ShunjiHashimoto/alexa_chatgpt/blob/main/docs/images/invocation.PNG?raw=true)
- インテント  
「先輩、〜」と先輩と問いかけたあとの言葉をChatGPTに渡す言葉としています。  
![intent](https://github.com/ShunjiHashimoto/alexa_chatgpt/blob/main/docs/images/intent.PNG?raw=true)
- エンドポイント  
自作したLambda関数のARNをここに入力します。  
また、スキルIDはAlexa Developer Consoleで先程作成したスキルのIDを登録してください。  
![endpoint](https://github.com/ShunjiHashimoto/alexa_chatgpt/blob/main/docs/images/endpoint.png?raw=true)
### AWS Lambda  
Lambda関数を作り、その関数をAlexa Developer Consoleから呼び出します。   
Lambda関数の作成方法は、[公式ドキュメント](https://docs.aws.amazon.com/ja_jp/lambda/latest/dg/getting-started.html)を参考にしてください。  
下記は、lambda関数で外部モジュールを利用したい場合の設定方法です。  

#### lambda関数のレイヤー設定
OpenAI、ask_sdk_coreそれぞれをローカルにインストール後、zipファイルに圧縮し、その圧縮されたファイルをレイヤーに登録します。  
- ask_sdk_core
    - [こちらのサイト](https://qiita.com/toshimin/items/e4d9bc3380db4d171f0e)を参考にしました。  
![layor](https://github.com/ShunjiHashimoto/alexa_chatgpt/blob/main/docs/images/layor.png?raw=true)  
- OpenAI
    - [こちらのサイト](https://thedeveloperspace.com/how-to-invoke-openai-apis-from-aws-lambda-functions/)を参考にしました。  