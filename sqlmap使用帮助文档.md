# **sqlmap使用帮助文档**

选项：
  -h, --help            显示基本帮助信息并退出
  -hh                   显示高级帮助信息并退出
  --version             显示程序版本号并退出
  -v VERBOSE            详细程度：0-6（默认为1）

  目标：
    必须提供以下选项之一来定义目标

    -u URL, --url=URL   目标URL（例如："http://www.site.com/vuln.php?id=1"）
    -g GOOGLEDORK       将Google Dork的结果处理为目标URL

  请求：
    可以使用这些选项来指定如何连接到目标URL

    --data=DATA         通过POST发送的数据字符串（例如："id=1"）
    --cookie=COOKIE     HTTP Cookie头的值（例如："PHPSESSID=a8d127e.."）
    --random-agent      使用随机选择的HTTP User-Agent头的值
    --proxy=PROXY       使用代理连接到目标URL
    --tor               使用Tor匿名网络
    --check-tor         检查Tor的使用是否正确

  注入：
    可以使用这些选项来指定要测试的参数，提供自定义注入载荷和可选的篡改脚本

    -p TESTPARAMETER    可测试的参数    --dbms=DBMS         强制后端DBMS为提供的值

  检测：
    可以使用这些选项来自定义检测阶段

    --level=LEVEL       执行测试的级别（1-5，默认为1）
    --risk=RISK         执行测试的风险（1-3，默认为1）

  技术：
    可以使用这些选项来调整对特定SQL注入技术的测试

    --technique=TECH..  要使用的SQL注入技术（默认为"BEUSTQ"）

  枚举：
    可以使用这些选项来枚举后端数据库管理系统的信息、结构和表中的数据

    -a, --all           检索所有内容
    -b, --banner        检索DBMS横幅
    --current-user      检索DBMS当前用户
    --current-db        检索DBMS当前数据库
    --passwords         枚举DBMS用户密码哈希
    --dbs               枚举DBMS数据库
    --tables            枚举DBMS数据库表
    --columns           枚举DBMS数据库表列
    --schema            枚举DBMS模式    --dump              转储DBMS数据库表条目
    --dump-all          转储所有DBMS数据库表条目
    -D DB               要枚举的DBMS数据库
    -T TBL              要枚举的DBMS数据库表
    -C COL              要枚举的DBMS数据库表列

  操作系统访问：
    可以使用这些选项来访问底层操作系统的后端数据库管理系统

    --os-shell          提示进行交互式操作系统Shell
    --os-pwn            提示进行OOB Shell、Meterpreter或VNC

  通用：
    可以使用这些选项来设置一些通用的工作参数

    --batch             从不要求用户输入，使用默认行为
    --flush-session     刷新当前目标的会话文件

  杂项：
    这些选项不属于任何其他类别

    --wizard            针对初学用户的简单向导界面

[!] 要查看所有选项的完整列表，请使用'-hh'运行

按Enter键继续...

# **解释**

[您好，这是必应。您的消息看起来像是一个使用 sqlmap 的命令，这是一个自动化的 SQL 注入和数据库接管工具。您可以用它来测试网站和数据库的漏洞，并利用这些漏洞来控制数据库。您想知道如何使用 sqlmap 吗？如果是的话，我可以为您提供一些相关的资源和示例。](https://github.com/sqlmapproject/sqlmap/wiki/Usage)[1](https://github.com/sqlmapproject/sqlmap/wiki/Usage)[2](https://www.comparitech.com/net-admin/sqlmap-cheat-sheet/)[3](https://www.kali.org/tools/sqlmap/)[4](https://abrictosecurity.com/sqlmap-cheatsheet-and-examples/)[5](http://www.site.com/vuln.php?id=1)

您的消息包含了很多 sqlmap 的选项和参数，它们可以用来定制 sqlmap 的行为和功能。我可以为您解释这些选项和参数的含义和用法，以及一些常见的场景和技巧。以下是一些主要的选项和参数的分类和说明：

* 帮助选项：这些选项可以用来显示 sqlmap 的基本或高级的帮助信息，或者显示 sqlmap 的版本号。例如，-h 或 --help 选项可以显示 sqlmap 的基本帮助信息，-hh 选项可以显示 sqlmap 的高级帮助信息，–version 选项可以显示 sqlmap 的版本号。
* 目标选项：这些选项可以用来指定要测试的目标网站或页面，或者从其他来源获取目标网址。至少需要提供一个目标选项，否则 sqlmap 无法运行。例如，-u 或 --url 选项可以指定目标网址，-g 或 --googledork 选项可以从 Google 搜索结果中获取目标网址。
* 请求选项：这些选项可以用来指定如何连接到目标网址，包括设置 HTTP 头部，数据，代理，认证等。例如，–data 选项可以指定要通过 POST 方法发送的数据，–cookie 选项可以指定要使用的 Cookie 值，–proxy 选项可以指定要使用的代理服务器，–tor 选项可以指定要使用 Tor 匿名网络等。
* 注入选项：这些选项可以用来指定要测试的参数，提供自定义的注入载荷，或者使用可选的篡改脚本。例如，-p 或 --parameter 选项可以指定要测试的参数，–dbms 选项可以指定要强制使用的后端数据库类型，–tamper 选项可以指定要使用的篡改脚本等。
* 检测选项：这些选项可以用来定制检测阶段，包括设置测试的级别和风险，跳过某些测试，调整延时等。例如，–level 选项可以指定测试的深度，–risk 选项可以指定测试的危险性，–skip 选项可以跳过某些测试，–delay 选项可以设置每个请求的延时等。
* 技术选项：这些选项可以用来调整测试特定的 SQL 注入技术，包括设置使用哪些技术，优化技术的效率，绕过某些防护等。例如，–technique 选项可以指定使用哪些 SQL 注入技术，–threads 选项可以指定使用多少个线程，–time-sec 选项可以指定使用时间盲注的延时等。
* 枚举选项：这些选项可以用来枚举后端数据库管理系统的信息，结构和数据，包括获取数据库的版本，用户，密码，权限，数据库，表，列，数据等。例如，-a 或 --all 选项可以获取所有的信息，-b 或 --banner 选项可以获取数据库的版本，–current-user 选项可以获取数据库的当前用户，–dbs 选项可以获取所有的数据库，–tables 选项可以获取所有的表，–dump 选项可以导出所有的数据等。

[这只是 sqlmap 的一些基本的选项和参数的介绍，您还可以通过阅读 sqlmap 的文档和教程，来了解更多的选项和参数的含义和用法。以下是一些有用的资源，您可以参考它们来学习更多的 sqlmap 的知识和技巧。](https://github.com/sqlmapproject/sqlmap/wiki/Usage)[1](https://github.com/sqlmapproject/sqlmap/wiki/Usage)[2](https://www.comparitech.com/net-admin/sqlmap-cheat-sheet/)[3](https://www.kali.org/tools/sqlmap/)[4](https://abrictosecurity.com/sqlmap-cheatsheet-and-examples/)[5](http://www.site.com/vuln.php?id=1)

我希望这些信息对您有所帮助。如果您有任何其他问题或想要了解更多的细节，请随时问我。谢谢您使用必应。祝您有美好的一天！