# 使い方

git clone serverless-janken

npm install

sls dynamodb install

sls dynamodb start

sls offline

curl 'http://localhost:3000/jankens?hand=rock&name=test' -X POST

curl 'http://localhost:3000/jankens' -X GET


## dynamodb-localの止め方

lsof -i:8000 -t | xargs kill


## デプロイ

sls deploy

## 削除(デプロイ取り消し)

sls remove
