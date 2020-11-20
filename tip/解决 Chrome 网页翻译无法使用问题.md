在使用 Chrome 科学上网的时候，经常遇到就算开了 VPN 还是无法使用 Chrome 内置的网页翻译功能，原来 PAC 没有识别 Google 翻译服务器

于是通过手动找到 谷歌翻译服务器的域名，然后把以下域名到科学上网的 PAC file 文件下
重新 load core 即可：

+ *.googletagmanager.com
+ *.google-analytics.com
+ *.translate.googleapis.com
