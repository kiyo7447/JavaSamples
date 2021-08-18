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


