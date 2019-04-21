<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Ruby学習まとめ](#ruby%E5%AD%A6%E7%BF%92%E3%81%BE%E3%81%A8%E3%82%81)
  - [パーフェクトRubyまとめ](#%E3%83%91%E3%83%BC%E3%83%95%E3%82%A7%E3%82%AF%E3%83%88ruby%E3%81%BE%E3%81%A8%E3%82%81)
    - [変数と定数](#%E5%A4%89%E6%95%B0%E3%81%A8%E5%AE%9A%E6%95%B0)
      - [ローカル変数](#%E3%83%AD%E3%83%BC%E3%82%AB%E3%83%AB%E5%A4%89%E6%95%B0)
      - [定数](#%E5%AE%9A%E6%95%B0)
      - [ヒアドキュメント](#%E3%83%92%E3%82%A2%E3%83%89%E3%82%AD%E3%83%A5%E3%83%A1%E3%83%B3%E3%83%88)
      - [%q記法](#%25q%E8%A8%98%E6%B3%95)
      - [%w記法](#%25w%E8%A8%98%E6%B3%95)
      - [%i記法](#%25i%E8%A8%98%E6%B3%95)
      - [正規表現の`===`や`=~`](#%E6%AD%A3%E8%A6%8F%E8%A1%A8%E7%8F%BE%E3%81%AE%E3%82%84)
      - [手続きオブジェクト（Proc）](#%E6%89%8B%E7%B6%9A%E3%81%8D%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88proc)
    - [制御構造・メソッド・組み込み関数](#%E5%88%B6%E5%BE%A1%E6%A7%8B%E9%80%A0%E3%83%BB%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%83%BB%E7%B5%84%E3%81%BF%E8%BE%BC%E3%81%BF%E9%96%A2%E6%95%B0)
      - [演算子の優先順位](#%E6%BC%94%E7%AE%97%E5%AD%90%E3%81%AE%E5%84%AA%E5%85%88%E9%A0%86%E4%BD%8D)
      - [case式](#case%E5%BC%8F)
      - [ハッシュをforでループさせる](#%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E3%82%92for%E3%81%A7%E3%83%AB%E3%83%BC%E3%83%97%E3%81%95%E3%81%9B%E3%82%8B)
      - [`$0`と$PROGRAM_NAME](#0%E3%81%A8program_name)
      - [`__FILE__`](#__file__)
      - [例外を制御](#%E4%BE%8B%E5%A4%96%E3%82%92%E5%88%B6%E5%BE%A1)
      - [メソッドやクラス・モジュール定義で例外を捕捉する](#%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%84%E3%82%AF%E3%83%A9%E3%82%B9%E3%83%BB%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB%E5%AE%9A%E7%BE%A9%E3%81%A7%E4%BE%8B%E5%A4%96%E3%82%92%E6%8D%95%E6%8D%89%E3%81%99%E3%82%8B)
      - [例外が発生した場合にリトライする](#%E4%BE%8B%E5%A4%96%E3%81%8C%E7%99%BA%E7%94%9F%E3%81%97%E3%81%9F%E5%A0%B4%E5%90%88%E3%81%AB%E3%83%AA%E3%83%88%E3%83%A9%E3%82%A4%E3%81%99%E3%82%8B)
      - [任意の処理からの脱出](#%E4%BB%BB%E6%84%8F%E3%81%AE%E5%87%A6%E7%90%86%E3%81%8B%E3%82%89%E3%81%AE%E8%84%B1%E5%87%BA)
      - [メソッド呼び出しとローカル変数](#%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97%E3%81%A8%E3%83%AD%E3%83%BC%E3%82%AB%E3%83%AB%E5%A4%89%E6%95%B0)
      - [メソッドと定数](#%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%A8%E5%AE%9A%E6%95%B0)
      - [可変長引数](#%E5%8F%AF%E5%A4%89%E9%95%B7%E5%BC%95%E6%95%B0)
      - [配列の展開](#%E9%85%8D%E5%88%97%E3%81%AE%E5%B1%95%E9%96%8B)
      - [ブロック](#%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF)
          - [yeild](#yeild)
      - [仮引数としてブロックを受け取る](#%E4%BB%AE%E5%BC%95%E6%95%B0%E3%81%A8%E3%81%97%E3%81%A6%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E3%82%92%E5%8F%97%E3%81%91%E5%8F%96%E3%82%8B)
      - [オブジェクトをブロックとして渡す](#%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%82%92%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E3%81%A8%E3%81%97%E3%81%A6%E6%B8%A1%E3%81%99)
      - [includeとextend](#include%E3%81%A8extend)
      - [undefでメソッド定義の取り消しを行うことができる](#undef%E3%81%A7%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E5%AE%9A%E7%BE%A9%E3%81%AE%E5%8F%96%E3%82%8A%E6%B6%88%E3%81%97%E3%82%92%E8%A1%8C%E3%81%86%E3%81%93%E3%81%A8%E3%81%8C%E3%81%A7%E3%81%8D%E3%82%8B)
      - [aliasでメソッドに別名をつける](#alias%E3%81%A7%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AB%E5%88%A5%E5%90%8D%E3%82%92%E3%81%A4%E3%81%91%E3%82%8B)
      - [「1」を「0001」に変換したいとき、sprintfを使う](#1%E3%82%920001%E3%81%AB%E5%A4%89%E6%8F%9B%E3%81%97%E3%81%9F%E3%81%84%E3%81%A8%E3%81%8Dsprintf%E3%82%92%E4%BD%BF%E3%81%86)
      - [外部コマンドを実行する](#%E5%A4%96%E9%83%A8%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89%E3%82%92%E5%AE%9F%E8%A1%8C%E3%81%99%E3%82%8B)
          - [外部コマンドを実行してその結果（標準出力）を文字列で取得するには「\`」（バッククォート）を使うらしい](#%E5%A4%96%E9%83%A8%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89%E3%82%92%E5%AE%9F%E8%A1%8C%E3%81%97%E3%81%A6%E3%81%9D%E3%81%AE%E7%B5%90%E6%9E%9C%E6%A8%99%E6%BA%96%E5%87%BA%E5%8A%9B%E3%82%92%E6%96%87%E5%AD%97%E5%88%97%E3%81%A7%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF%5C%E3%83%90%E3%83%83%E3%82%AF%E3%82%AF%E3%82%A9%E3%83%BC%E3%83%88%E3%82%92%E4%BD%BF%E3%81%86%E3%82%89%E3%81%97%E3%81%84)
          - [外部コマンドの出力を必要とせず、真偽判定ができればいい場合は#systemメソッドを使う](#%E5%A4%96%E9%83%A8%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89%E3%81%AE%E5%87%BA%E5%8A%9B%E3%82%92%E5%BF%85%E8%A6%81%E3%81%A8%E3%81%9B%E3%81%9A%E7%9C%9F%E5%81%BD%E5%88%A4%E5%AE%9A%E3%81%8C%E3%81%A7%E3%81%8D%E3%82%8C%E3%81%B0%E3%81%84%E3%81%84%E5%A0%B4%E5%90%88%E3%81%AFsystem%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%92%E4%BD%BF%E3%81%86)
          - [他にもexec、spawn、などがある](#%E4%BB%96%E3%81%AB%E3%82%82execspawn%E3%81%AA%E3%81%A9%E3%81%8C%E3%81%82%E3%82%8B)
      - [外部ファイルを読み込むrequire](#%E5%A4%96%E9%83%A8%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%82%92%E8%AA%AD%E3%81%BF%E8%BE%BC%E3%82%80require)
      - [外部ファイルを読み込むload](#%E5%A4%96%E9%83%A8%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%82%92%E8%AA%AD%E3%81%BF%E8%BE%BC%E3%82%80load)
      - [`$:`と`$LOAD_PATH`の役割](#%E3%81%A8load_path%E3%81%AE%E5%BD%B9%E5%89%B2)
      - [割り込みハンドラを定義する](#%E5%89%B2%E3%82%8A%E8%BE%BC%E3%81%BF%E3%83%8F%E3%83%B3%E3%83%89%E3%83%A9%E3%82%92%E5%AE%9A%E7%BE%A9%E3%81%99%E3%82%8B)
  - [プロを目指す人のためのRuby入門まとめ](#%E3%83%97%E3%83%AD%E3%82%92%E7%9B%AE%E6%8C%87%E3%81%99%E4%BA%BA%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AEruby%E5%85%A5%E9%96%80%E3%81%BE%E3%81%A8%E3%82%81)
    - [_を使った大きい数字の記述法](#_%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E5%A4%A7%E3%81%8D%E3%81%84%E6%95%B0%E5%AD%97%E3%81%AE%E8%A8%98%E8%BF%B0%E6%B3%95)
    - [割り算](#%E5%89%B2%E3%82%8A%E7%AE%97)
    - [Rubyでの偽判定](#ruby%E3%81%A7%E3%81%AE%E5%81%BD%E5%88%A4%E5%AE%9A)
    - [%記法で文字列を作る](#%25%E8%A8%98%E6%B3%95%E3%81%A7%E6%96%87%E5%AD%97%E5%88%97%E3%82%92%E4%BD%9C%E3%82%8B)
    - [フォーマットを指定して文字列を作成する](#%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%83%E3%83%88%E3%82%92%E6%8C%87%E5%AE%9A%E3%81%97%E3%81%A6%E6%96%87%E5%AD%97%E5%88%97%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B)
    - [10進数以外の整数リテラル](#10%E9%80%B2%E6%95%B0%E4%BB%A5%E5%A4%96%E3%81%AE%E6%95%B4%E6%95%B0%E3%83%AA%E3%83%86%E3%83%A9%E3%83%AB)
    - [ビット演算](#%E3%83%93%E3%83%83%E3%83%88%E6%BC%94%E7%AE%97)
    - [指数表現](#%E6%8C%87%E6%95%B0%E8%A1%A8%E7%8F%BE)
    - [case文](#case%E6%96%87)
    - [keysメソッドを利用して、ハッシュのキーを配列で返す](#keys%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E3%81%AE%E3%82%AD%E3%83%BC%E3%82%92%E9%85%8D%E5%88%97%E3%81%A7%E8%BF%94%E3%81%99)
    - [valuesメソッドを利用して、ハッシュの値を配列で返す](#values%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E3%81%AE%E5%80%A4%E3%82%92%E9%85%8D%E5%88%97%E3%81%A7%E8%BF%94%E3%81%99)
    - [has_key?メソッドを利用して、ハッシュの中に指定されたキーが存在するか確認する](#has_key%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E3%81%AE%E4%B8%AD%E3%81%AB%E6%8C%87%E5%AE%9A%E3%81%95%E3%82%8C%E3%81%9F%E3%82%AD%E3%83%BC%E3%81%8C%E5%AD%98%E5%9C%A8%E3%81%99%E3%82%8B%E3%81%8B%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B)
    - [**でハッシュを展開させる](#%E3%81%A7%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E3%82%92%E5%B1%95%E9%96%8B%E3%81%95%E3%81%9B%E3%82%8B)
    - [**引数を利用して、任意のキーワードを受け付ける](#%E5%BC%95%E6%95%B0%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E4%BB%BB%E6%84%8F%E3%81%AE%E3%82%AD%E3%83%BC%E3%83%AF%E3%83%BC%E3%83%89%E3%82%92%E5%8F%97%E3%81%91%E4%BB%98%E3%81%91%E3%82%8B)
    - [to_aメソッドを利用して、ハッシュを配列に変換する](#to_a%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E3%82%92%E9%85%8D%E5%88%97%E3%81%AB%E5%A4%89%E6%8F%9B%E3%81%99%E3%82%8B)
    - [to_hメソッドを利用して、配列をハッシュに変換する](#to_h%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E9%85%8D%E5%88%97%E3%82%92%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E3%81%AB%E5%A4%89%E6%8F%9B%E3%81%99%E3%82%8B)
    - [%記法でシンポルやシンボルの配列を作成する](#%25%E8%A8%98%E6%B3%95%E3%81%A7%E3%82%B7%E3%83%B3%E3%83%9D%E3%83%AB%E3%82%84%E3%82%B7%E3%83%B3%E3%83%9C%E3%83%AB%E3%81%AE%E9%85%8D%E5%88%97%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B)
    - [&.演算子](#%E6%BC%94%E7%AE%97%E5%AD%90)
    - [||=演算子](#%E6%BC%94%E7%AE%97%E5%AD%90)
    - [!!を利用して、真偽値を確実に返す](#%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E7%9C%9F%E5%81%BD%E5%80%A4%E3%82%92%E7%A2%BA%E5%AE%9F%E3%81%AB%E8%BF%94%E3%81%99)
    - [正規表現において=~を利用して、真偽判定](#%E6%AD%A3%E8%A6%8F%E8%A1%A8%E7%8F%BE%E3%81%AB%E3%81%8A%E3%81%84%E3%81%A6%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E7%9C%9F%E5%81%BD%E5%88%A4%E5%AE%9A)
    - [matchメソッド](#match%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89)
    - [キャプチャの結果に名前をつける](#%E3%82%AD%E3%83%A3%E3%83%97%E3%83%81%E3%83%A3%E3%81%AE%E7%B5%90%E6%9E%9C%E3%81%AB%E5%90%8D%E5%89%8D%E3%82%92%E3%81%A4%E3%81%91%E3%82%8B)
    - [scanメソッドを利用して、正規表現にマッチした部分を配列にして返す](#scan%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E6%AD%A3%E8%A6%8F%E8%A1%A8%E7%8F%BE%E3%81%AB%E3%83%9E%E3%83%83%E3%83%81%E3%81%97%E3%81%9F%E9%83%A8%E5%88%86%E3%82%92%E9%85%8D%E5%88%97%E3%81%AB%E3%81%97%E3%81%A6%E8%BF%94%E3%81%99)
    - [[]やsliceを利用して、文字列から正規表現にマッチした部分を抜き出す](#%E3%82%84slice%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E6%96%87%E5%AD%97%E5%88%97%E3%81%8B%E3%82%89%E6%AD%A3%E8%A6%8F%E8%A1%A8%E7%8F%BE%E3%81%AB%E3%83%9E%E3%83%83%E3%83%81%E3%81%97%E3%81%9F%E9%83%A8%E5%88%86%E3%82%92%E6%8A%9C%E3%81%8D%E5%87%BA%E3%81%99)
    - [splitを利用してマッチした文字列を区切り文字で分解し、配列にする](#split%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E3%83%9E%E3%83%83%E3%83%81%E3%81%97%E3%81%9F%E6%96%87%E5%AD%97%E5%88%97%E3%82%92%E5%8C%BA%E5%88%87%E3%82%8A%E6%96%87%E5%AD%97%E3%81%A7%E5%88%86%E8%A7%A3%E3%81%97%E9%85%8D%E5%88%97%E3%81%AB%E3%81%99%E3%82%8B)
    - [gsubメソッド](#gsub%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89)
    - [クラスメソッド](#%E3%82%AF%E3%83%A9%E3%82%B9%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89)
    - [name=のようなセッタメソッドを呼び出したい場合は、必ずselfをつける必要がある。](#name%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E3%82%BB%E3%83%83%E3%82%BF%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%92%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97%E3%81%9F%E3%81%84%E5%A0%B4%E5%90%88%E3%81%AF%E5%BF%85%E3%81%9Aself%E3%82%92%E3%81%A4%E3%81%91%E3%82%8B%E5%BF%85%E8%A6%81%E3%81%8C%E3%81%82%E3%82%8B)
    - [インスタンスメソッドからクラスメソッドを呼び出す場合](#%E3%82%A4%E3%83%B3%E3%82%B9%E3%82%BF%E3%83%B3%E3%82%B9%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%8B%E3%82%89%E3%82%AF%E3%83%A9%E3%82%B9%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%92%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%99%E5%A0%B4%E5%90%88)
    - [privateメソッド](#private%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89)
    - [クラスメソッドをprivateにしたい場合](#%E3%82%AF%E3%83%A9%E3%82%B9%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%92private%E3%81%AB%E3%81%97%E3%81%9F%E3%81%84%E5%A0%B4%E5%90%88)
    - [後からメソッドの公開レベルを変更する場合](#%E5%BE%8C%E3%81%8B%E3%82%89%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E5%85%AC%E9%96%8B%E3%83%AC%E3%83%99%E3%83%AB%E3%82%92%E5%A4%89%E6%9B%B4%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88)
    - [protectedメソッド](#protected%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89)
    - [定数の値を後から変更しないためにfreezeメソッドを使う](#%E5%AE%9A%E6%95%B0%E3%81%AE%E5%80%A4%E3%82%92%E5%BE%8C%E3%81%8B%E3%82%89%E5%A4%89%E6%9B%B4%E3%81%97%E3%81%AA%E3%81%84%E3%81%9F%E3%82%81%E3%81%ABfreeze%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%92%E4%BD%BF%E3%81%86)
    - [エイリアスメソッドの定義](#%E3%82%A8%E3%82%A4%E3%83%AA%E3%82%A2%E3%82%B9%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E5%AE%9A%E7%BE%A9)
    - [オープンクラスとモンキーパッチ](#%E3%82%AA%E3%83%BC%E3%83%97%E3%83%B3%E3%82%AF%E3%83%A9%E3%82%B9%E3%81%A8%E3%83%A2%E3%83%B3%E3%82%AD%E3%83%BC%E3%83%91%E3%83%83%E3%83%81)
    - [特異メソッド](#%E7%89%B9%E7%95%B0%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89)
    - [メソッドの有無を調べるrespond_to?](#%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E6%9C%89%E7%84%A1%E3%82%92%E8%AA%BF%E3%81%B9%E3%82%8Brespond_to)
    - [あるクラスに特定のモジュールがincludeされているか確認する方法](#%E3%81%82%E3%82%8B%E3%82%AF%E3%83%A9%E3%82%B9%E3%81%AB%E7%89%B9%E5%AE%9A%E3%81%AE%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB%E3%81%8Cinclude%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E3%81%8B%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95)
    - [オブジェクトのクラスを調べる](#%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%81%AE%E3%82%AF%E3%83%A9%E3%82%B9%E3%82%92%E8%AA%BF%E3%81%B9%E3%82%8B)
    - [Enumerableモジュール](#enumerable%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB)
    - [Comparableモジュール](#comparable%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB)
    - [Kernelモジュール](#kernel%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB)
    - [ネストなしで名前付きのクラスを定義する](#%E3%83%8D%E3%82%B9%E3%83%88%E3%81%AA%E3%81%97%E3%81%A7%E5%90%8D%E5%89%8D%E4%BB%98%E3%81%8D%E3%81%AE%E3%82%AF%E3%83%A9%E3%82%B9%E3%82%92%E5%AE%9A%E7%BE%A9%E3%81%99%E3%82%8B)
    - [名前空間内からトップレベルのクラスを指定する](#%E5%90%8D%E5%89%8D%E7%A9%BA%E9%96%93%E5%86%85%E3%81%8B%E3%82%89%E3%83%88%E3%83%83%E3%83%97%E3%83%AC%E3%83%99%E3%83%AB%E3%81%AE%E3%82%AF%E3%83%A9%E3%82%B9%E3%82%92%E6%8C%87%E5%AE%9A%E3%81%99%E3%82%8B)
    - [モジュール単体でそのメソッドを呼び出したいとき](#%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB%E5%8D%98%E4%BD%93%E3%81%A7%E3%81%9D%E3%81%AE%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%82%92%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97%E3%81%9F%E3%81%84%E3%81%A8%E3%81%8D)
    - [モジュール関数](#%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB%E9%96%A2%E6%95%B0)
    - [円周率の導き方](#%E5%86%86%E5%91%A8%E7%8E%87%E3%81%AE%E5%B0%8E%E3%81%8D%E6%96%B9)
    - [クラスを使ってシングルトンパターンを実装する場合](#%E3%82%AF%E3%83%A9%E3%82%B9%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%A6%E3%82%B7%E3%83%B3%E3%82%B0%E3%83%AB%E3%83%88%E3%83%B3%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88)
    - [prepend](#prepend)
    - [有効範囲を限定するrefinements](#%E6%9C%89%E5%8A%B9%E7%AF%84%E5%9B%B2%E3%82%92%E9%99%90%E5%AE%9A%E3%81%99%E3%82%8Brefinements)
  - [その他](#%E3%81%9D%E3%81%AE%E4%BB%96)
    - [Rubyの正規表現まとめ](#ruby%E3%81%AE%E6%AD%A3%E8%A6%8F%E8%A1%A8%E7%8F%BE%E3%81%BE%E3%81%A8%E3%82%81)
    - [protetedとprivateの違い](#proteted%E3%81%A8private%E3%81%AE%E9%81%95%E3%81%84)
    - [selectメソッド](#select%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89)
    - [rejectメソッド](#reject%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89)
    - [findメソッド](#find%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89)
    - [injectメソッド](#inject%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89)
    - [範囲](#%E7%AF%84%E5%9B%B2)
    - [rjustメソッド（P105）](#rjust%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89p105)
    - [hexメソッド(P110)](#hex%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89p110)
    - [scanメソッド(P112)](#scan%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89p112)
    - [配列の要素の取得方法](#%E9%85%8D%E5%88%97%E3%81%AE%E8%A6%81%E7%B4%A0%E3%81%AE%E5%8F%96%E5%BE%97%E6%96%B9%E6%B3%95)
    - [多重代入で残りの全要素を配列として受け取る](#%E5%A4%9A%E9%87%8D%E4%BB%A3%E5%85%A5%E3%81%A7%E6%AE%8B%E3%82%8A%E3%81%AE%E5%85%A8%E8%A6%81%E7%B4%A0%E3%82%92%E9%85%8D%E5%88%97%E3%81%A8%E3%81%97%E3%81%A6%E5%8F%97%E3%81%91%E5%8F%96%E3%82%8B)
    - [１つの配列を複数の引数として展開する](#%EF%BC%91%E3%81%A4%E3%81%AE%E9%85%8D%E5%88%97%E3%82%92%E8%A4%87%E6%95%B0%E3%81%AE%E5%BC%95%E6%95%B0%E3%81%A8%E3%81%97%E3%81%A6%E5%B1%95%E9%96%8B%E3%81%99%E3%82%8B)
    - [メソッドの可変長引数](#%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E5%8F%AF%E5%A4%89%E9%95%B7%E5%BC%95%E6%95%B0)
    - [*で配列同士を非破壊的に連結する](#%E3%81%A7%E9%85%8D%E5%88%97%E5%90%8C%E5%A3%AB%E3%82%92%E9%9D%9E%E7%A0%B4%E5%A3%8A%E7%9A%84%E3%81%AB%E9%80%A3%E7%B5%90%E3%81%99%E3%82%8B)
    - [%記法で文字列の配列を作る](#%25%E8%A8%98%E6%B3%95%E3%81%A7%E6%96%87%E5%AD%97%E5%88%97%E3%81%AE%E9%85%8D%E5%88%97%E3%82%92%E4%BD%9C%E3%82%8B)
    - [charsメソッド](#chars%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89)
    - [ミュータブルなオブジェクト&イミュータブルなオブジェクト](#%E3%83%9F%E3%83%A5%E3%83%BC%E3%82%BF%E3%83%96%E3%83%AB%E3%81%AA%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%82%A4%E3%83%9F%E3%83%A5%E3%83%BC%E3%82%BF%E3%83%96%E3%83%AB%E3%81%AA%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88)
          - [ミュータブルなオブジェクト: 変更可能なオブジェクト。そのため、破壊的変更が適用できる。](#%E3%83%9F%E3%83%A5%E3%83%BC%E3%82%BF%E3%83%96%E3%83%AB%E3%81%AA%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88-%E5%A4%89%E6%9B%B4%E5%8F%AF%E8%83%BD%E3%81%AA%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%81%9D%E3%81%AE%E3%81%9F%E3%82%81%E7%A0%B4%E5%A3%8A%E7%9A%84%E5%A4%89%E6%9B%B4%E3%81%8C%E9%81%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B)
          - [イミュータブルなオブジェクト: 変更不可能なオブジェクト。そのため、破壊的な変更は適用できない。](#%E3%82%A4%E3%83%9F%E3%83%A5%E3%83%BC%E3%82%BF%E3%83%96%E3%83%AB%E3%81%AA%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88-%E5%A4%89%E6%9B%B4%E4%B8%8D%E5%8F%AF%E8%83%BD%E3%81%AA%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%81%9D%E3%81%AE%E3%81%9F%E3%82%81%E7%A0%B4%E5%A3%8A%E7%9A%84%E3%81%AA%E5%A4%89%E6%9B%B4%E3%81%AF%E9%81%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%81%AA%E3%81%84)
    - [繰り返し処理の際、添え字も取得したいときに使うメソッドは？](#%E7%B9%B0%E3%82%8A%E8%BF%94%E3%81%97%E5%87%A6%E7%90%86%E3%81%AE%E9%9A%9B%E6%B7%BB%E3%81%88%E5%AD%97%E3%82%82%E5%8F%96%E5%BE%97%E3%81%97%E3%81%9F%E3%81%84%E3%81%A8%E3%81%8D%E3%81%AB%E4%BD%BF%E3%81%86%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AF)
    - [配列がブロック引数に引き渡される場合](#%E9%85%8D%E5%88%97%E3%81%8C%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E5%BC%95%E6%95%B0%E3%81%AB%E5%BC%95%E3%81%8D%E6%B8%A1%E3%81%95%E3%82%8C%E3%82%8B%E5%A0%B4%E5%90%88)
    - [単純にn回処理を繰り返したい場合のメソッドは？](#%E5%8D%98%E7%B4%94%E3%81%ABn%E5%9B%9E%E5%87%A6%E7%90%86%E3%82%92%E7%B9%B0%E3%82%8A%E8%BF%94%E3%81%97%E3%81%9F%E3%81%84%E5%A0%B4%E5%90%88%E3%81%AE%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AF)
- [nからmまで数値を１つずつ増やしたい/減らしたい場合のメソッドは？](#n%E3%81%8B%E3%82%89m%E3%81%BE%E3%81%A7%E6%95%B0%E5%80%A4%E3%82%92%EF%BC%91%E3%81%A4%E3%81%9A%E3%81%A4%E5%A2%97%E3%82%84%E3%81%97%E3%81%9F%E3%81%84%E6%B8%9B%E3%82%89%E3%81%97%E3%81%9F%E3%81%84%E5%A0%B4%E5%90%88%E3%81%AE%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AF)
    - [nからmまで数値をx個ずつ増やしたい場合のメソッドは?](#n%E3%81%8B%E3%82%89m%E3%81%BE%E3%81%A7%E6%95%B0%E5%80%A4%E3%82%92x%E5%80%8B%E3%81%9A%E3%81%A4%E5%A2%97%E3%82%84%E3%81%97%E3%81%9F%E3%81%84%E5%A0%B4%E5%90%88%E3%81%AE%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AF)
    - [while文で最低1回実行したいときは、どうするか?](#while%E6%96%87%E3%81%A7%E6%9C%80%E4%BD%8E1%E5%9B%9E%E5%AE%9F%E8%A1%8C%E3%81%97%E3%81%9F%E3%81%84%E3%81%A8%E3%81%8D%E3%81%AF%E3%81%A9%E3%81%86%E3%81%99%E3%82%8B%E3%81%8B)
    - [繰り返し処理で一気に外側のループまで脱出したい場合は？](#%E7%B9%B0%E3%82%8A%E8%BF%94%E3%81%97%E5%87%A6%E7%90%86%E3%81%A7%E4%B8%80%E6%B0%97%E3%81%AB%E5%A4%96%E5%81%B4%E3%81%AE%E3%83%AB%E3%83%BC%E3%83%97%E3%81%BE%E3%81%A7%E8%84%B1%E5%87%BA%E3%81%97%E3%81%9F%E3%81%84%E5%A0%B4%E5%90%88%E3%81%AF)
    - [繰り返し処理で使うbreakとreturnの違いとは？](#%E7%B9%B0%E3%82%8A%E8%BF%94%E3%81%97%E5%87%A6%E7%90%86%E3%81%A7%E4%BD%BF%E3%81%86break%E3%81%A8return%E3%81%AE%E9%81%95%E3%81%84%E3%81%A8%E3%81%AF)
    - [四捨五入などの方法で整数に変換するには？](#%E5%9B%9B%E6%8D%A8%E4%BA%94%E5%85%A5%E3%81%AA%E3%81%A9%E3%81%AE%E6%96%B9%E6%B3%95%E3%81%A7%E6%95%B4%E6%95%B0%E3%81%AB%E5%A4%89%E6%8F%9B%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Ruby学習まとめ
- プロを目指す人のためのRuby入門
- パーフェクトRuby

## [パーフェクトRuby](https://www.amazon.co.jp/%E6%94%B9%E8%A8%822%E7%89%88-%E3%83%91%E3%83%BC%E3%83%95%E3%82%A7%E3%82%AF%E3%83%88Ruby-Ruby%E3%82%B5%E3%83%9D%E3%83%BC%E3%82%BF%E3%83%BC%E3%82%BA/dp/4774189774/ref=tmm_other_meta_binding_swatch_0?_encoding=UTF8&qid=&sr=)まとめ


### 変数と定数

#### ローカル変数
- メソッドの外で定義されたローカル変数をメソッド内で使うことはできない
- ブロックの外で定義されたローカル変数はブロックの中で使える。

#### 定数
- メソッドの中で定数を定義することはできない

#### ヒアドキュメント
```rb
str = << EOS
１行目
２行目
EOS

# 「~」をつけると内容をインデントできる
str = <<~EOS
  １行目
  ２行目
EOS

# ヒアドキュメントの開始の識別子をシングルクォートで囲むと式展開やバックスラッシュ記法を無効にできる
```

#### %q記法
```rb
# 式展開とバックスラッシュ記法が無効
%q(It's #{weather})

# 式展開とバックスラッシュ記法が有効
%(It's #{weather})
%Q(It's #{weather})
```

#### %w記法
```rb
%w(Alice Bob Carol)
#=> ["Alice", "Bob", "Carol"]

# 大文字にすると式展開やバックスラッシュ記法を有効にできる
# 要素が空白を含む場合はバックスラッシュでエスケープする
```

#### %i記法
```rb
%i(Alice Bob Carol)
#=> [:Alice, :Bob, :Carol]

# 大文字にすると式展開やバックスラッシュ記法を有効にできる
# 要素が空白を含む場合はバックスラッシュでエスケープする
```

#### 正規表現の`===`や`=~`
- `===`は文字列が正規表現にマッチするかを真偽値で返す
- `=~`は最初にマッチした位置を整数で返す
```rb
pattern = /[0-9]+/

pattern === 'HAL 9000'
#=> true

pattern =~ 'HAL 9000'
#=> 4
```

#### 手続きオブジェクト（Proc）
- `Proc.new`にオブジェクトを渡すことで手続きオブジェクトを作成できる
```rb
greeter = Proc.new{|name|
  puts "Hello, #{name}!"
}
```
- Proc#callを呼び出すと手続きが行われる
```rb
greeter.call 'Proc'
#=> "Hello, Proc!"
```
- procやlamda、「->」を使って短く記述できる
```rb
by_proc = proc {|name| puts puts "Hello, #{name}!" }
by_lamda = lamda {|name| puts "Hello, #{name}!"}
by_literal = ->(name){ puts "Hello, #{name}!" }
```

### 制御構造・メソッド・組み込み関数

#### 演算子の優先順位
```rb
高い   ::
       []
       +(単項)  !  ~
       **
       -(単項)
       *  /  %
       +  -
       << >>
       &
       |  ^
       > >=  < <=
       <=> ==  === !=  =~  !~
       &&
       ||
       ..  ...
       ?:(条件演算子)
       =(+=, -= ... )
       not
低い   and or
```

#### case式
- 条件式が複数ある場合は、elsif節を複数記述しても良いが、比較対象が1つである場合はcase式を使う
- when説の値とcase式の値は`===`で比較される
- 下記の例では`/ruby/ === stone`のような比較が行われる。
- `===`は正規表現が文字列にマッチすると真を返すので、マッチしたwhen説が実行される
```rb
stone = 'ruby'

case stone
when /ruby/
  puts '7月'
when /peridot|sardonyx/
  puts '8月'
else
  puts 'よくわかりません'
end
```

#### ハッシュをforでループさせる
```rb
for val in {a: 1, b: 2}
  puts val[0] # "a"や"b"などのキーを表示
  puts val[1] # 1や2などの要素を表示
end
```
```rb
for key, val in { a: 1, b: 2 }
  puts key
  puts val
end
```

#### `$0`と$PROGRAM_NAME
- 実行中のRubyスクリプト名

#### `__FILE__`
- 現在実行中のソースのファイル名

#### 例外を制御
- `raise`は第一引数に例外クラス、第二引数に例外メッセージ
```rb
raise StandardError, 'error!' # StandardError: error!
```
- 例外を捕捉するには`begin`と`rescue`
```rb
begin
  do_process  # 例外が発生する可能性のある何らかの処理
rescue => e
  puts "Error occured (#{e.class})"
end
```
- 式の後ろにrescueを記述すると、その式を実行した時に発生した例外を制御できる。
```rb
# ZeroDivisionErrorが発生する式
1 / 0 rescue false
#=> false
```
- ensureは、例外の有無にかかわらず、最後に必ず実行したい処理はensure節に記述する
```rb
begin
  file = File.open('whatever.txt')

  do_process file # 例外が発生する可能性のある処理
rescue
  puts '何かが起きました'
ensure
  file.close if file
end
```
- elseは、例外が発生しない場合だけ行う処理を記述できる
```rb
begin
  File.open('whatever.txt')
rescue SystemCallError
  puts 'ファイルを開く途中で何かが起きました'
else
  puts '無事にファイルが開けました'
end
```

#### メソッドやクラス・モジュール定義で例外を捕捉する
```rb
def meth
  # 何らかの処理
rescue
  # メソッド呼び出し時に例外が発生した場合の処理
else
  # メソッド呼び出し時に例外が発生しなかった場合の処理
ensure
  # 例外の有無にかかわらず実行される処理
end
```

#### 例外が発生した場合にリトライする
- rescue節の中でretryを呼び出すと、begin節やメソッド本体の初めから処理をやり直す。
```rb
begin
  failed ||= 0
  puts 'trying...'

  process! # 例外が発生するかもしれない処理
rescue
  failed += 1

  retry if failed < 5 # begin節の最初から再度実行される
end
```

#### 任意の処理からの脱出
- catchに渡したブロックの中でthrowを呼び出すと、catchの呼び出し元に戻ることができる。catchとthrowの引数にシンボルを指定すると、throwは対応するcatchに戻る
```rb
catch :outer do
  catch :middle do
    catch :inner do
      throw :middle # :middleのブロックを中断する
      puts 'この行は実行されない'
    end
    puts 'この行も実行されない'
  end
  puts 'この行は実行される'
end
```
- throwの第二引数に渡された値はcatchの戻り値として受け取る。第二引数がなければ、catchはnilを返す。
```rb
catch(:foo){
  throw :foo, 'returned value'
}
#=> 'returned value'
```

#### メソッド呼び出しとローカル変数
- レシーバーと括弧、引数のないメソッドの呼び出しは、同じ名前のローカル変数と区別がつかないため、そのような場合は括弧を明示する。
```rb
sweet = 'honey'

def sweet
  'salt'
end

# ローカル変数へのアクセスになる
sweet
#=> 'honey'

# メソッドを呼び出すには明示的に括弧をつける
sweet() #=> 'salt'
```

#### メソッドと定数
- メソッドは大文字で命名しても間違いではないが、呼び出すときは括弧をつけること。レシーバー、引数、括弧なしで呼び出すと、定数とみなされる。
```rb
def Hello
  puts 'hello'
end

Hello # エラー

Hello() #=> hello
```

#### 可変長引数
- メソッドの定義で仮引数の頭に`*`をつけると、そのメソッドは任意の数の引数を配列として受け取れるようになる。
```rb
def greet(name, *messages)
  messages.each do |message|
    puts "#{message}, #{name}"
  end
end

greet 'Ruby', 'Hello', 'こんにちは'
#=> Hello, Ruby
#=> こんにちは, Ruby
```
- `*`は単に引数を無視したい場合も使う
```rb
def greet(name, *)
  puts "Hello, #{name}"
end

greet 'Ruby', 'こんにちは', 'foo'
#=> Hello, Ruby
```

#### 配列の展開
- メソッドの呼び出しで実引数の頭に`*`をつけると、1つの配列を複数の引数として渡せる
```rb
def greet_twice(name, first_message, second_message)
  puts "#{first_message}, #{name}"
  puts "#{second_message}, #{name}"
end

greetings = %w(Hello Hola)

greet_twice 'Ruby', *greetings
#=> Hello, Ruby
#=> Hola, Ruby
```

#### ブロック

###### yeild
- メソッドの中でyeildを呼び出すと、受け取ったブロックを実行する
```rb
def block_sample
  puts 'stand up'
  yeild
  puts 'sit down'
end

block_sample do
  puts 'walk'
end
#=> stand up
#=> walk
#=> sit down
```
- block_sampleメソッドの中でyeildが呼び出されると、メソッド呼び出し時に渡したブロックが実行される。
- yeildを呼び出しているメソッドをブロックなしで呼び出すと、`LocalJumpError`という例外が発生する
- メソッドにブロックが与えられたかどうかは`block_given?`メソッドを用いる。
- `block_given?`は実行中のメソッドがブロック付きで呼び出されているときに真を返す
```rb
def block_sample
  puts 'stand up'

  yeild if block_given?

  puts 'sit down'
end

# ブロックを渡さない
block_sample
#=> stand up
#=> sit down

# ブロックを渡す
block_sample do
  puts 'walk'
end
#=> stand up
#=> walk
#=> sit down
```

#### 仮引数としてブロックを受け取る
```rb
def block_sample(&block)
  puts 'stand up'

  block.call if block

  puts 'sit down'
end

block_sample do
  puts 'walk'
end
#=> "stand up"
#=> "walk"
#=> "sit down"
```
- 仮引数blockには、ブロックがProcオブジェクトとして渡され、Proc#callメソッドを呼び出すことで、yeildと同じようにブロックを呼び出せる。

#### オブジェクトをブロックとして渡す
- メソッドの呼び出しで引数の頭に`&`をつけると、その引数をブロックとして渡せる
```rb
people = %w(Alice Bob Charlie)
block = Proc.new{|name| puts name}

people.each &block
#=> Alice
#=> Bob
#=> Charlie
```
```rb
# p1とp2は同じ意味
p1 = Proc.new {|val| val.upcase}
p2 = :upcase.to_proc

p1.call('hi') #=> HI
p2.call('hi') #=> HI

```

#### includeとextend
- includeはモジュールのメソッドをインスタンスメソッドとして取り込む
- extendはモジュールのメソッドを特異メソッドとして取り込む

#### undefでメソッド定義の取り消しを行うことができる
```rb
def greet
  puts 'hola'
end

greet #=> hola
puts 'hi' #=> hi

undef greet, puts

greet #=> error
puts 'hi' #=> error
```

#### aliasでメソッドに別名をつける
```rb
# putsをgreetという名前で呼び出せるようになる
alias greet puts

greet 'hi' #=> hi

# aliasした後に元のメソッドの定義を取り消した場合でも、別名のメソッドまで取り消されることはない
undef puts

greet 'ho' #=> ho
```

#### 「1」を「0001」に変換したいとき、sprintfを使う
```rb
sprintf('%04d', 1) #=> 0001
'%04d' % 1 #=> 0001
```

#### 外部コマンドを実行する

###### 外部コマンドを実行してその結果（標準出力）を文字列で取得するには「\`」（バッククォート）を使うらしい
- よくわからん　p106

###### 外部コマンドの出力を必要とせず、真偽判定ができればいい場合は#systemメソッドを使う
- 同上

###### 他にもexec、spawn、などがある

#### 外部ファイルを読み込むrequire
外部ファイルを読み込む`require`は`$LOAD_PATH`に含まれているディレクトリを探してファイルを読み込む。
よって、`$LOAD_PATH`に含まれていないディレクトリを読み込むことはできない。
その場合は`$LOAD_PATH`にディレクトリを追加するか`require_relative`で直接指定する。
`require`は実行中の「ディレクトリ」を起点としてパスを設定するのに対し、`require_relative`は実行中の「ファイル」を起点としてパスを設定する

#### 外部ファイルを読み込むload
`require`と`require_relative`が一度読み込んだファイルは二度と読み込まないのに対して、`load`は何度も読み込む。さらに拡張子を省略できない点も異なる
例： `load __dir__ + '/config.rb'`

#### `$:`と`$LOAD_PATH`の役割
`require`や`load`で用いる時の探索パスが配列で格納されている
この配列に格納することで`require`でファイルを読み込む先に相対パスで記述できる
例： `$LOAD_PATH << File.dirname(__FILE__)`

#### 割り込みハンドラを定義する
- シグナルとは：　プロセスの正常処理に割り込む処理のこと（例えば処理が終了した時に「 Bye 」 と表示させるなど）

trapを使うとシグナルに対応するハンドラ（処理）を登録できる
trapの第一引数にシグナルをシンボルで指定し、第二引数にはハンドラをブロックで指定する


## [プロを目指す人のためのRuby入門](https://www.amazon.co.jp/dp/B077Q8BXHC/ref=dp-kindle-redirect?_encoding=UTF8&btkr=1)まとめ

### _を使った大きい数字の記述法
```rb
1_000_000_000
#=> 1000000000
```

### 割り算
- 整数同士の割り算は整数になる
- 小数点以下の値が必要な場合は、計算式に少数を含める
```rb
n = 1
n.to_f # to_fメソッドで整数から少数に変更
#=> 1.0
n.to_f / 2
#=> 0.5
```

### Rubyでの偽判定
- falseまたはnilであれば偽
- それ以外は全て真

### %記法で文字列を作る
```rb
puts %q{He said, "Don't speak."}
#=> He said, "Don't speak."
```

### フォーマットを指定して文字列を作成する
```rb
'%0.3f' % 1.2
#=> 1.200

'%0.3f + %0.3f' % [1.2, 0.48]
#=> "1.200 + 0.480"
```

### 10進数以外の整数リテラル

### ビット演算

### 指数表現

### case文
```rb
case 対象のオブジェクトや式
when 値1
　# 値１に一致する場合の処理
when 値2
  # 値2に一致する場合の処理
else
  # どれにも一致しない処理
end
```

```rb
country = 'italy'

message = 
  case country
  when 'japan'
    'こんにちは'
  when 'us'
    'Hello'
  when 'italy'
    'ciao'
  else
    '???'
  end
```

### keysメソッドを利用して、ハッシュのキーを配列で返す
```rb
currencies = { japan: 'yen', us: 'dollar', india: 'rupee' }
currencies.keys
#=> [:japan, :us, :india]
```

### valuesメソッドを利用して、ハッシュの値を配列で返す
```rb
currencies = { japan: 'yen', us: 'dollar', india: 'rupee' }
currencies.values
#=> ["yen", "dollar", "rupee"]
```

### has_key?メソッドを利用して、ハッシュの中に指定されたキーが存在するか確認する
```rb
currencies = { japan: 'yen', us: 'dollar', india: 'rupee' }
currencies.has_key? #=> true
currencies.has_key? #=> false
```

### **でハッシュを展開させる
- `**`をハッシュの前につけるとハッシュリテラル内で他のハッシュのキーと値を展開することができる

```rb
h = { us: 'dollar', india: 'rupee' }
{japan: 'yen', **h }
#=> {:japan=>"yen", :us=>"dollar", :india=>"rupee"}

# mergeメソッドを使っても同じ結果が得られる
{ japan: 'yen'}.merge(h)
#=> {:japan=>"yen", :us=>"dollar", :india=>"rupee"}
```

### **引数を利用して、任意のキーワードを受け付ける
- `**`をつけた引数にはキーワード引数で指定されていないキーワードがハッシュとして格納される

```rb
def buy_burger(menu, drink: true, potato: true, **others)
  # othersはハッシュとして渡される
  puts others
end
buy_burger('fish', drink: true, potato: false, salad: true, chicken: false)
#=> {:salad=>true, :chicken=>false}
```

### to_aメソッドを利用して、ハッシュを配列に変換する
```rb
currencies = { japan: 'yen', us: 'dollar', india: 'rupee' }
currencies.to_a
#=> [[:japan, "yen"], [:us, "dollar"], [:india, "rupee"]]
```

### to_hメソッドを利用して、配列をハッシュに変換する
```rb
array = [[:japan, "yen"], [:us, "dollar"], [:india, "rupee"]]
array.to_h
#=> {:japan=>"yen", :us=>"dollar", :india=>"rupee"}
```

### %記法でシンポルやシンボルの配列を作成する
```rb
%s(ruby is fun)
#=> :"ruby is fun"

%i(apple orange melon)
#=> [:apple, :orange, :melon]
```

### &.演算子
- &.演算子を使ってメソッドを呼び出すと、メソッドを呼び出されたオブジェクトがnilでない場合はその結果を、nilだった場合はnilを返す。

```rb
# nil以外のオブジェクトであれば、a.upcaseと書いた場合と同じ結果になる
a = 'foo'
a&.upcase
#=> "FOO"

# nilであればnilを返す
a = nil
a&.upcase
#=> nil
```

### ||=演算子
- 左辺が「nilまたはfalse」であれば、右辺を代入する

```rb
limit = nil
limit ||= 10
limit
#=> 10

limit = 20
limit ||= 10
limit
#=> 20
```

### !!を利用して、真偽値を確実に返す
```rb
def user_exists?
  # データベース等からユーザーを探す（なければnil）
  user = find_user
  if user
    # userが見つかったのでtrue
    true
  else
    # userが見つからないのでfalse
    false
  end
end

# ----------------------------------------

def user_exists?
  !!find_user
end
# ----------------------------------------

!!true  #=> true
!!1     #=> true
!!false #=> false
!!nil   #=> false

```

### 正規表現において=~を利用して、真偽判定
- `=~`を使うと、正規表現がマッチした場合は文字列中のマッチした位置が返り、マッチしなかった場合はnilが返る。この性質を利用してif文の条件分岐ができる

```rb
if '123-4567' =~ /\d{3}-\d{4}/
  puts 'マッチしました'
else
  puts 'マッチしませんでした'
end
```

### matchメソッド
`正規表現.match(文字列)`
- 文字列に正規表現がマッチすると、matchdataオブジェクトが返り、マッチしない場合はnilが返る

```rb
text = '私の誕生日は1977年7月17日です。'
m = /(\d+)年(\d+)月(\d+)日/.match(text)
# マッチした部分全体を取得する
m[0] #=> "1977年7月17日"

# キャプチャの1番目を取得する
m[1] #=> "1977"
```

### キャプチャの結果に名前をつける
- `(?<name>)`をすることでキャプチャに名前をつけることができる
- 左辺に正規表現リテラルを、右辺に文字列を置いて`=~`演算子を使うと、キャプチャの名前がそのままローカルの変数に割り当てられる

```rb
text = '私の誕生日は1977年7月17日です。'
m = /(?<year>\d+)年(?<month>\d+)月(?<day>\d+)日/.match(text)
m[:year] #=>'1977'
m[:month] #=> '7'
m[:day] #=> '17'

text = '私の誕生日は1977年7月17日です。'
# キャプチャの名前がそのままローカル変数に割り当てられる
if /(?<year>\d+)年(?<month>\d+)月(?<day>\d+)日/ =~ text
  puts "#{year}#{month}#{day}"
end
```

### scanメソッドを利用して、正規表現にマッチした部分を配列にして返す
- 引数で渡した正規表現にマッチする部分を配列で返す。

```rb
'123 456 789'.scan(/\d+/)
#=> ['123', '456', '789']

'1977年7月17日 2016年12月31日'.scan(/(\d+)年(\d+)月(\d+)日/)
#=> [["1977", "7", "17"], ["2016", "12", "31"]]
```

### []やsliceを利用して、文字列から正規表現にマッチした部分を抜き出す
```rb
text = '郵便番号は123-4567です'
text[/\d{3}-\d{4}/]
#=> "123-4567"

text = '誕生日は1977年7月17日です'
text[/(?<year>\d+)年(?<month>\d+)月(?<day>\d+)日/, :day]
#=> "17"

text = '郵便番号は123-4567です'
text.slice(/\d{3}-\d{4}/)
#=> "123-4567"
```

### splitを利用してマッチした文字列を区切り文字で分解し、配列にする
```rb
text = '123,456-789'

text.split(',')
#=> ["123", "456-789"]

# 正規表現を使ってカンマまたはハイフンを区切り文字に指定する
text.split(/,|-/)
#=> ["123", "456", "789"]
```

### gsubメソッド
- 第一引数の正規表現にマッチした文字列を第二引数の文字列で置き換える

```rb
text = '123,456-789'
text.gsub(/,|-/, ':')
#=> "123:456:789"

text = '誕生日は1977年7月17日です'
text.gsub(/(\d+)年(\d+)月(\d+)日/, '\1-\2-\3')
#=> "誕生日は1977-7-17です"

text = '誕生日は1977年7月17日です'
text.gsub(
  /(?<year>\d+)年(?<month>\d+)月(?<day>\d+)日/,
  '\k<year>-\k<month>-\k<day>'
)
#=> "誕生日は1977-7-17です"
```

### クラスメソッド
```rb
class クラス名
  def self.クラスメソッド
  
  end
end
```
```rb
class クラス名
  class << self
    def クラスメソッド

    end
  end
end
```

### name=のようなセッタメソッドを呼び出したい場合は、必ずselfをつける必要がある。

### インスタンスメソッドからクラスメソッドを呼び出す場合
```rb
class Sample

  def self.format_price

  end

  def example
    Sample.format_price
  end
  # または
  def example_2
    self.class.format_price
  end
end
```

### privateメソッド
- privateメソッドは「レシーバを指定して呼び出すことができないメソッド」
- 他の言語では「privateメソッドはそのクラスの内部のみ呼び出せる」という仕様になっていることがあるが、Rubyの場合は「privateメソッドはそのクラスだけでなく、サブクラスでも呼び出せる」

### クラスメソッドをprivateにしたい場合
```rb
class User
  class << self
    private

      def hello
      end
  end
end
```

### 後からメソッドの公開レベルを変更する場合
- **privateキーワードは実際にはメソッドなので、引数を渡すことができる。**
- **既存のメソッド名をprivateキーワードに渡すと、そのメソッドがprivateメソッドになる**

```rb
class User
  def foo
  end

  def bar
  end

  # fooメソッドとbarメソッドをpublicからprivateに変更する
  private :foo, :bar
end
```

### protectedメソッド
- **protectedメソッドはそのメソッドを定義したクラス自身と、そのサブクラスのインスタンスメソッドからレシーバ付きで呼び出せる**
- 使い所: **外部には公開したくないが、同じクラスやサブクラスの中であればレシーバ付きで呼び出せるようにしたい、というときにprotectedメソッドを使う**

### 定数の値を後から変更しないためにfreezeメソッドを使う
```rb
# mapメソッドで各要素をfreezeし、最後にmapメソッドの戻り値をfreezeする
SOME_NAMES = %w(Foo Bar Baz).map(&:freeze).freeze
```

### エイリアスメソッドの定義
`alias 新しい名前 元の名前`

```rb
class User
  def hello
    'Hello'
  end

  # helloメソッドのエイリアスメソッドとしてgreetingを定義する
  alias greeting hello
end
```

### オープンクラスとモンキーパッチ
定義済みのクラスそのものにメソッドを追加したり、メソッドの定義を上書きしたりすることができる。

```rb
# オープンクラスの例: 既存のクラスに新しいメソッドを追加する
class String
  # 文字列をランダムにシャッフルする
  def shuffle
    chars.shuffle.join
  end
end
```
```rb
# モンキーパッチの例: 既存のメソッドを上書きする例

# 以下のUserクラスは外部ライブラリで定義されている設定
class User
  def initialize(name)
    @name = name
  end

  def hello
    "Hello, #{@name}!"
  end
end

# モンキーパッチを当てるためにUserクラスを再オープンする
class User
  # 既存のhelloメソッドはhello_originalとして呼び出せるようにしておく
  alias hello_original hello

  # helloメソッドにモンキーパッチを当てる
  # (もともと実装されていたhelloメソッドも再利用する)
  def hello
    "#{hello_original}じゃなくて、#{@name}さん、こんにちは"
  end
end
```

### 特異メソッド
- 特定のオブジェクトにだけ紐づくメソッドを**特異メソッド**と呼ぶ
- クラスメソッドは特異メソッドの一種

```rb
alice = 'I am alice'

# 方法1
def alice.shuffle
  chars.shuffle.join
end

# 方法2
class << alice
  def shuffle
    charf.shuffle.join
  end
end
```

### メソッドの有無を調べるrespond_to?
- オブジェクトに対して特定のメソッドが呼び出し可能か確認する場合に使う

```rb
s = 'Alice'

# Stringクラスはsplitメソッドを持つ
s.respond_to?(:split) #=> true

# nameメソッドは持たない
s.respond_to?(:name) #=> false
```
```rb
# 使用例
def display_name(object)
  if object.respond_to?(:name)
    # nameメソッドが呼び出せる場合
    puts "Name is << object.name >>"
  else
    # nameメソッドが呼び出せない場合
    puts 'No name.'
  end
end
```

### あるクラスに特定のモジュールがincludeされているか確認する方法

```rb
# ProductクラスにLoggableモジュールがincludeされているか確認する

# include?メソッドを使う
Product.include?(Loggable)
#=> true

# indcluded_modulesメソッドを使う
Product.included_modules
#=> [Loggable, Karnel]
```

### オブジェクトのクラスを調べる
- 継承関係(is-a)にあるかどうかも併せて確認したいときは`is_a?`メソッドを使う

```rb
user = User.new

user.class
#=> User

# userはUserのインスタンスか？
user.instance_of?(User)
#=> true

# userはStringのインスタンスか？
user.instance_of?(String)
#=> false

# instance_of?はクラスが全く同じでないとtrueにならない
user.instance_of(Object)
#=> false

# is_a?はis-a関係にあればtrueになる
user.is_a?(User)
#=> true
user.is_a?(Object)
#=> true
```

### Enumerableモジュール
- これをincludeすると、mapなどのメソッドが使える
- include先でeachメソッドが実装されていることが条件

### Comparableモジュール
- これをincludeすると、<などの演算子が使える
- include先で<=>演算子が実装されていることが条件

### Kernelモジュール
- これをincludeすると、putsなどのメソッドが使える

### ネストなしで名前付きのクラスを定義する
- すでに他でモジュールが定義されている場合は以下のように定義できる

```rb
module Baseball
end

class  Baseball::Second
  def initialize(player, uniform_number)
    @player = player
    @uniform_number = uniform_number
  end
end
```

### 名前空間内からトップレベルのクラスを指定する

```rb
class Second
end

module Clock
 class Second
  ::Second.new
  end
end
```

### モジュール単体でそのメソッドを呼び出したいとき
- モジュールの特異メソッドを定義する

```rb
module Loggable
  def self.log(text)
    puts "[LOG]#{text}"
  end
end
```

### モジュール関数
- ミックスインとしても特異メソッドとしても使えるメソッドのことをモジュール関数と呼ぶ
- モジュール関数にするには`module_function`メソッドを使用する
- モジュール関数となったメソッドはprivateメソッドになる

```rb
module Loggable
  def log(text)
    puts "[LOG]#{text}"
  end

  # logメソッドをミックスインとしてもモジュールの特異メソッドとしても使えるようにする
  module_function :log

  Loggable.log('Hello') #=> [LOG]Hello

  class Product
    include Loggable

    def title
      # includeしたLoggableモジュールのlogメソッドを呼び出す
      log 'title is called'
      'A great movie'
    end
  end

  # ミックスインとしてlogメソッドを呼び出す
  product = Product.new
  product.title
  #=> [LOG]title is called
  #=> A great movie
end
```

### 円周率の導き方
`Math::PI`

### クラスを使ってシングルトンパターンを実装する場合
- Singletonモジュールをincludeする
- p.314 - チェリー

### prepend
- prependでモジュールをミックインすると、ミックスインしたクラスよりも先にモジュールのメソッドが呼ばれる
- prependを使えば、既存メソッドを置き換える際にaliasメソッドを定義する必要がない
- 新しいメソッド用のモジュールを作成して、ミックスイン先でprependを使えば良いから
- p.319 - チェリー
- p.320 - チェリー

### 有効範囲を限定するrefinements
- refinementsを使うと既存クラスに対する変更の有効範囲が限定できる
- `refine`メソッドでrefinementsを適用するクラスを指定し、
- 有効にしたいクラス内で`using`メソッドを使ってrefinementsを有効化する

```rb
module StringShuffle
  refine String do
    def shuffle
      chars.shuffle.join
    end
  end
end

class User
  using StringShuffle

  # Userクラス内であればshuffleメソッドは有効になり、クラスを抜けると無効になる
end

user = User.new
user.shuffle
```

## その他

### Rubyの正規表現まとめ

- \d は「半角数字1文字」を表す

- 　{n,m} は「直前の文字が n 文字以上、m 文字以下」であることを表す

- {n} は「直前の文字がちょうど n 文字」であることを表す

- [AB] は「AまたはBが1文字」であることを表す

- [a-z] と [-az] ではハイフンの意味が異なる([a-z]はa-zの文字、[-az]は-(ハイフン)、またはa、またはz、という意味)

### protetedとprivateの違い
protected: 同じクラスやサブクラス内のメソッドの中だけで呼び出せる。レシーバをつけても呼び出せる。

private  : 同じクラスやサブクラス内のメソッドの中だけで呼び出せる。レシーバをつけると呼び出せない。


### selectメソッド
各要素に対してブロックを評価し、その戻り値が真の要素を集めた配列を返す。

```rb
numbers = [1,2,3,4,5,6]
even_numbers = numbers.select(&:even?)
even_numbers
#=> [2,4,6]
```

### rejectメソッド
各要素に対してブロックを評価し、その戻り値が真の要素を**除外した**配列を返す。

```rb
numbers = [1,2,3,4,5,6]
non_multiples_three = numbers.reject{ |n| n % 3 == 0 }
non_multiples_three
#=> [1,2,4,5]
```

### findメソッド
ブロックの戻り値が真になった最初の要素を返す。

```rb
numbers = [1,2,3,4,5,6]
even_number = numbers.find(&:even?)
even_number #=> 2
```

### injectメソッド

```rb
numbers = [1,2,3,4]
sum = numbers.inject(0){ |result, n| result + n }
sum #=> 10
```

### 範囲

最初の値..最後の値（最後の値を含む）
最初の値...最後の値（最後の値を含まない）

### rjustメソッド（P105）

```rb
# rjustメソッドで右寄せ。第一引数に桁数（デフォルトは空白）。第二引数は空白以外の文字列

'0'.rjust(5) #=> '    0'
'0'.rjust(5, '0') #=> '00000'
'0'.rjust(5, '_') #=> '____0'
```

### hexメソッド(P110)
16進数の文字列を10進数の整数に変換するメソッド

```rb
'00'.hex #=> 0
'ff'.hex #=> 255
'2a'.hex #=> 42

# 10進数を16進数に変換する時

0.to_s(16) #=> "0"
255.to_s(16) #=> "ff"
```

### scanメソッド(P112)
正規表現にマッチした文字列を配列にして返す

```rb
'#12abcd'.scan(/\w\w/) 
#=> ["12","ab","cd"]
```

### 配列の要素の取得方法

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

### 多重代入で残りの全要素を配列として受け取る

```rb
e, *f = 100, 200, 300
e #=> 100
f #=> [200, 300]
```

### １つの配列を複数の引数として展開する

```rb
a = []
b = [2, 3]
a.push(1) #=> [1]
# 配列を*付きで追加する（a.push(2,3）と同じ）
a.push(*b) #=> [1,2,3]
```

### メソッドの可変長引数
可変長引数は配列として受け取る

```rb
def greeting(*names)
  "#{names.join('と')}、こんにちは
end

greeting('田中さん')                       #=> "田中さん、こんにちは！"
greeting('田中さん', '鈴木さん')            #=> "田中さんと鈴木さん、こんにちは！"
greeting('田中さん', '鈴木さん', '佐藤さん') #=> "田中さんと鈴木さんと佐藤さん、こんにちは！"
```

### *で配列同士を非破壊的に連結する

```rb
a = [1,2,3]
[-1, 0, *a, 4, 5] #=> [-1, 0, 1, 2, 3, 4, 5]
```

### %記法で文字列の配列を作る

```rb
%w(apple melon orange) #=> ["apple", "melon", "orange"]
```

### charsメソッド
文字列中の文字を配列の要素に分解するメソッド

```rb
"Ruby".chars #=> ["R", "u", "b", "y"]
```

### ミュータブルなオブジェクト&イミュータブルなオブジェクト

###### ミュータブルなオブジェクト: 変更可能なオブジェクト。そのため、破壊的変更が適用できる。

- 文字列(Stringクラス)

###### イミュータブルなオブジェクト: 変更不可能なオブジェクト。そのため、破壊的な変更は適用できない。

- 数値（IntegerクラスやFloatクラス）
- シンボル（Symbolクラス）
- true/false（TrueClassクラスとFalseClassクラス）
- nil（NilClassクラス）

### 繰り返し処理の際、添え字も取得したいときに使うメソッドは？

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

### 配列がブロック引数に引き渡される場合

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

### 単純にn回処理を繰り返したい場合のメソッドは？
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

### nからmまで数値をx個ずつ増やしたい場合のメソッドは?
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

### while文で最低1回実行したいときは、どうするか?
A. 処理内容をbeginとend囲む

```rb
# begin ... endで囲むとどんな条件でも最低1回は実行される
begin
  a << 1
end while false
a #=> [1]
```

### 繰り返し処理で一気に外側のループまで脱出したい場合は？

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

### 繰り返し処理で使うbreakとreturnの違いとは？
breackメソッドは繰り返し処理からの脱出だが、returnメソッドはメソッドからの脱出。

### 四捨五入などの方法で整数に変換するには？

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


