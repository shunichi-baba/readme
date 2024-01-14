# アプリ名：🐻クックま🐻

BTC5 チーム名：ウィッシュ

PO：まあや、TL：shun、Amazingdev:たなちゅー、Amazingdev：ぶっちー





# How to use 
アプリの動きは写真左から右の流れ

1.ログイン画面でユーザー名、パスワードを入力しログイン  
  　ユーザー名:あなたの設定、 passwword:あなたの設定
  
2.アカウントなければ新規登録で必要事項入力しログイン  
  　ユーザー名:あなたの設定、　メールアドレス:あなたの設定、　 passwword:あなたの設定
  　大人、子供の人数、アレルギーを登録する
  
3.自動生成された献立(5日分)を確認

4.献立変更ボタンで献立を選択し、献立(5日分)を決める

５.買い物リストで献立(5日分)の食材を購入する

6.料理ボタンを押すと当日の献立の料理工程を最適化した手順で料理をサポート

<img width="100" alt="ログイン" src="https://github.com/shunichi-baba/readme/assets/119465420/f116651e-3d47-456e-b86e-fbfa4f7e9606">　
<img width="100" alt="新規登録" src="https://github.com/shunichi-baba/readme/assets/119465420/88176283-0179-4b36-957c-466399b0a209">　
<img width="100" alt="アレルギー" src="https://github.com/shunichi-baba/readme/assets/119465420/a0daa4eb-7e61-43b9-b647-be74a1b7dd2f">　
<img width="100" alt="献立" src="https://github.com/shunichi-baba/readme/assets/119465420/95151ee5-abf8-4bab-be2a-55ca0b405f0e">
<img width="100" alt="献立変更" src="https://github.com/shunichi-baba/readme/assets/119465420/a7af1f48-e023-4cbc-8a5a-8d288a6fecab">
<img width="100" alt="買い物リスト" src="https://github.com/shunichi-baba/readme/assets/119465420/37810b6b-7da8-421a-8922-25c4d456a895">
<img width="100" alt="料理工程" src="https://github.com/shunichi-baba/readme/assets/119465420/f7590e30-09b3-405d-8693-055486be3e19">


# Index

