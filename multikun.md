# 基本的なアプリの設作り方
プロジェクトファイルの構成  
### create flutterでフォルダーを生成すると、以下のファイルが作成される
# プロジェクトのフォルダ類
## .darttoolフォルダ
dart言語が自動生成するファイルを補完するとこ
## .ideaフォルダ
inteliJ IDEA開発ツールの設定情報
## buildフォルダ
ビルドして生成されるファイル類
## androidフォルダ
Androidアプリ生成に必要なファイル類
## iosフォルダ
iosアプリ生成に必要なファイル類
## linuxフォルダ
Linuxアプリ生成に必要なファイル類
## macOSフォルダ
macOSアプリ生成に必要なファイル類
## windowsフォルダ
windowsアプリ生成に必要なファイル類
## web
Webアプリ生成に必要なファイル類
## libフォルダ
ここにdartのスクリプトが保存される
## testフォルダ
ユニットテスト関連のファイル類
# プロジェクトのファイル類
## .gitgnore
Gitで使用するファイル
## .metadata
Flutterツールが利用するファイル
## .packges
利用しているパッケージ情報
## anarysis_options.yaml
Dartの分析に関するファイル
## flutter_app.iml
モジュール定義ファイル
## pubspec.lock
Pub(Dartのパケットマネージャー)が利用するファイル
## pubspec.yaml
Pubが利用するファイル
## README.md
よむべきもの
# アプリの構成について
flutterでは画面表示はウィジェットと呼ばれる部品によって作成される  
ベースとなるウィジェットの中にウィジェットを入るなど階層的に組み込んで作成する。  
このウィジェットの組み込み構造をウィジェットツリーと言う。
## アプリ実行の仕組み
一般的なプロジェクト構造では、まず
package:flutter/material.dartというパッケージを読み込む
次にmain関数である
```
void main(){
    runApp(var);
}
```
という関数を起動し実行する
## StatelessWidget
上のrunApp()関数の引数に指定しているのはMyAppというクラスのインスタンス  
このクラスはStatelessWidgetというクラスのサブクラスこのクラスはステート（状態を表す値）を持たないウィジェットベースとなるクラス  
WidgetのクラスはこのStatelessWidgetとステートを持つStatefulWidgetのいずれかを継承して作成する
StatelessWidgetにはbuildというメソッドが用意されている  
これはウィジェットが作成される際に呼び出されるもの
## MaterialApp
MaterualAppクラスは様々な設定情報を指定することができるクラスここでいろいろ必要なウィジェットを足していく。
## Scaffold
Scafflodはアプリ作成の土台となる部分を担当する部品、ここにはマテリアルデザインの基本的なデザインとレイアウトが組み込まれている。
## appBar
appBarはアプリ上部に表示されるバーを設定する値のこと
### AppBarはそのインスタンス
この下に構成要素となる 
### bodyを入れる
## StatefulWidget
SatefulWidgetというクラスは状態を扱うためのきのうを持っているクラス
論理型
##　centerによる中央揃え
この値を使うと textやボタンなどが右上からではなく中央から配置されるようになる