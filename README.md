# vue-memo

## vue-cognito1
AWS Cognito を使ったユーザー認証をvueで。  
参考：https://qiita.com/daikiojm/items/b02c19cfea6766c308ca#  

```
vue init webpack  
npm i aws-sdk --save  
npm i amazon-cognito-identity-js --save
```
いろいろ修正して、
```
npm run build
npm run start
 => localhost:8080
```

distをS3バケット投入して普通に動作した。アプリクライアントIDはbuildで暗号化されるのでデプロイしても大丈夫。

私物awsエンドポイント : http://tobi-vue-cognito-test1.s3-website-ap-northeast-1.amazonaws.com  
ユーザープール：cog2  
