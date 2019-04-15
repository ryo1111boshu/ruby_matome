# Rubyまとめ
- プロを目指す人のためのRuby入門
- パーフェクトRuby

## Rubyの正規表現まとめ

- \d は「半角数字1文字」を表す

- 　{n,m} は「直前の文字が n 文字以上、m 文字以下」であることを表す

- {n} は「直前の文字がちょうど n 文字」であることを表す

- [AB] は「AまたはBが1文字」であることを表す

- [a-z] と [-az] ではハイフンの意味が異なる([a-z]はa-zの文字、[-az]は-(ハイフン)、またはa、またはz、という意味)

## protetedとprivateの違い
protected: 同じクラスやサブクラス内のメソッドの中だけで呼び出せる。レシーバをつけても呼び出せる。

private  : 同じクラスやサブクラス内のメソッドの中だけで呼び出せる。レシーバをつけると呼び出せない。


## selectメソッド
各要素に対してブロックを評価し、その戻り値が真の要素を集めた配列を返す。

```rb
numbers = [1,2,3,4,5,6]
even_numbers = numbers.select(&:even?)
even_numbers
#=> [2,4,6]
```

## rejectメソッド
各要素に対してブロックを評価し、その戻り値が真の要素を**除外した**配列を返す。

```rb
numbers = [1,2,3,4,5,6]
non_multiples_three = numbers.reject{ |n| n % 3 == 0 }
non_multiples_three
#=> [1,2,4,5]
```

## findメソッド
ブロックの戻り値が真になった最初の要素を返す。

```rb
numbers = [1,2,3,4,5,6]
even_number = numbers.find(&:even?)
even_number #=> 2
```

## injectメソッド

```rb
numbers = [1,2,3,4]
sum = numbers.inject(0){ |result, n| result + n }
sum #=> 10
```

## 範囲

最初の値..最後の値（最後の値を含む）
最初の値...最後の値（最後の値を含まない）

## rjustメソッド（P105）

```rb
# rjustメソッドで右寄せ。第一引数に桁数（デフォルトは空白）。第二引数は空白以外の文字列

'0'.rjust(5) #=> '    0'
'0'.rjust(5, '0') #=> '00000'
'0'.rjust(5, '_') #=> '____0'
```

## hexメソッド(P110)
16進数の文字列を10進数の整数に変換するメソッド

```rb
'00'.hex #=> 0
'ff'.hex #=> 255
'2a'.hex #=> 42

# 10進数を16進数に変換する時

0.to_s(16) #=> "0"
255.to_s(16) #=> "ff"
```

## scanメソッド(P112)
正規表現にマッチした文字列を配列にして返す

```rb
'#12abcd'.scan(/\w\w/) 
#=> ["12","ab","cd"]
```

## 配列の要素の取得方法

```rb
配列[位置、　取得する長さ]

a = [1, 2, 3, 4, 5]
a[1, 3]
#=> [2,3,4]

# values_atを使うと取得したい要素の添え字を複数指定できる
a = [1, 2, 3, 4, 5]
a.values_at(0,2,4)
#=> [1,3,5]

# 2つめから３要素分を100で置き換える
a = [1, 2, 3, 4, 5]
a[1,3] = 100
a #=> [1,100,5]

# 指定した要素を削除する
a = [1, 2, 3, 4, 5]
# 値が２である要素を削除する（削除した要素が戻り値となる）
a.delete(2) #=> 2
a           #=> [1,3,1,3]
```

## 多重代入で残りの全要素を配列として受け取る

```rb
e, *f = 100, 200, 300
e #=> 100
f #=> [200, 300]
```

## １つの配列を複数の引数として展開する

```rb
a = []
b = [2, 3]
a.push(1) #=> [1]
# 配列を*付きで追加する（a.push(2,3）と同じ）
a.push(*b) #=> [1,2,3]
```

## メソッドの可変長引数
可変長引数は配列として受け取る

```rb
def greeting(*names)
  "#{names.join('と')}、こんにちは
end

greeting('田中さん')                       #=> "田中さん、こんにちは！"
greeting('田中さん', '鈴木さん')            #=> "田中さんと鈴木さん、こんにちは！"
greeting('田中さん', '鈴木さん', '佐藤さん') #=> "田中さんと鈴木さんと佐藤さん、こんにちは！"
```

## *で配列同士を非破壊的に連結する

```rb
a = [1,2,3]
[-1, 0, *a, 4, 5] #=> [-1, 0, 1, 2, 3, 4, 5]
```

## %記法で文字列の配列を作る

```rb
%w(apple melon orange) #=> ["apple", "melon", "orange"]
```

## charsメソッド
文字列中の文字を配列の要素に分解するメソッド

```rb
"Ruby".chars #=> ["R", "u", "b", "y"]
```

## ミュータブルなオブジェクト&イミュータブルなオブジェクト

