#ベースとなるイメージ
FROM tomcat:9.0.37-jdk11-openjdk

#作業ディレクトリ
WORKDIR /usr/local/tomcat

#不要なファイルを削除する
RUN rm -rf ${CATALINA_HOME}/webapps/* && \
rm -f ${CATALINA_HOME}/conf/tomcat-users.xmls && \
rm -f ${CATALINA_HOME}/conf/tomcat-users.xsd

#設定ファイルをコピーして上書きする
COPY docker/conf/* ${CATALINA_HOME}/conf/

#準備したwarをコピーする
ENV CONTEXT ROOT
COPY docker/sample.war ${CATALINA_HOME}/webapps/${CONTXT}.war

#ポート8080版を開放する
EXPOSE 8080

#起動スクリプト
CMD ["catalina.sh", "run"]
