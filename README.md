# アプリの仕様
- ランキングの閲覧(誰でも)
- ランキングの追加(パスワード認証)
- ランキングの削除(パスワード認証)
- ランキング形式でスコア順+時間が早い順にソート
- データはpostgresqlによるDB保存
- github pagesで公開しているので、APIでログイン(パスワードが正しければ認証キーの取得)

# DBの構造
DB -> main  
--> id(text)  
--> username(text)  
--> score(int8)  
--> time(timestamp with time zone)  

- id
  - ランダムな文字列の64桁程度で管理しています
- username
  - 入力されたクエリに依存します
- score
  - 今回の出し物はストラックアウトなのでn/9点です
- time
  - 同じスコアの場合の条件になります
