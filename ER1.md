# ER図1
## 全体
- 指摘事項
>管理人と商品やユーザー情報を関連付けさせる必要がない、よって商品及びユーザーの外部キーとして管理者IDを代入する必要はない
>管理人と商品やユーザーテーブル間で関連付けることによる恩恵が存在しないため、関連付けない方がいい。

## テーブル名
- 指摘事項
## ユーザーテーブル
- 配送先は、テーブルを独立させ複数管理できるようにするべき。
## 商品テーブル
- アーティスト、ジャンル、レーベルはそれぞれ新規テーブルを作成し、商品テーブル内には外部キーを保存する形にした方が管理しやすい。
- 曲名に関しては、別途テーブルを作成した上で1:Nという形で関連付けを行い保存するべきだ。商品と曲の間にディスクテーブルを挟み、n番目のディスクの曲と管理しやすくする必要もある。
- 商品とカートのテーブル間の関係は1:1以上にしてはいけない。カートに入れられない場合も考え、1:0以上にするべき。
- カートテーブル内に商品の情報を直接保存せず、外部キーの形で参照できるようにした方がいい。
## 決済テーブル
- カートテーブルと決済テーブルの間に関係は与えるべきではない。購入済の商品については新規のテーブルを作成し、それと決済テーブル間の関係を与えるべきだ。そのため、カートテーブル内に注文IDを与える必要もない。
- 決済テーブルと購入履歴テーブル間の関係は1:0以上ではいけない。確実に購入した商品の情報が入るので1:1以上がふさわしい。
## 購入履歴テーブル
- テーブル内に主キーが存在しない。識別できるよう購入履歴専用のIDを与えるべき。
- テーブル内にそれぞれの商品の合計金額や購入枚数を保存できる様、新規のカラムを追加する必要がある。


# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。
## 全体

## 共通

