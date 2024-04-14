# ComfyUI-RequestsPoster
* 入力（any）に反応して指定のURLにrequests.post(url,{key:value})を投げられます。
* X（Twitter）にポストする機能を使う場合、ComfyUIが利用するPython環境に「tweepy」モジュールが入っている必要があります。

# インストール方法
下記のどちらかでインストールできます
* ComfyUI-Managerの「Install via Git URL」でこのリポジトリのクローン用URLをコピペする<br>
クローン用URLはこのページの上部にある緑色のボタン「<> Code」を押すと表示されます。
* ComfyUI > Cutom_nodesのフォルダをコマンドプロンプトで開き下記コマンドを実行する<br>
`git clone https://github.com/aburahamu/ComfyUI-RequestsPoster.git`

これでインストールは完了です。ComfyUIを再起動してください。<br>
※Xへの投稿機能を使う場合は必要モジュールもインストールが必要です。<br>

# Xへの投稿に必要なモジュールのインストール方法
## 概要
* Xの開発用アカウントを取得してください。
* Consumer Keysの「API Key」と「API Key Secret」の2つをメモしておいてください。
* Authentication Tokensの「Access Token」と「Access Token Secret」の2つをメモしておいてください。
* ComfyUIが利用しているPython環境に「tweepy」モジュールをインストールしてください。
## 手順　※ComfyUIがvenvを使っている場合で解説しています
1. ComfyUIが参照している仮想環境をアクティベートする<br>
![04_venvActivate](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/c02fbf7e-b480-40f2-99d5-78c2919f60a5)

2. 仮想環境に入ったら「pip install tweepy」と入力しエンターを押す<br>
![05_input_pipinstalltweepy](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/a9d6e9ce-f283-4d97-b9d1-632ed9c8653b)

完了です。

# アップデート方法
## 概要<br>
ComfyUI > custom_nodes > ComfyUI-RequestsPoster をコマンドプロンプトで開いて「git pull」してください。

## 手順<br>
1. ComfyUI > custom_nodes > ComfyUI-RequestsPoster をエクスプローラーで開き、パスをクリックする<br>
![01_ClickPass](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/506fb188-e3f9-465e-a376-ce9d86249470)

2. 「cmd」と入力しエンターを押す<br>
![02_input_cmd](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/d21da5dd-a640-463e-8202-da335f9c6a0a)

3. コマンドプロンプトが開いたら「git pull」と入力しエンターを押す<br>
![03_input_git_pull](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/484328c0-6846-48cc-b969-c9decc356db2)

完了です。<br>

# 使い方（テキストの送信：PostText）
1. AddNode > RequestsPoster > PostText でノードを追加する
2. anyにトリガーとしたいノードを繋ぐ
3. urlにリクエストを投げたいURLをコピペする　例）ディスコードのウェブフックURL
4. keyとvalueにそれぞれリクエストに含めたい文字列を入力する　例）key = content、value = 画像が出来ました
5. Queueする

# 使用例
DiscordのサーバーにWebhookを使ってメッセージを投稿させられます。

# WebhookURLの取得方法
1. 左下の「＋」を押してサーバーを追加して、作られたサーバーの歯車アイコンを押す<br>
![02_addServer](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/a9c2b8d9-0a21-4eeb-9409-6c5a82a3b9d4)

2. 連携サービス　→　ウェブフック　と押す<br>
![03_addWebhook](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/89b17581-51ab-404a-9d94-2117c4ec25d6)

3. ウェブフックを開き「URLをコピー」をクリック<br>
![04_copyURL](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/c8ebcd28-7464-4ebb-ab0c-8d0f7b16a443)

4. AddNode > RequestsPoster > PostRequest　でノードを追加しanyにトリガーとしたいノードを繋ぎ、URLにウェブフックのURLをコピペする<br>
![01_node](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/36fb87ad-21a6-49ca-b145-d2e7f583b322)

