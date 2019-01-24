<h1 align="center" style="border-bottom: none;">🔊 Text to Speech デモ </h1>
<h3 align="center">Node.js の IBM Watson Text to Speech (音声合成) サンプルアプリケーション </h3>
<p align="center">
  <a href="http://travis-ci.org/watson-developer-cloud/text-to-speech-nodejs">
    <img alt="Travis" src="https://travis-ci.org/watson-developer-cloud/text-to-speech-nodejs.svg?branch=master">
  </a>
  <a href="#badge">
    <img alt="semantic-release" src="https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg">
  </a>
</p>
</p>

Text to Speechはストリーミング、低レイテンシ、テキストからのオーディオの合成のために設計されています。

こちらのアプリケーションのデモ(英語)は [こちら][demo_url] で見ることができます。

## 事前準備

1. [IBM Cloud アカウント](https://console.bluemix.net/registration/) の取得
2. [IBM Cloud CLI](https://console.bluemix.net/docs/cli/index.html#overview)のダウンロード
3. Speech to Text APIの資格情報の取得
    - Webブラウザを開き、[IBM Cloud](https://cloud.ibm.com/) にログインする。
    - 「[IBM Cloud ダッシュボード](https://cloud.ibm.com/)」→「カタログ」→ 「AI」→「[Text to Speech](https://cloud.ibm.com/catalog/services/text-to-speech) 」の順にアクセスする。
    - 任意のサービス名を入力し、デプロイする地域/ロケーションの選択で **ダラス** を選択し、**「作成」** ボタンをクリックする。
    - **「資格情報」** に表示される `API鍵` および `URL` をコピーしてメモしておく。

## アプリケーションの設定

0. Gitリポジトリをクローンまたはダウンロードする。
   ```
   git clone https://github.com/ayatokura/text-to-speech-nodejs
   ```

1. アプリケーションフォルダ内の *.env.example* ファイルを *.env* というファイル名でコピーファイルを作成する。

    ```
    cp .env.example .env
    ```

2. エディタで *.env* ファイルを開き、前の手順で取得した資格情報を追加して保存する。

    デプロイする地域/ロケーションで「ダラス」を選択した場合の例:

    ```
    TEXT_TO_SPEECH_IAM_APIKEY=
    TEXT_TO_SPEECH_URL=https://stream.watsonplatform.net/speech-to-text/api
    ```

## ローカルで実行する方法

1. コマンドラインで依存関係をインストールするコマンドを実行する。

    ```
    npm install
    ```

2. 次のコマンドを実行でアプリケーションをローカルで実行する。

    ```
    npm start
    ```

1. ebブラウザで `localhost:3000` にアクセスする。

## IBM Cloud へデプロイする方法

1. コマンドラインから [IBM Cloud CLI](https://console.bluemix.net/docs/cli/index.html#overview)
を使ってIBM Cloud へログインする。

    ```
    ibmcloud login
    ```

2. Cloud Foundryの組織とスペースをターゲットにするコマンドを実行する。

    ```
    ibmcloud target --cf
    ```
3. *manifest.yml* ファイルを開き、 **name** フィールドを任意の名前に置き換えて保存する。
   ```
   - name: my-app-name
   ```
4. 次のコマンドでアプリケーションをIBM Cloudへデプロイする。

    ```
    ibmcloud app push
    ```

5. 再起動後、Webブラウザで、アプリケーションをデプロイしたURLへアクセスする。  
例えば、前の手順でmy-app-nameを指定した場合:  https://my-app-name.mybluemix.net


## Directory structure

```none
.
├── app.js                      // express routes
├── config                      // express configuration
│   ├── error-handler.js
│   ├── express.js
│   └── security.js
├── manifest.yml
├── package.json
├── public                      // static resources
├── server.js                   // entry point
├── test                        // tests
└── views                       // react components
```

## ライセンス

  This sample code is licensed under Apache 2.0.

## Contributing

  See [CONTRIBUTING](./CONTRIBUTING.md).

## Open Source @ IBM
  Find more open source projects on the [IBM Github Page](http://ibm.github.io/)


[service_url]: https://www.ibm.com/watson/services/text-to-speech/
[docs]: https://www.ibm.com/watson/developercloud/text-to-speech/api/v1/curl.html?curl
[sign_up]: https://console.bluemix.net/registration/?target=/catalog/services/text-to-speech/
[demo_url]: https://text-to-speech-demo.ng.bluemix.net