---
title: "SUEP開発規則"
date: 2021-10-29T21:22:16+09:00
draft: false
---

基本的には「リーダブルコード」に規則を遵守してください。下記の内容はリーダブルコードを読んだ前提での規則になっています。また、下記で定められていない部分についてはコントリビューター自身の裁量に任せます。

##  変数名・関数名の命名規則

基本的には下記の二つのwebページの内容を順守してください。
1. https://zenn.dev/kodai/articles/5fe454d436bf3e
2. https://qiita.com/yamadashy/items/e64762e407b8dd5e0247#%E5%91%BD%E5%90%8D%E8%A6%8F%E5%89%87

- フォルダ・ファイル名の命名規則
必ずキャメルケースでの命名を行うこと。
例：/Util/ReservationCard.js

## コメントについて
第三者が見た時に理解不能、または理解に著しく時間がかかるプログラムにはコメントを行ってください。ただし、コメントアウトを書く必要のないプログラムを書くようにも心掛けてください。

## 三項演算子の利用規則
三項演算子の利用は推奨しませんが、単純な分岐を示す場合のみ利用可能です。

## 連想配列の処理について
forEachを安易に利用しないように気を付けてください。パフォーマンス・可読性の観点から他のメソッド（.filter, .map, .test etc.）を利用することも考えてください。

参考：https://qiita.com/diescake/items/70d9b0cbd4e3d5cc6fce

## 外部関数ファイルの作成基準
再利用可能な関数については積極的に`Util`（現 `App`, `appFunction` ）フォルダ内で管理すること。

## 画像ファイルなどの保存フォルダ
`Assets` （現 assets）フォルダ内で管理してください。
```
Assets
　┣ FirstSemisterLects
　┣ SecondSemisterLecs
　┣ Img
```

## モジュールの利用について
基本的には`Android, iOS` 両者のプラットフォームに対応したモジュールを選択してください。6カ月以上メンテナンスされていないモジュールは原則利用禁止です。
<<<<<<< HEAD

## Gitコマンドに関する注意

### add
- 少数のファイルのみの変更を加える場合はgit add [ファイル名] として、変更したファイルのみを追加すること
- 多くのファイルの変更を行う際には git add . として、必ず漏れなく追加すること

### commit
後から振り返った際にその修正の目的・内容が理解しやすいコメントを記載してください。
（例1） git commit -m "○○.jsのリファクタ"
（例2） git commit -m "○○.js内のFlatListのパフォーマンスチューニング"
（例3） git commit -m "○○スクリーンのUI調整"


### pushおよびPull Request
プッシュ後、プルリクを出す前に必要なファイルの変更が全てプッシュされているか確認してください。特にファイル・フォルダ名の変更を行う際には小文字・大文字の変更が正確になされているかなども確かめてください。

### ブランチ
作業をする際はdevelopブランチから派生させたブランチを使用すること
