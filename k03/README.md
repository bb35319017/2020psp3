# 課題3 レポート
35319017 河辺桜


## 課題  

以下の2つのアルゴリズムで文字列を検索するプログラムを作成する。  
- 力ずく法
- BM法

1. 使用するデータ  
以下のデータを使用する。ただし、検索対象文字列、検索する文字列は変更しても良い。  
    - StrOriginal: 検索対象データ
    - StrKey: 検索する文字列

2. 必須問題：実装する関数  
本課題では、以下の関数を実装する。C言語の標準ライブラリは使用しないこと。  
    (1) ForceSearch: 力ずく法で文字列を検索する。  
    [入力]  
    - char text[]: 検索対象文字列  
    - char key[]: 検索する文字列  

    [出力]  
    - return値：検索する文字列が出現した場所(ポインタ)。ただし、検索する文字列が見つからない場合はNULL。  

    (2) BMSearch: BM法で文字列を検索する。  
    [入力]  
    - char text[]: 検索対象文字列  
    - char key[]: 検索する文字列  
 
    [出力]  
    - return値：検索する文字列が出現した場所(ポインタ)。ただし、検索する文字列が見つからない場合はNULL。  

3. 補助関数  
なし

## ソースコードの説明

l.13-17:変数を定義する

l.16-17:strlenで文字列の長さを調べる

l.19:探索対象‐検索する文字列より小さい間繰り返す

l.20:検索する文字列より小さい間繰り返す

l.23-33:比較し、検索する文字列があればfindを1としてl.23のforを抜ける

l.36:findが1だったらl.19のforを抜ける

l.41-48:検索する文字列があったらその場所を返し、なければNULLを返す

l.55-61:変数を定義する

l.63-70:ずらし量テーブルを作る

l.71-74:indexをkey_len-1としkey_lenより小さい間繰り返し、index_bfにindexを代入

l.75:key_indexが0以上の間繰り返す

l.77-84:検索する文字列の1部があったら1文字前も確認して一致していたらfindを1として、l.75のforを抜ける

l.86-95:なければ、ずらし量テーブルにより次の開始位置を決め、indexが開始位置より前にあったら1つずらす

l.97:findが1だったらl.19のforを抜ける

l.102-109:検索する文字列があったらその場所を返し、なければNULLを返す

## 出力結果

```
Force Search. Find keyword at:wind in my hair.
BM Search. Find keyword at: wind in my hair.
```

## 修正履歴

[#20201210]

l.104:キーの先頭文字をリターンするようにした