#### ミュータブルなオブジェクト: 変更可能なオブジェクト。そのため、破壊的変更が適用できる。

- 文字列(Stringクラス)

#### イミュータブルなオブジェクト: 変更不可能なオブジェクト。そのため、破壊的な変更は適用できない。

- 数値（IntegerクラスやFloatクラス）
- シンボル（Symbolクラス）
- true/false（TrueClassクラスとFalseClassクラス）
- nil（NilClassクラス）

## 繰り返し処理の際、添え字も取得したいときに使うメソッドは？

A. with_indexメソッド

```rb
fruits = ['apple', 'orange', 'melon']
# mapとして処理しつつ、添え字も受け取る
fruits.map.with_index { |fruit, i| "#{i}: #{fruit}" }
#=> ["0: apple", "1: orange", "2: melon"]

fruits = ['apple', 'orange', 'melon']
# 名前に"a"を含み、なおかつ添え字が奇数である要素を削除する
fruits.delete_if.with_index { |fruit, i| fruit.include?('a') && i.odd? }
#=> ["apple", "melon"]
```

## 配列がブロック引数に引き渡される場合

```rb
# ブロック引数を２つにしてやれば、配列の各値を取得できる
dimensions = [
  # [縦, 横]
  [10, 20],
  [30, 40],
  [50, 60],
]
# 面積の計算結果を格納する配列
areas = []
# 配列の要素分だけブロック引数を用意すると、各要素の値が別々の変数に格納される
dimensions.each do |length, width|
  areas << length * width
end
# areas = dimensions.map{ |length, width| length * width }
areas #=> [200, 1200, 3000]

# with_indexメソッドを使う際は注意。
dimensions = [
  [10, 20],
  [30, 40],
  [50, 60],
]
# ブロック引数を()で囲んで、配列の要素を別々の引数として受け取る
dimensions.each_with_index do |(length, width), i|
  puts "length: #{length}, width: #{width}, i: #{i}"
end
#=> length: 10, width: 20, i: 0
#   length: 30, width: 40, i: 1
#   length: 50, width: 60, i: 2
```

## 単純にn回処理を繰り返したい場合のメソッドは？
A. timesメソッド

```rb
sum = 0
# 処理を5回繰り返す。nには0, 1, 2, 3, 4が入る
5.times { |n| sum += n }
sum #=> 10
```

# nからmまで数値を１つずつ増やしたい/減らしたい場合のメソッドは？
A. uptoメソッド、downtoメソッド

```rb
# n.upto(m){ 処理 }

a = []
10.upto(14) { |n| a << n }
a #=> [10, 11, 12, 13, 14]


# n.downto(m){ 処理 }

a = []
14.downto(10) { |n| a << n }
a #=> [14, 13, 12, 11, 10]
```

## nからmまで数値をx個ずつ増やしたい場合のメソッドは?
A. stepメソッド

```rb
# n.step(m, x){ 処理 }

a = []
1.step(10, 2) { |n| a << n }
a #=> [1, 3, 5, 7, 9]

a = []
10.step(1, -2) { |n| a << n }
a #=> [10, 8, 6, 4, 2]
```

## while文で最低1回実行したいときは、どうするか?
A. 処理内容をbeginとend囲む

```rb
# begin ... endで囲むとどんな条件でも最低1回は実行される
begin
  a << 1
end while false
a #=> [1]
```

## 繰り返し処理で一気に外側のループまで脱出したい場合は？

breakメソッドは内側のループしか脱出できないが、throwメソッドとcatchメソッドを使えば一気に外側へ脱出できる。ここでのthrow,catchメソッドは例外処理とは関係がない。

```rb
fruits = ['apple', 'melon', 'orange']
numbers = [1, 2, 3]
catch :done do
  fruits.shuffle.each do |fruit|
    numbers.shuffle.each do |n|
      puts "#{fruit}, #{n}"
      if fruit == 'orange' && n == 3
        # すべての繰り返し処理を脱出する
        throw :done
      end
    end
  end
end
#=> melon,  2
#   melon,  1
#   melon,  3
#   orange, 1
#   orange, 3


# throwメソッドに第二引数を渡すとcatchメソッドの戻り値となる
ret =
  catch :done do
    throw :done
  end
ret #=> nil

ret =
  catch :done do
    throw :done, 123
  end
ret #=> 123

```

## 繰り返し処理で使うbreakとreturnの違いとは？
breackメソッドは繰り返し処理からの脱出だが、returnメソッドはメソッドからの脱出。

## 四捨五入などの方法で整数に変換するには？

floorメソッド
https://www.javadrive.jp/ruby/numeric_class/index3.html
　

---
4/13

- 文字列をまとめてfrozenしたい場合は`frozen_string_literal`を使う

- 文字列がマッチするか知りたい場合は`===`を使える

```ruby
/[0-9]/ === 'もじ' #=> false
```

- scanメソッドはマッチした文字列を配列で返す


