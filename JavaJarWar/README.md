# 情報サイト
https://qiita.com/Qui/items/14961678ef939673f744
# Jar ファイルの作成
## Step 1 classファイルの作成
javac -sourcepath src -d classes src\sample\App.java
## Step 2 jarファイルの作成
jar cvfm sample.jar META-INF\MANIFEST.MF -C classes .
## Step 3 jarファイルの実行
java -jar sample.jar

# War ファイルの作成
## Step 1 classファイルの作成
javac -sourcepath src -classpath lib\* -d WebContent\WEB-INF\classes src\sample\SampleServlet.java
## Step 2 Warファイルの作成
jar cvf sample.war -C WebContent .
# Docker対応
## Step 1 warファイルを作成
jar cvf docker/sample.war -C WebContent .
## Step 2 Dockerビルド
docker build -t my-javaapp .
## Step 3 Dockerを起動
docker run --rm -p 8080:8080 my-javaapp

・・・ここで一旦諦める。server.xmlをテキストエディッタで開発するのは限界。。
