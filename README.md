# Lujinsuo
爬取陆金所新标、转让标的信息，并提醒

login_check_p2p.py（20190518亲测可用）

2019年4月后陆金所对网页的访问进行了限制，直接使用requests爬取的网页为验证网页，爬取不到需要的项目信息，改为selenium模拟浏览器进行爬取，可获得所需项目信息，但需要控制爬取频率，否则容易被封。 将休眠时间设置为20秒以上，可顺利爬取一段时间，但最后还是被封（实测爬了约2小时，IP被封了）。

需在python中安装selenium包，安装chrome浏览器，并下载对应版本的chromedriver.exe放在python的安装目录或其他环境变量的目录下（我把chromedriver.exe放在E:\ProgramFiles\Anaconda3\Scripts）

在代码中填入自己的陆金所账号和密码：

self.username = '*********'

self.pwd = '*********' 


new_p2p.py（20190518亲测可用）

不登录，直接抓取新标网页，若全部为“新客专享”，则提示“有新标！共%s项，其中新客专享%s项”；若出现“新客专享”的次数<“投资金额”出现的次数，说明有项目老客户也可投，则提示“有可投新标！！！！！” 注：新标页面貌似没有反爬设置，可以直接用requests爬取。


transfer_p2p.py（2019年4月后不可用）

不登录，直接抓取转让标的网页，若有新的转让项目，则提示“有新项目，快查看！”若有符合条件的转让项目，则打印出项目信息，并打开网页。 注：2019年4月前可用，4月后陆金所对网页的访问进行了限制，直接使用requests爬取的网页为验证网页，爬取不到需要的项目信息。
