# ATMで「お金を引き出す」ユースケース記述

## ユースケース図
ATMで「お金を引き出す」
## 概略
銀行のATMを利用して、自分の口座からキャッシュカードで必要なお金を引き出します。

## アクター
利用者

## 事前条件
アクターが口座とキャッシュカードを持っていること。

## 事後条件
アクターの口座から指定された金額が引き出されること。
# イベントフロー
### 基本フロー
・利用者が「引き出し」を選択すると、このユースケースは開始する。

・利用者は、ATMにキャッシュカードを入れる。
・システムは、「暗証番号を入力」を画面に表示する。(E-1)

・利用者は、キャッシュカードの暗証番号を入力する。
・システムは、暗証番号を確認し、「金額を入力」を画面に表示する。

・利用者は、引き出す分の金額を入力する。

・システムは、口座の残高を確認し、お金を取り出し口に出す。(E-2)
・利用者は、取り出し口から現金とキャッシュカードを取る。

・ユースケースを終える。
### 代替フロー
E1.暗証番号を間違えた場合
   
    1. 「暗証番号が違います」と画面に表示して、再入力させる。
    
    2. 暗証番号が一致したら、処理を進める。
    
    3. 一致しない場合、処理を終了し、最初の画面に戻す。


E2. 残高が足りない場合
   
    1. システムは「残高が不足しています」と画面に表示し、再入力させる。
   
    2. 引き出し額が残高を上回っていない場合、処理を進める。
   
    3. 一致しない場合、処理を終了し、最初の画面に戻す。
### 例外フロー
# 基本シナリオ
## ユースケース名　現金の引き出し
 1. シナリオ1: 引き出しに成功した場合
 2. 利用者は現金引き出しを選択する
 3. 利用者はキャッシュカードをATMに挿入する
 4. 利用者は暗証番号4桁を入力する
 5. 利用者は引き出す金額を入力する
 6. ATMは現金の引き出しを実行する
 7. 利用者は、引き出された現金とカードを受け取る
 8. ATMは「終了する」を実行する