- [About](#about)
- [Development](#development)
- [How to Deploy](#how-to-Deploy)
- [Future plans](#future-plans)


# About
毎日忙しいけど愛する人を手料理で喜ばせたい...    
限られた時間で複数品の料理をマルチタスクで実施する為、自分の時間がなくゆっくり休めない。  
<br>
そんな方へ私達から解決手段を提供します。    
私たちのサービスを使用する事で、あなたとパートナーは、毎回新鮮で素晴らしい体験が出来るでしょう  


I am busy every day but want to please my loved ones with home-cooked food...    
You multitask and cook multiple dishes in a limited amount of time, leaving you no time for yourself and no time for rest. 
<br>
We offer you a solution.   
By using our service, you and your partner will have a fresh and wonderful experience every time!  

# Development
Follow this guide to set up your environment etc.
### < Database >  
This project assumes a Postgres database, naturally, this is not included in the package.json file, so must be installed separately.

Create a database called `las_damas_primero`.

### < Rakuten Developers >
このプロダクトを試用するのは楽天デベロッパーズのアプリIDが必要だよ

アプリID作成用URL　：　https://webservice.rakuten.co.jp/app/create
### <.env config >
このプロダクトは.envファイルを使用して環境変数を定義しているよ。

1.Go into the repository

`$ cd las-damas-primero/server`

2.Create .env file

`$ touch .env`
3.環境変数を記述しよう
```
DB_USER="hoge" <= Your command line username
APP_ID="fuga" <= Your command line あなたの楽天APP_ID
DB_PASSWORD="hogehoge" <= Your command line password
DB_NAME=las_damas_primero
NODE_ENV=development
```
### < Downloading and installing steps >  
1.Clone this repository

`$ git clone https://github.com/ryozo7/las-damas-primero.git`  

2.Go into the repository

`$ cd las-damas-primero/server`

3.Install dependencies

`$ npm install`

4.Create database, Run migrations and set up the database

`$ npm run migrate`

5.Run the app

`npm run dev`

# How to Deploy
レンダーの場合を説明するよ
### < 1.Renderでデータベースを作成しよう >
```
  1.ヘッダーに表示されている「New +」のボタンをクリック  
  2.「PostgreSQL」を選択  
  3.作成するデータベースの名称を記入します
  4.入力できたら「Create Database」をクリック  
  5.データベースの作成が始まり、「Status」に「Creating」と表示されます  
  6.Statusが「Available」に変わったらデータベースの作成は完了  
  7.画面を下にスクロールし「Internal Database URL」をコピー
```
### < 2.Renderでアプリを新規作成 >
```
  1.ヘッダーにある「New +」のボタンをクリック  
  2.「Web　service」をクリック  
  3.「Build and deploy from a Git repository」をチェック
  4.「Next」をクリック
  5.GitHubの「Configure account」をクリック
  6.クローンしたリポジトリを保存しているアカウントの「Configure」をクリック
  7.passwordを入力しlogin
  8.「Only select repositories」をチェックし、「Select repositories」をクリック
  9.クローンしたリポジトリーをクリック
  10.renderの画面に遷移し、クローンしたリポジトリが表示されるので、「Connect」のボタンをクリック
  11.Name欄にアプリケーションの名称を入力
  12.アプリのデプロイや起動時のコマンドを入力します
    Branch => main
    Root Directory => ./server
    Build =>　npm run build
    Start =>　　npm start
  13.画面をスクロールすると、「Advanced」という文字が書かれているのでクリック
  14.環境変数を設定します。
      key         :   value
    APP_ID        : あなたの楽天APP_ID
    DATABASE_URL  : 1.Renderでデータベースを作成しよう_7.でコピーしたURL
    NODE_ENV      : production
    VITE_NODE_ENV : production
  15.ターミナルが表示され、デプロイ作業が開始されます
    デプロイが完了すると、緑色のアイコンで「Live」(画面上部)と表示されたらデプロイ完了
    画面上部のURLからアプリに接続し、正常に動かすことができるか確認しよう！
```
# Future plans
- 絞り込み地域の細分化  
- レビュー点数しか見ていないので、レビュー数と相関した、より信頼性の高い評価ソート
- 宿泊したことあるホテルリストの追加



ライセンス情報？  







# こんにちは dev ブランチ

ルート直下で、`npm run setup`を起動すると、

- ルート直下
- client フォルダ内
- sever フォルダ内

で、

`npm install`コマンドが実行されて初期セットアップできます。

## ER 図

```mermaid
erDiagram
    foods ||--o{ categories : "categoryId"
    ingredients ||--|{ foods : "foodId"
    cook_kinds ||--o{ recipes : "kindId"
    recipes ||--o{ foods : "foodId"
    images ||--|{ foods : "pictPathId"
    ingredient_list ||--|{ ingredients : "ingredientId"
    menus ||--|{ foods : "foodId"
    images ||--o{ recipes : "imageId"
    menus ||--|{ users : "userId"
    store_area ||--o{ ingredient_list : "genreId"

    cook_kinds {
        int id PK
        string kindName "作業区分(肉を切る など)"
        int priority "優先順位"
    }


    recipes {
        int id PK
        int foodId FK
        string text "作業手順の内容"
        int imageId FK
        int kindId FK
        int workTime "目安作業時間"
        boolean canWrap "他の作業トラップできるか"
    }

    foods {
        int id PK
        string name "料理名"
        boolean isMain "主菜か"
        boolean isSide "副菜か"
        boolean isSoup "汁物か"
        boolean isRice "ご飯か"
        int categoryId FK
        boolean shrimp "えびアレルギー"
        boolean crab "かにアレルギー"
        boolean wheat "小麦アレルギー"
        boolean buckwheat_noodles "蕎麦アレルギー"
        boolean egg "卵アレルギー"
        boolean milk "乳アレルギー"
        boolean peanut "落花生アレルギー"
        string pictPathId FK "完成品メニュー画像パス"
        int totalTime "単品料理の調理時間"
    }

    ingredients {
        int id PK
        int foodId FK
        int ingredientId FK
        float quantity "数量"
        string unit "単位"
    }

    ingredient_list {
        int id PK
        string name "食材名"
        int genreId FK "買い物時の売り場区分け用ID"
    }

    store_area {
        int id PK
        string name "野菜・魚・肉など"
    }

    images {
      int id PK
      string imagePath "publicフォルダの画像名を格納"
    }

    categories {
        int id PK
        string categoryName "魚料理、鶏肉料理など"
    }

    users {
      int id PK
      string userName "ユーザー名"
      string mail "メールアドレス"
      string salt "ソルト"
      string hash "ハッシュ"
      int numOfAdults "大人の人数"
      int numOfChildren "子供の人数"
      boolean shrimp "えびアレルギー"
      boolean crab "かにアレルギー"
      boolean wheat "小麦アレルギー"
      boolean buckwheat_noodles "蕎麦アレルギー"
      boolean egg "卵アレルギー"
      boolean milk "乳アレルギー"
      boolean peanut "落花生アレルギー"
    }

    menus {
      int id PK
      int userId FK "ユーザーIDで紐付け"
      int foodId FK "料理IDで紐付け"
      date startWeek "調理週"
      date date "調理日"
      int timingFlag "朝: 0, 昼: 1, 夕: 2"
    }

```
