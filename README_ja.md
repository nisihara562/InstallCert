# InstallProxyCert.java

InstallCert.javaのHTTPプロキシ対応版です。

InstallCertの実装だとHTTPSのプロキシに対応しきれないので作成しました。

# サーバへのアクセスと証明書の取得を実行

`$ java -Dhttps.proxyHost=<proxyHost> -Dhttps.proxyPort=<proxyPort> -Dhttp.proxyUser=<username> -Dhttp.proxyPassword=<password> InstallProxyCert <https-url>`

あとの使用方法はInstallCertと同じです。
