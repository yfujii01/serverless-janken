# サーバーレスじゃんけんAPI

## 1.準備

git clone git@github.com:yfujii01/serverless-janken.git

npm install

## 2-1-1.dynamodb-localを使う場合

sls dynamodb install

sls dynamodb start

## 2-1-2.dynamodb-localの止め方

lsof -i:8000 -t | xargs kill

## 2-2-1.dynamodb.jarを使う場合

こちらのURLからjarファイルをダウンロード

https://docs.aws.amazon.com/ja_jp/amazondynamodb/latest/developerguide/DynamoDBLocal.html

起動

java -Djava.library.path=./DynamoDBLocal_lib -jar DynamoDBLocal.jar -sharedDb

テーブル作成

sls dynamodb migrate

seed登録

sls dynamodb seed

## 2-3-1.dockerを使う場合(slsとうまく連携できなかった..[未解決])

docker run -p 8000:8000 amazon/dynamodb-local

テーブル作成

sls dynamodb migrate

seed登録

sls dynamodb seed

## 3.起動方法

sls offline

## 4.動作確認

curl 'http://localhost:3000/jankens?hand=rock&name=test' -X POST

curl 'http://localhost:3000/jankens?hand=paper&name=test' -X POST

curl 'http://localhost:3000/jankens?hand=scissors&name=test' -X POST

curl 'http://localhost:3000/jankens' -X GET

## aws-lambdaへデプロイ

sls deploy

## aws-lambdaから削除(デプロイ取り消し)

sls remove
