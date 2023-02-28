# mixway-API-Docs

## 初回起動時
- Node.js version 16.14以上
```
npm install
```

## local起動時
```
npm start
```

## deploy方法
masterが更新されると、環境へデプロイされます (powered by Amplify)

- [Amplify構築手順](https://mixway.esa.io/posts/130)

## APIドキュメントの追加手順
1. `/api`に各APIのymlを追加。
APIが`https://mixway.ekispert.jp/v1/json/search/course/extreme`の場合、
`/api/search/courseにextreme.yml`を追加する。

2. `/api/api.yml`のpathsに先程追加したymlを追記する。
```yml:/api/api.yml
paths:
  /v1/json/search/course/extreme:
    $ref: search/course/extreme.yml
```

## ディレクトリ構成
```
.
├── api   APIのymlを格納するディレクトリ
│   ├── course
│   ├── point
│   └── search/course
│            └── 各APIのyml
│   
│
├── docs    Tipsのmdを格納するディレクトリ
│   ├── teiki
│            ├── create-teiki.md
│   │       └── category.json   サイドバーに表示するタイトルや順番を設定
│   └── tips
│            ├── index.md
│            └── category.json 
│
├── amplify.yml   Amplifyの設定ファイル
└── docusaurus.config.js    docusaurusの設定ファイル
```