5. 画像を生成すると、ディスコードにメッセージが投稿されます<br>
![05_HelloWorld](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/058960e2-0983-4b8c-be35-ca5bd2aa7cb0)

# 使い方（Xへの投稿：PostImage2X）
1. AddNode > RequestsPoster > PostImage2X でノードを追加する
2. imageに投稿したいimageを繋ぐ
3. textに投稿したい文章を書く
4. Xの開発者ポータルで生成した各キーをコピペする　※取得方法は下部に説明を書いておきます<br>
例：<br>
`【consumer_key】j0Ja1Ab2Bc3Cd4De5Ef6Fg7Gh`<br>
`【consumer_secret】a1Ab2Bc3Cd4De5Ef6Fg7Gh8Hi9Ij0Ja1Ab2Bc3Cd4De5Ef6Fg7`<br>
`【access_token】1234567890123456789-Abcdea1Ab2Bc3Cd4De5Ef6Fg7Gh8Hi`<br>
`【access_token_secret】a1Ab2Bc3Cd4De5Ef6Fg7Gh8Hi9Ij0Ja1Ab2Bc3Cd4De5E`<br>

5. Queueする<br>

# XのKeyの生成方法
1. Xの開発者用ページを開く<br>
https://developer.twitter.com

2. Freeプランの「Get Started」を押す<br>
![01_developer_getstarted](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/0278ea17-1b38-4478-9002-d45043d7c954)

3. 「Sign up for Free Account」を押す<br>
![02_SignUpForFreeAccount](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/02f0c4a4-fd2d-4f57-bad3-94bb0a2eab4d)

4. XのデータとAPIを何に使うかを250文字以上で入力し、規約同意的な3カ所にチェックを入れて「Submit」を押す<br>
![03_PolicyAccept](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/ed49b76f-7ad0-434c-b879-8bd90d7b8ada)<br>
例文：<br>
`ComfyUIでのPythonによるtweepyライブラリを用いたTwitterへの各種投稿に使います。`<br>
`投稿する内容のパターンは下記の通りです。`<br>
`・１行テキスト`<br>
`・複数行テキスト`<br>
`・１行テキストおよび単一画像`<br>
`・１行テキストおよび複数画像`<br>
`・複数行テキストおよび単一画像`<br>
`・複数行テキストおよび複数画像`<br>
`・一般ユーザーでも閲覧可能な属性付け`<br>
`・SuperFollowersのみが閲覧可能な属性付け`<br>
`・他SNSへ誘導可能なハイパーリンク`<br>
`またXのAPI制限範囲内に収まるように日時を指定した予約投稿も実施します。`<br>
4. ダッシュボードを開き左側の「Project & Apps」内のプロジェクトを選択し、右側の「Set up」を押す<br>
![04_ClickSetUp](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/42e9d94f-eb58-4128-bb0d-5de066b07881)
5. 各項目をチェックおよび入力し画面下部の「Save」を押す<br>
![05_ClickSave](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/c674f4d2-76e8-4a2b-84eb-1ea186df7f6d)
* App permissionsは「Read and write」にチェックを入れる
* Type of Appは「Web App. Automated App or Bot」にチェックを入れる
* App Infoの「Callback URI」と「WebSite URL」には自分のXアカウントのURLを入れる

6. Yesを押す<br>
![05_ClickYes](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/5748bcb8-5dbe-4104-817d-61ec67d9bf4e)
7. ダッシュボードに戻り、プロジェクトを開き「Keys and tokens」のタブを開き、各キーの計4個をジェネレートしメモする<br>
![06_ClickRegenerateAndGenerate](https://github.com/aburahamu/ComfyUI-RequestsPoster/assets/166828042/2ef9f4b0-3eaa-4e31-91e8-7a02614d7804)
* Consumer Keysのボタン「Regenerate」を押すとキーが2個表示される
* Access Token and Secretのボタン「Generate」を押すとキーが2個表示される

完了です。
