# 初回導入

```aidl
$ npm install
```

# コンパイル

```aidl
$ sh ./zip.sh
```

- resize.zipが生成される

# AWSコンソールで、Lambdaコンソールにresize.zipを設定

- Lambda関数の作成 > Blank Function > トリガーにS3を指定
　- 「バケット」に、変換元のバケット指定
　- 「イベントタイプ」に、COPY or PUT 指定
　- 「プレフィックス」に、変換元の対象フォルダ指定
　- 「トリガーを有効化」　にチェック

- 名前入力

- ランタイム Node.js 6.10

- コードエントリ　タイプ
  - .ZIPファイルをアップロード > resize.zipを指定

- ロール
  - IAMで、S3にFullAccessできる権限のロールを設定
  
