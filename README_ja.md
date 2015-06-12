# InstallProxyCert.java

InstallCert.javaのHTTPプロキシ対応版です。

InstallCertの実装だとHTTPSのプロキシに対応しきれないので作成しました。

ファイアウォール内にいる場合、プロキシ側でSSL/TLSの暗号化を解除してプロキシの証明書で暗号化している場合があります。
Eclipse等のJavaプログラムでHTTPSアクセスする場合（plug-inのインストール等）に以下のエラーが発生する場合があります。

` javax.net.ssl.SSLHandshakeException:sun.security.validator.ValidatorException: PKIX path building failed: `

InstallCertだとSSLSocketによる直接接続のみが有効で、プロキシ経由のHTTPS接続には対応できないので作成しました。

#プロキシ経由でサーバへのアクセスと証明書の取得を実行

`$ java -Dhttps.proxyHost=<proxyHost> -Dhttps.proxyPort=<proxyPort> -Dhttp.proxyUser=<username> -Dhttp.proxyPassword=<password> InstallProxyCert <https-url>`

あとの使用方法はInstallCertと同じです。
