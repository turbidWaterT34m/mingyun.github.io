[python中有没有直接对多维数组排序](https://segmentfault.com/q/1010000009302207)
```js
sorted(dl1, key=lambda x: x[0])
>>> a=np.array([[ 0.02598003,1.],
               [ 0.00730082,2.],
               [ 0.05471569,3.],
               [ 0.02599167,4.],
               [ 0.0544947 ,5.],
               [ 0.00753346,6.]])
>>> a.sort(0)
>>> a
array([[ 0.00730082,  1.        ],
       [ 0.00753346,  2.        ],
       [ 0.02598003,  3.        ],
       [ 0.02599167,  4.        ],
       [ 0.0544947 ,  5.        ],
       [ 0.05471569,  6.        ]])
>>> a=np.array([[ 0.02598003,1.],
               [ 0.00730082,2.],
               [ 0.05471569,3.],
               [ 0.02599167,4.],
               [ 0.0544947 ,5.],
               [ 0.00753346,6.]])

>>> a[a.argsort(0)[:,0]]
array([[ 0.00730082,  2.        ],
       [ 0.00753346,  6.        ],
       [ 0.02598003,  1.        ],
       [ 0.02599167,  4.        ],
       [ 0.0544947 ,  5.        ],
       [ 0.05471569,  3.        ]])
```
[php fsockopen win10本地调用接口正常](https://segmentfault.com/q/1010000009423264)
```js
 $params = json_encode($template,JSON_UNESCAPED_UNICODE);
    $fp = fsockopen('api.weixin.qq.com', 80, $error, $errstr, 1);
    $http = "POST /cgi-bin/message/template/send?access_token={$access_token} HTTP/1.1 ".PHP_EOL."Host: api.weixin.qq.com".PHP_EOL."Content-type: application/x-www-form-urlencoded".PHP_EOL."Content-Length: " . strlen($params) .PHP_EOL. "Connection:close".PHP_EOL.PHP_EOL.$params.PHP_EOL.PHP_EOL;
    fwrite($fp, $http);
    fclose($fp);
```
https://github.com/Anahkiasen/underscore-php 
Laravel 中两类 Collection 的区别https://segmentfault.com/q/1010000009409607
MySQL数据库误操作后快速回滚的方法http://www.jb51.net/article/99553.htm
SUM(IF(type = 1, score, -score)) SUM(CASE WHEN type = 1 THEN score ELSE -score END)
http://www.php.cn/php.html
用一条sql实现该查询https://segmentfault.com/q/1010000009480365
SELECT user_id, COUNT(IF(status=0,true, null)) AS 'right_count', COUNT(IF(status=1,true, null)) AS 'error_count', COUNT(IF(status=2,true, null)) AS 'absenteeism_count' FROM online_exam_user_detail WHERE exam_publish_id in (1, 2, 3) GROUP BY user_id;
深入理解SELECT ... LOCK IN SHARE MODE和SELECT ... FOR UPDATEhttp://m.blog.csdn.net/article/details?id=50544728
mysql有没有语句可以直接更新排序后的数据的前十条https://segmentfault.com/q/1010000009471209
不支持使用 LIMIT 子句的 IN/ALL/ANY/SOME 子查询，只要你再来一层就行 如：

UPDATE table SET name='zhangsan' WHERE id IN
(SELECT t.id FROM (SELECT id FROM table LIMIT 10) AS t) 
composer 的SSL错误https://segmentfault.com/q/1010000009417320
failed to open stream: HTTP request failed!
SSH连接到服务器，一段时间不操作后会卡住https://segmentfault.com/q/1010000009421113
 linux 的安全问题,如果 60s 内没用任何数据,将会自动断开.
nosql 数据实时同步方案 案例https://github.com/liukelin/canal_mysql_nosql_sync
[阿里云 ecs 怎么安装mysql](https://segmentfault.com/q/1010000009366246)
启动报错，看mysql的error日志
登录权限报错，skip-grant-tables 跳过以后，修改mysql用户密码
skip grunt tables 放错位置了 我放在[mysqld_safe]的块下面了 放在[mysqld]即可
接下来重启失败，看错误日志，3306被占用了，kill -9 [pid] 发现杀掉后立刻重启，我用kill [pid]直接杀掉，发现3306端口不被占用了
接下来进行连接mysql，报错没有mysql.sock文件，可能是我之前误删了，重启服务器，然后service mysqld restart 重启，找到了mysql.sock ，之后发现my.cnf 文件下的socket位置与它找的不一样，用ln -s 软连接了一下

df包括已经删除但没释放的空间通过命令lsof|grep delete查看有哪些文件被删除但仍被程序占用。
需要将这些程序重启才能将所占用的空间释放掉。https://segmentfault.com/q/1010000009263138
[lnmp环境下有几种安装php扩展方式](https://segmentfault.com/q/1010000009341934)
make clean 清理一下
然后./configure$ phpize
$ ./configure
$ make && make install
[linux 的crond服务 最少是1分钟 php](https://segmentfault.com/q/1010000009329754)
系统使用systemd的话可以利用systemd.timer设置秒甚至毫秒级定时任务。https://segmentfault.com/a/1190000007916299#articleHeader2 
* * * * * sleep 10; php /home/test.php
* * * * * sleep 20; php /home/test.php
* * * * * sleep 30; php /home/test.php

[service ssh restart报错](https://segmentfault.com/q/1010000009316761)
nginx 代理location /api/ {
    proxy_pass http://ip:port
}https://segmentfault.com/a/1190000009082326 
service ssh restart是centos 6的命令。你这是centos 7。应该是systemctl restart sshd
[数字保留小数点后几位](https://segmentfault.com/q/1010000009314050)
from decimal import Decimal
a = Decimal('1.0231212121')
a = round(a,3) # Decimal('1.023')
'{:.2f}'.format(1.0231212121) # '1.02'
[git 上传项目至远程仓库](https://segmentfault.com/q/1010000009365671)
关于pull的错误：refusing to merge...
因为他们是两个不同的项目，要把两个不同的项目合并，git需要添加一句代码，在git pull,所以 
git pull origin master --allow-unrelated-histories
然后再push就ok了
git push origin master 
git remote add origin git@github.com:youngxhui/Test.git http://youngxhui.github.io/2016/08/13/Git%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C/
[mysql新说·记录数据轨迹的binlog](https://segmentfault.com/a/1190000008290848)
binlog是mysql的日志工具，binlog日志可以记录insert、update、delete的sql和操作时间。
mysqlbinlog /var/log/mysql/mysql-bin.000002
mysqlbinlog --start-datetime="2017-01-10 10:31:12" /var/log/mysql/mysql-bin.000002 > sql.txt

[ RBAC用户权限管理数据库设计](http://blog.csdn.net/qiaqia609/article/details/38102091)
![img](http://img.blog.csdn.net/20140725020830656?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcWlhcWlhNjA5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)
http://www.php.cn/course/497.html rbac视频教程已发
https://github.com/chjj/marked
 http://d.laravel-china.org/ 这个 网站 怎么由 md 格式转换为 html 网站的嘛？能帮解决的发红包感谢 https://github.com/evilstreak/markdown-js
[知乎上妹子都爱取啥名？](https://zhuanlan.zhihu.com/p/27016289)
[只有内心强大的人，才敢看这11部让人绝望的国产电影](https://zhuanlan.zhihu.com/p/26973597)
[Markdown中插入图片有什么技巧？](https://www.zhihu.com/question/21065229/answer/171989853)
使用搜狗输入法的截图工具加上极简图传  https://jiantuku.com/#/ 点击markdown 就可以复制了
[知乎上的好身材女神](https://www.zhihu.com/collection/62024183)
[揭秘勒索软件！用Python实现RSA加密，模拟文件劫持](https://zhuanlan.zhihu.com/p/26917148)
http://link.zhihu.com/?target=https%3A//github.com/QuantumLiu/pyRSA_demo 
[一个福利 · 520小程序爱の水晶球配置教程](https://zhuanlan.zhihu.com/p/26127760)
https://www.zhihu.com/question/57172252  
[结婚需要什么基本的安排和注意事项？](https://www.zhihu.com/question/22658147/answer/171062024)
[PHP黑系列之一：PHP 为什么大小写规则是如此不规则？](https://zhuanlan.zhihu.com/p/26965548)
[我在B站学数学](https://zhuanlan.zhihu.com/p/26899736)
http://link.zhihu.com/?target=http%3A//space.bilibili.com/88461692/%23%21/ 
有个网站叫kanbilibili哈哈哈哈专门提供b站下载。只要在b站找到你想下载的视频，再在网址栏里的bilibili前面加上kan然后猛敲回车就好啦
[论如何找到男朋友、女朋友？](https://www.zhihu.com/question/59089074/answer/170373589)
[javascript代码测试](https://scriptoj.com/topic/27/23-%E8%82%A5%E7%8C%AB%E5%88%97%E8%A1%A8)
[使用 PDO 的 prepare 预处理，能 100%防止 SQL 注入吗](https://www.v2ex.com/t/362646#reply30)
[PHP算法](http://www.leapcode.cn/question/two-sum)
[为什么有些程序员看不起 PHP 这门语言](https://www.zhihu.com/question/59820507)
http://www.albee.me/ http://blog.csdn.net/wuxia2001/article/details/45743641  
https://github.com/wuxia2001/loveyue https://link.zhihu.com/?target=http%3A//www.albee.me/index2.html
https://www.zhihu.com/topic/19577540/top-answers  http://love.nodoccat.cn/#/step-4 http://app.ikow.cn/love/
520送钱包，里面带钱
[有哪些程序员的告白方式？](https://www.zhihu.com/question/57172252)（）
[HTML5 进阶系列：拖放 API 实现拖放排序](https://zhuanlan.zhihu.com/p/26666141?group_id=848937782297628672)
[几个有趣又实用的网站](https://zhuanlan.zhihu.com/p/26993122?group_id=848916862652776448)
http://link.zhihu.com/?target=https%3A//itunes.apple.com/cn/app/id548861535%3Fmt%3D8
PHP 5.3的匿名函数中会丢失$this, self, parent作用域，所以你既不能use($this)，也不能直接在匿名函数里使用$this。怎么办呢，对于$this，你可以$that = $this然后use($that)，对于self和parent，可以改写__call方法，然后仍然用$that调用。准确说这个也不是use的bug，而是匿名函数的bug。当然这些bug在5.4及以后的版本都被修复了。
最好是PHP老手都会踩的语法坑。比如PHP的函数编码问题 echo trim("邯郸市","市"); 比如官方函数传参是传引用还是传值的问题
[无聊的马](http://endless.horse/)
[基于搜狗微信搜索的微信公众号爬虫接口](https://zhuanlan.zhihu.com/p/26675148?group_id=847065916146585600)
http://link.zhihu.com/?target=https%3A//github.com/Chyroc/WechatSogou
数据可视化的工具BDP个人版http://link.zhihu.com/?target=https%3A//me.bdp.cn/home.html
[又有实用效率小工具推荐](https://zhuanlan.zhihu.com/p/26941722?group_id=847920103541583872)
://cloudconvert.com/ 一个打造漂亮可视化数据图表的网站——文图http://link.zhihu.com/?target=https%3A//www.wentu.io/
[面试的时候，如何自我介绍](https://www.zhihu.com/question/19603341/answer/170829220?group_id=848269894255538176)
[如何让你的Python 代码一直运行着](https://zhuanlan.zhihu.com/p/26891627?group_id=847031341399830528)
[公众号文章配图去哪找](https://www.zhihu.com/question/37493361/answer/170634089?group_id=848519848135901184)
百度图片 FindIcons 免费图标搜索引擎    http://findicons.com/ 小猪动图 http://www.piggif.com/ 美图秀秀 创客贴
词云图悦 http://www.picdata.cn/ Wordart   https://wordart.com/    秀米 图表秀
现免费提供ps教程，想要的朋友可以关注公众号：0的开始，回复“教程”两个字即可获得下载地址。
[）如何编辑修改PDF文件里的文字？](https://zhuanlan.zhihu.com/p/26961504?group_id=848247152189788160)
迅捷PDF编辑器 搜索工具网站：smallpdf
[有哪些有意思的礼物可以送给女朋友](https://www.zhihu.com/question/28551841)
[删除了MySQL数据库中的文件](https://zhuanlan.zhihu.com/p/26941061)
rm -rf /var/lib/mysql/test/t.ibd表空间删除以后，依然可以查询和修改这张表
虽然在文件系统中已经找不到该文件，但是，该文件还没有真正被删除。在Linux下，如果我们删除了较大的文件，但是，使用df命令查看磁盘的空间，磁盘可用空间并没有增大。那么，很有可能是因为，你删除的这个文件正在被某一个进程使用。如果一个文件正在被一个进程使用，那么，删除文件时，文件并不会被立即删除，占用的磁盘空间也不会释放。
由于有进程（MySQL进程）打开了该文件，因此，当我们从外部删除文件时，文件并没有被真正的删除。只有当进程关闭该文件的文件句柄时，文件才会被真正删除。此时，我们依然可以使用lsof命令查看已经被删除的文件，如下所示：
lsof | grep t.ibd 在/proc[pid]/fd目录下，保存了所有进程打开的文件 ll /proc/11401/fd/25 
直接对文件句柄进行拷贝即可。将数据文件拷贝到MySQL的数据库目录下，并修改文件的权限 
cp /proc/11401/fd/25 /var/lib/mysql/test/t.ibd
chown mysql:mysql /var/lib/mysql/test/t.ibd  https://zhuanlan.zhihu.com/p/26923061
[只需两行，在微信中监控你的 Python 程序](https://zhuanlan.zhihu.com/p/25768417)
[Python爬虫和 Flask 实现小说网站](https://zhuanlan.zhihu.com/p/26937917)
github http://link.zhihu.com/?target=https%3A//github.com/Blackyukun/dingdian/tree/last 
[爆款游戏《贪吃蛇大作战》的 Python 实现](https://zhuanlan.zhihu.com/p/22339492)
[为什么有些程序员看不起 PHP 这门语言？](https://www.zhihu.com/question/59820507/answer/169623084)
[一张图让你彻底明白八字的关系](https://zhuanlan.zhihu.com/p/26892621)
[Python学习路径及练手项目合集](https://zhuanlan.zhihu.com/p/23561159)
[GitHub Pages + Hexo搭建博客](https://link.zhihu.com/?target=http%3A//crazymilk.github.io/2015/12/28/GitHub-Pages-Hexo%25E6%2590%25AD%25E5%25BB%25BA%25E5%258D%259A%25E5%25AE%25A2/%23more)
[爬虫杂谈（四）抓取微信公众号文章的轮子](https://zhuanlan.zhihu.com/p/26675148)
pip install wechatsogou
引用
from wechatsogou import *
wechats = WechatSogouApi() http://link.zhihu.com/?target=https%3A//github.com/Chyroc/WechatSogou


[又有实用效率小工具推荐啦](https://zhuanlan.zhihu.com/p/26941722)
Zybuluo 是在线Markdown 写作工具。  http://link.zhihu.com/?target=https%3A//cloudconvert.com/ CloudConvert 又是一个强大的在线多媒体转换工具。
视频下载王是一款视频下载工具。http://link.zhihu.com/?target=https%3A//www.apowersoft.cn/video-download-capture
Copyfish 是一款Chrome OCR（扫描识别成文字） 插件。http://link.zhihu.com/?target=https%3A//ocr.space/


QQ群记录16406911
```js

所有的功能模块全部存入数据库　然后把模块分配给用户 当用户访问模块的时候　判断是否是已经分配了
如果没有分配　就是没有权限　　　如果有分配就可以正常访问 这就是rbac的整体逻辑
有几种方式　　１.直接为用户分配权限　　２.为用户组分配权限（有人也叫角色权限）　　
权限一般有三种　　１.查看　　２.编辑　　３.删除
rbac比较绕　弄不懂思路　看代码也没用 拿tp 做为示例说一下　例：　/index.php?m=会员管理?a=查看会员
这样的一个ＵＲＬ　　分别有模块名，操作名 你把模块与操作名记录到数据库里
然后指定某个用户　能不能访问这个模块

1，不打电话，用邮件或短信通知面试的，不去
2，打电话，但不是女的公司，不去
3，是女的，一问三不知的公司，不去
自己的顶级域名个博客网站
自己顶级域名的邮箱
github仓库
不要跟我说什么 性能，并发，加载量，给我一个laravel，拿起来就是干
有这三项，人家至少知道你在这行混久了，好多人开发3 4年，连个网站都不会赔的
mail@sniu.com
mail@zhangxihai.cn 
mail@is.cx
买个域名  去腾讯申请个域名邮箱就是了 又不需要备案
电话通知面试用女人，是专业的表现
还有，老板自己通知面试的，肯定更不专业了
域名这东西 随便注册
申请域名邮箱又不要备案
找工作最爽的就是，你说的东西框架什么面试官都没听过，然后各种羡慕的眼光的时候，然后面试官想让你上班，然后你说对该公司不感兴趣的时候，是最爽的
laravel三大核心：
1，mvc
2，blade
3，orm

其他的不会也不影响工作
不问设计模式  问的话也把单例模式给去掉   问问 工厂  观察者  代理三种
公式化回答的话 就问问什么简单工厂的变种
说再过2年 程序员不会docker  就会被淘汰了

问设计模式有什么用啊   框架下面有个鸡毛的设计模式  又不招架构
会那么多有鸡毛用啊，给你3天让你换个技术路线你换的了么
orm用的贼熟，一用原生SQL就没辙，有鸡毛用
前端不熟，难到你要换个技术路线，用rest架构再招个前端

要就要基础牢  被虐经验多的
但是就很多问设计模式的啊  还一堆题目 现场写SQL查询的  当时可真不好写那些SQL
要学会分析SQL是否有性能问题

设计模式，单例，工厂，观察者，够用了 观察者，核心是是事件驱动
实际上你的类没继承  没实现接口 没人trait， 就去用静态得了
有继承 有接口 有trait 就用单例
可以把静态扔了，当然，单例，本身就是一个静态
类型为 “人”，你传参数时传的是“女人”，但程序能跑通，这就是多态 因为女人也是人
laravel + swoole = 天下无敌 
yaf是世界上最简单的框架之一，一天之内学不会都难
本身就特别简单，没有组件，没有m，没有v
php-fpm php是解析式的，每次解析完，就会把内存释放掉。不同于其他语言。
>>> print '\xe7\xa7\xbb\xe5\x8a\xa8'.decode('utf-8')
移动
我们公司的面试题里，有：redis请求量比较大的时候怎么办，
开发者可以考虑用事务 而事务又分原子性与非原子性，这两个有什么区别，使用场景是什么
其实问题都是很简单，对于 批量读数据，就可以用非原子性批处理（事务），对于写数据，如果考虑高安全，要使用原子性，但原子性的批处理要比非原子性的批处理慢10倍。。。。

  function consoleLog($data, $log = false)
    {
        // 数据预处理json
        if (is_string($data) && $preJsonMsg = json_decode($data, true)) {
            if (count($preJsonMsg) > 1) {
                $data = $preJsonMsg;
            }
        }

        $logFunc = $log ? 'console.log' : 'console.dir';

        if (is_array($data) || is_object($data)) {
            echo("<script>".$logFunc."(".json_encode($data).");</script>");
        } else {
            echo("<script>".$logFunc."('".$data."');</script>");
        }
    }
 laravel composer update
 $ composer update
Loading composer repositories with package information
Updating dependencies (including require-dev)
Package operations: 12 installs, 43 updates, 0 removals
  - Removing rase/socket.io-emitter (0.7.0)
  - Installing rase/socket.io-emitter (dev-master ce11711): Downloading (connect
Downloading (100%)
  - Installing paragonie/random_compat (v1.x-dev 965cdeb): Downloading (connecti
Downloading (100%)
  - Removing nesbot/carbon (1.21.0)
  - Installing nesbot/carbon (dev-master 926aee5): Downloading (100%)
  - Updating mtdowling/cron-expression (v1.0.4 => v1.2.0): Downloading (connecti
Downloading (100%)
  - Removing symfony/polyfill-util (dev-master 41250fb)
  - Installing symfony/polyfill-util (dev-master 746bce0): Downloading (connecti
Downloading (100%)
  - Removing symfony/polyfill-php56 (dev-master b188ceb)
vhalllsp@VHALLLSP-PC /d/soft/wamp/www/laravel_web (switch_host)nloading (connect
$ wnloading (100%)
  - Removing jeremeamia/superclosure (dev-master 29a88be)
  - Installing jeremeamia/superclosure (dev-master af26c92): Downloading (connec
Downloading (100%)
  - Updating barryvdh/laravel-debugbar (v2.1.1 => v2.1.4): Downloading (connecti
Downloading (100%)
  - Removing guzzlehttp/psr7 (1.2.1)
  - Installing guzzlehttp/psr7 (dev-master 8882b25): Downloading (connecting...)
Downloading (100%)
  - Removing guzzlehttp/promises (dev-master b1e1c0d)
  - Installing guzzlehttp/promises (dev-master 73815f3): Downloading (connecting
Downloading (100%)
  - Removing guzzlehttp/guzzle (dev-master 74fc390)
  - Installing guzzlehttp/guzzle (dev-master 1739e8b): Downloading (connecting..
Downloading (100%)
  - Updating league/oauth1-client (1.6.1 => 1.7.0): Downloading (100%)
  - Removing sebastian/recursion-context (dev-master 913401d)
  - Installing sebastian/recursion-context (1.0.x-dev b19cc32): Downloading (con
Downloading (100%)
  - Removing sebastian/exporter (dev-master f88f893)
  - Installing sebastian/exporter (1.2.x-dev dcd43bc): Downloading (connecting..
Downloading (100%)
  - Removing sebastian/comparator (dev-master 937efb2)
  - Installing sebastian/comparator (1.2.x-dev 18a5d97): Downloading (connecting
Downloading (100%)
  - Installing webmozart/assert (dev-master 4a8bf11): Downloading (connecting...
Downloading (100%)
  - Installing phpdocumentor/reflection-common (dev-master a046af6): Downloading
Downloading (100%)
  - Installing phpdocumentor/type-resolver (0.2.1): Downloading (100%)
  - Updating phpdocumentor/reflection-docblock (2.0.4 => 3.1.1): Downloading (co
Downloading (100%)
  - Removing phpspec/prophecy (dev-master e55e3e3)
  - Installing phpspec/prophecy (dev-master abe41cb): Downloading (connecting...
Downloading (100%)
  - Removing sebastian/environment (dev-master 6e71337)
  - Installing sebastian/environment (1.3.x-dev 67f5569): Downloading (connectin
Downloading (100%)
  - Removing phpunit/php-code-coverage (dev-master 40103f9)
  - Installing phpunit/php-code-coverage (2.2.x-dev eabf68b): Downloading (conne
Downloading (100%)
  - Removing phpunit/php-timer (1.0.7)
  - Installing phpunit/php-timer (dev-master d107f34): Downloading (connecting..
Downloading (100%)
  - Removing phpunit/phpunit-mock-objects (dev-master a1304c5)
  - Installing phpunit/phpunit-mock-objects (2.3.x-dev ac8e7a3): Downloading (co
Downloading (100%)
  - Removing phpspec/php-diff (v1.0.2)
  - Installing phpspec/php-diff (dev-master 0464787): Downloading (connecting...
Downloading (100%)
  - Updating omnipay/common (2.4.0 => 2.5.x-dev b1440bd):  Checking out b1440bd7
c0
  - Updating symfony/css-selector (2.8.x-dev ac06d81 => dev-master 4d882dc):  Ch
ecking out 4d882dced7
  - Removing sebastian/global-state (1.1.1)
  - Installing sebastian/global-state (1.1.x-dev cea85a8): Downloading (connecti
Downloading (100%)
  - Installing vhall/ip_location (dev-master 62b4d3e): Downloading (connecting..
Downloading (100%)
  - Installing vhall/check_picture (dev-master 6dd5373): Downloading (connecting
Downloading (100%)
  - Installing flamecore/user-agent (dev-master 3e8517d): Downloading (connectin
Downloading (100%)
  - Installing composer/ca-bundle (dev-master b17e615): Downloading (connecting.
Downloading (100%)
  - Installing maxmind/web-service-common (v0.3.1): Downloading (100%)
  - Installing maxmind-db/reader (v1.1.3): Downloading (100%)
  - Installing geoip2/geoip2 (v2.5.0): Downloading (100%)
  - Installing aliyuncs/oss-sdk-php (v2.2.4): Downloading (100%)
  - Removing doctrine/instantiator (dev-master 8e884e7)
  - Installing doctrine/instantiator (dev-master 5acd2bd): Downloading (connecti
Downloading (100%)
  - Removing league/flysystem (dev-master 3130ff9)
  - Installing league/flysystem (dev-master 64ff28b): Downloading (connecting...
Downloading (100%)
  - Removing psr/log (dev-master d8e60a5)
  - Installing psr/log (dev-master 4ebe3a8): Downloading (100%)
  - Removing phpunit/php-file-iterator (dev-master 6150bf2)
  - Installing phpunit/php-file-iterator (dev-master 3cc8f69): Downloading (conn
Downloading (100%)
  - Removing phpunit/php-token-stream (dev-master cab6c6f)
  - Installing phpunit/php-token-stream (dev-master 9ddb181): Downloading (conne
Downloading (100%)
  - Removing guzzle/guzzle (dev-master b3f5050)
  - Installing guzzle/guzzle (dev-master f7778ed): Downloading (100%)
  - Removing psr/http-message (dev-master 85d6369)
  - Installing psr/http-message (dev-master f6561bf): Downloading (connecting...
Downloading (100%)
  - Removing symfony/security-core (2.6.x-dev 05f58bb)
  - Installing symfony/security-core (2.6.x-dev 813cf2a): Downloading (connectin
Downloading (100%)
  - Removing doctrine/inflector (dev-master 90b2128)
  - Installing doctrine/inflector (dev-master 803a2ed): Downloading (connecting.
Downloading (100%)
  - Removing monolog/monolog (1.x-dev 592af02)
  - Installing monolog/monolog (1.x-dev 35c07a8): Downloading (100%)
  - Removing sebastian/diff (dev-master 13edfd8)
  - Installing sebastian/diff (dev-master 86ba64b): Downloading (100%)
  - Removing maximebf/debugbar (dev-master 173f334)
  - Installing maximebf/debugbar (dev-master b0dbb58): Downloading (connecting..
Downloading (100%)
  - Removing laravel/framework (5.0.x-dev b47cbe5)
  - Installing laravel/framework (5.0.x-dev 262b813): Downloading (connecting...
Downloading (100%)
  - Updating phpoffice/phpexcel 1.8.x-dev (f29b05b => 185bf41):  Checking out 18
5bf41233
  - Removing swiftmailer/swiftmailer (5.x-dev fffbc0e)
  - Installing swiftmailer/swiftmailer (5.x-dev cd4ffa8): Downloading (connectin
Downloading (100%)
  - Removing symfony/http-kernel (2.6.x-dev 498866a)
  - Installing symfony/http-kernel (2.6.x-dev cdd991d): Downloading (connecting.
Downloading (100%)
  - Removing symfony/event-dispatcher (2.8.x-dev 475b620)
  - Installing symfony/event-dispatcher (2.8.x-dev 7fc8e2b): Downloading (connec
Downloading (100%)
  - Removing nikic/php-parser (1.x-dev f78af2c)
  - Installing nikic/php-parser (1.x-dev c4bbc8e): Downloading (100%)
  - Removing symfony/yaml (2.8.x-dev 085a1eb)
  - Installing symfony/yaml (2.8.x-dev 93ccdde): Downloading (100%)
paragonie/random_compat suggests installing ext-libsodium (Provides a modern cry
pto API that can be used to generate random bytes.)
maxmind-db/reader suggests installing ext-gmp (bcmath or gmp is requred for deco
ding larger integers with the pure PHP decoder)
maxmind-db/reader suggests installing ext-maxminddb (A C-based database decoder
that provides significantly faster lookups)
Package guzzle/guzzle is abandoned, you should avoid using it. Use guzzlehttp/gu
zzle instead.
Writing lock file
Generating autoload files
> php artisan clear-compiled
> php artisan optimize
    
```
[关于laravel5 消息订阅/发布的理解初](http://www.cnblogs.com/phpper/p/6867786.html)
php artisan make:command RedisSubscribe
\Redis::publish('user-channel', json_encode(['username' => 'fantasy','message'=>'i miss you']));
$exitCode = \Artisan::call('redis:subscribe');//这里应该是代码启动进程监听的命令了 网页调用 同php artisan redis:subscribe
[基于Token的身份验证——JWT ](http://www.cnblogs.com/zjutzz/p/5790180.html)
JWT就是一个字符串，经过加密处理与校验处理的字符串，一个JWT实际上就是一个字符串，它由三部分组成，头部、载荷与签名。形式为： 
A.B.C
http://www.cnblogs.com/xiekeli/p/5607107.html  http://laravelacademy.org/post/3640.html
A由JWT头部信息header加密得到
B由JWT用到的身份验证信息json数据加密得到
C由A和B加密得到，是校验部分
$token = array(
    "iss" => "http://example.org",
    "aud" => "http://example.com",
    "iat" => 1356999524,
    "exp" => 1357000000
);$jwt = JWT::encode($token, $key);
mac 系统由于空格引发的 storage/framework/views/wfdfdfdfdf 语法错误 unexceped end of file
@if(empty($webinar->is_demand))回放@endif观看详情 模板引擎别这样写了... mac 用户访问页面之间崩溃了

汉字别挨着 if关键字..就行 
@if(empty($webinar->is_demand)) 回放 @endif 观看详情
$x('//a').filter(function($i){return $i.href && $i.href!='javascript:;';}).map(function($a){return $a.href;}).join(',')
[面向未来的团队工作方式机器人](https://bearychat.com/)
https://github.com/ElfSundae/BearyChat

[微信支付api.mch.weixin.qq.com域名解析慢原因：ipv6](http://2014.54chen.com/blog/2016/06/18/wexin-resolve-slowly/)
wget api.mch.weixin.qq.com
wget -4 api.mch.weixin.qq.com

如果是curl，c可以强制指定ipv4，使用curl_easy_setopt(curl, CURLOPT_IPRESOLVE, CURL_IPRESOLVE_V4);
[Md5在线破解 MD5 Crack](http://2014.54chen.com/blog/2008/11/25/md5%E5%9C%A8%E7%BA%BF%E7%A0%B4%E8%A7%A3-md5-crack/)
[MySQL的性能调优工具：比mysqlreport更方便的tuning-primer.sh](http://2014.54chen.com/blog/2008/12/22/mysql%E7%9A%84%E6%80%A7%E8%83%BD%E8%B0%83%E4%BC%98%E5%B7%A5%E5%85%B7%EF%BC%9A%E6%AF%94mysqlreport%E6%9B%B4%E6%96%B9%E4%BE%BF%E7%9A%84tuning-primersh/)
wget http://www.day32.com/MySQL/tuning-primer.sh chmod +x tuning-primer.sh
./tuning-primer.sh

[Web压力测试工具介绍](http://2014.54chen.com/blog/2008/11/26/web%E5%8E%8B%E5%8A%9B%E6%B5%8B%E8%AF%95%E5%B7%A5%E5%85%B7%E4%BB%8B%E7%BB%8D/)
ab -n 1000 -c 50 http://www.domain.com/test.php
[PHP代码的优与劣](http://2014.54chen.com/blog/2008/11/27/php%E4%BB%A3%E7%A0%81%E7%9A%84%E4%BC%98%E4%B8%8E%E5%8A%A3/)
[MySQL时间字段究竟使用INT还是DateTime？](http://2014.54chen.com/blog/2009/04/27/%E5%8E%9F%E5%88%9B%E5%AE%9E%E6%B5%8Bmysql%E6%97%B6%E9%97%B4%E5%AD%97%E6%AE%B5%E7%A9%B6%E7%AB%9F%E4%BD%BF%E7%94%A8int%E8%BF%98%E6%98%AFdatetime%EF%BC%9F/)
大数据量下，如果存在大量的select * from table where 时间>XX这样的查询，在MySQL5.1时使用int换datetime是有意义的。
```js
优良的PHP代码应该是结构化的。大段的代码应该被分割整理成一个个函数或方法，而那些不气眼的小段代码则应该加上注释，以便日后清楚它们的用途。而且应该尽可能地把前台代码如HTML、CSS、Javascript等从程序中分离出来。PHP的面向对象编程特性可以很好地帮助程序员将代码整理有序。
　　优良的PHP代码应该是规范化的。无论是为变量名和函数名设定命名规则，还是对一些会重复使用的过程如数据库操作和错误处理进行标准化，抑或是简单到规定好代码是怎样缩进的，这些规范化都可以让代码的可读性大大提高。
　　优良的PHP代码应该是自适应的。PHP有许多特性如magic quotes和short tags，这些特性的打开和关闭会影响到程序的运行。所以，一个好的程序员应该在他的代码中加如适当的语句来使程序能够根据环境进行调整。
　　优良的PHP代码应该是安全的。虽然PHP是一种高效、灵活的语言，没有固定的框架，但却把安全问题留给了程序员们。对潜在安全漏洞的深刻理解，如跨站脚本攻击（XSS）、跨站请求伪造（CSRF）、代码注入漏洞、字符编码循环漏洞等，对于今天的专业程序员来说是至关重要的。
  htmlspecialchars($_GET['query'], ENT_QUOTES)
  
```

[window有内置属性name](https://segmentfault.com/q/1010000009425086)
var name = [0, 1, 2]
console.log(name) // 输出 "0,1,2"
因为window有内置属性name，所以你在全局下声明name其实就是在给window.name赋值。关于window.name。类似的属性还有status等

所以你用name1就没有问题。其实你在非全局下用name，或者在node环境的全局下用name也是没有逗号的。
作用域是全局的 所以你定义的 name 变量相当于 window.name 
它是一个特殊的全局变量 任何值赋值给它都会进行 toString 操作
这里你将数组给 window.name 实际你可以输出看一下会发现它并不是数组而是字符串
而恰好字符串是可以用循环遍历的 所以输出了逗号

var name = [0, 1, 2]
console.log(name) // 0,1,2
console.log(typeof name === 'string') // true
解决方法：不使用全局作用域 加一层自执行函数
name是关键字，不要用这个命名变量,你可以typeof一下，会发现name是string，name1是object
(function() {
  var name = [0, 1, 2]
  console.log(name) // [0, 1, 2]
  console.log(Object.prototype.toString.call(name)) // [object Array]
})()
[PHP实现Unicode和Utf-8编码的互相转换](https://segmentfault.com/a/1190000003020776)
[JavaScript 全局变量的一个困惑](https://segmentfault.com/q/1010000009418450)
// ①
console.log(b); // 代码执行到这行的时候，b未定义，在当前的作用域链上找不到b，所以 b is not defined
b = 2; 

// ②
console.log(b);
var b = 2;
// 由于变量声明提升，相当于
var b;
console.log(b); // 代码执行到这行的时候，b已经声明了，只是没有赋值而已，所以 undefined
b = 2; 
代码执行总有个先后顺序吧。。。
[设置cookie之后,刷新页面消失](https://segmentfault.com/q/1010000009395195)
找到原因了,是因为跨域造成的,添加下头信息就行了
[H5或者JS如何获得当前位置地理定位](https://segmentfault.com/q/1010000009120811)
[cookie设置了生命周期30分钟](https://segmentfault.com/q/1010000009423958)
cookie是单页面的，cookie 是每次都是重新生成的，如果设置了时间，是不是即便一直操作，时间到了也会失效的
[php条件判断中同时有"与、或"，优先级](https://segmentfault.com/q/1010000009424520)
优先级是与 > 或；
$isAuthor = $article->user_id ==  Auth::id();
$isValid = $article->status==0 || $article->expired_at < Carbon::now();

if ($isAuthor && $isValid)
{
    $article->delete();
    return back();
}
[laravel如何拼接多个模糊条件查询?](https://segmentfault.com/q/1010000009413913)
[商品无限极分类Mysql表设计](https://segmentfault.com/q/1010000009419758)
用like并不是一个好的选择，推荐一个Mysql函数find_in_set应该能解决楼主需求。

[匿名函数 返回值的问题](https://segmentfault.com/q/1010000009415498)
[fwrite和fread操作同一个文件](https://segmentfault.com/q/1010000009423315)
fopen的第二个参数为模式, 有r, w, b, a等模式, 其中a表示append, 也就是附加的意思, 打开时不会清空文件(把EOF指向0), 而是把文件指针指向文件末尾
[算法题：从数组中取出n个元素生成一个新的数组](https://segmentfault.com/q/1010000009427743)
[JS的函数递归阶乘问题](https://segmentfault.com/q/1010000009422753)
 function jiecheng(n){
            if(n==1){
                return 1
            }else{
                return n*jiecheng(n-1)    
            }
        }
        var n=5;
        alert(jiecheng(6))
[Yandex Gixy - NGINX 配置文件分析器](https://www.v2ex.com/t/361498)
pip install gixy
[算法如何实现?](https://segmentfault.com/q/1010000009424232)
[Fortran读取BMP图像](http://fcode.cn/code-list-1.html)
[简历黑客](http://jianliheike.com)
[Scrapy第五篇：断点续爬 | 存入MySQL](https://zhuanlan.zhihu.com/p/26810901?group_id=845755819374047232)
CTF学习站点总结https://zhuanlan.zhihu.com/p/26876253?group_id=846472044680990720  【以图搜图】网站大全了https://zhuanlan.zhihu.com/p/25610099
图片内容鉴别主要包括：鉴黄、暴恐识别、OCR（识别图片中的文字）https://zhuanlan.zhihu.com/p/26819950?group_id=845705440347176960 https://www.tuputech.com/demo  
Ngrok：本地主机的安全隧道工具https://ngrok.com/
用非常生动的动画给你讲数学，每集10分钟左右。http://t.cn/RIJNj6h 
app后端设计--总目录 http://blog.csdn.net/newjueqi/article/details/19003775 
你遇到过哪些神奇的网站，并且改变了你的生活质量http://weibo.com/2182038504/F1QTtbrkv 
 leetcode-cli: 体验不一样的刷题风 (2) 流程篇https://github.com/skygragon/leetcode-cli
唐宋文学编年地图http://sou-yun.com/poetlife.html
安利一个良心电影、电视剧下载网站https://moviejie.com/
ss翻墙http://macvpn.hk/
收集整理一些常用的PHP类库https://github.com/JingwenTian/awesome-php 
php 源码阅读http://ghost.icosplay.cc/2017/04/25/php-yuan-ma-yue-du
浅谈PHP进程管理http://www.manks.top/php-cgi-fpm.html
一行代码，打造在线编辑器http://blog.githuber.cn/posts/2395 http://litaotao.github.io/files/editor.html
8种常被忽视的SQL错误用法http://mp.weixin.qq.com/s/1WpspGr7R-EjXfhWzlsZvQ
支付开发填坑记之微信支付https://segmentfault.com/a/1190000009346755
public function xmlToArray($xml){
    return json_decode(json_encode(simplexml_load_string($xml, 'SimpleXMLElement', LIBXML_NOCDATA)), true);
}


easyPHP-Swoole：专为 API 而生的常驻内存化的 PHP 开发框架https://github.com/kiss291323003/easyPHP-Swoole  
SQLizer现在有将文件转换为SQL的API。  https://sqlizer.io/help/api#step1
这个在线二维码生成器不错 
推荐几个常用的PDF在线转换网站】Smallpdf：O网页链接，ilovepdf：O网页链接，ConvertPDFtoWord：PDFConverter：O网页链接，PDFmyURL
ypefont：用于识别照片中文本字体的算法。  https://github.com/Sirvasile/Typefont
数据结构常见的八大排序算法（详细整理）http://www.jianshu.com/p/7d037c332a9d
HTTP Prompt is an interactive command-line HTTPhttp://http-prompt.com/
Laravel的Facade实现原理http://www.jianshu.com/p/fd03d0ebc22a?hmsr=toutiao.io&utm_medium=toutiao.io&utm_source=toutiao.io
Facade其实是一个容器中类的静态代理，他可以让你以静态的方式来调用存放在容器中任何对象的任何方法。 直接来看看__callStatic这个方法
Hacking Tools搜罗大集合http://www.freebuf.com/sectool/133949.html
开源的类 PostMan，API 管理工具https://github.com/getinsomnia/insomnia
基于Python开发的可以模拟百万用户的压测工具https://github.com/locustio/locust?files=1
命令行下，我总是使用 jq 解析 JSON 数据网页版 https://github.com/fiatjaf/jq-web
APP应用和网页版的支付功能（支付宝，微信，银联）http://blog.leungjz.top/2017/05/10/payment-alipay/?hmsr=toutiao.io&utm_medium=toutiao.io&utm_source=toutiao.io
https://sqlnotebook.com/ 
php代码检测https://github.com/phpro/grumphp composer require --dev phpro/grumphp
[除了我们常用的硕鼠外，再给大家安利一款超厉害的视频下载工具视频下载王），它不仅支持YouTube、Vimeo、Fox、AcFun、哔哩哔哩、优酷、爱奇艺](https://www.apowersoft.cn/video-download-capture)
[常见的网站服务器架构有哪些](https://www.zhihu.com/question/20657269/answer/101795180)
反反爬虫利器！教你怎么用代理，拨号换IP……https://zhuanlan.zhihu.com/p/26876834
爬虫比较https://github.com/lining0806/PythonSpiderNotes
抓取手机app的数据（摩拜单车https://zhuanlan.zhihu.com/p/26785815 http://link.zhihu.com/?target=https%3A//github.com/kimg1234/pachong/blob/master/mobai.py
php数组排序https://www.zhihu.com/question/59614878/answer/167121815
```js
uasort($arr, function($a, $b) {
	// 比较函数返回1表示交换顺序
	if($a['Order_info']['add_time'] == $b['Order_info']['add_time']) {
		return 0;
	} else {	
		// 大的交换到前面,所以是降序
		return ($a['Order_info']['add_time'] < $b['Order_info']['add_time']) ? 1 : -1;
		// 小的交换到前面,所以是升序
		return ($a['Order_info']['add_time'] > $b['Order_info']['add_time']) ? 1 : -1;
	}
});

作者：eechen
链接：https://www.zhihu.com/question/59614878/answer/167121815
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```
[低端姿势拿下某IDC公司主站php](https://zhuanlan.zhihu.com/p/26658739?group_id=842400839929847808)
借助的就是MySQL的general_log，MySQL中这个general_log是用于记录MySQL中所有执行过的SQL查询，他的记录方式可以是数据表，也可以是文件，并且文件路径也可以指定https://github.com/cw1997/MySQL-Monitor MySQL服务器执行SQL记录实时监控（WEB版本）
show global variables like '%general%';
set global general_log = on;
set global general_log_file = 'D://phpStudy//WWW//ThinkPHP//test.php';
select '<?php @ev（防和谐补丁）al($_POST[admin])?>';
[有哪些实用的计算机相关技能，可以在一天内学会？](https://zhuanlan.zhihu.com/p/26661971?group_id=842461525452136448)
[把嵌套的python list转成一个一维的python list](https://www.zhihu.com/question/27010691)
```js
>>> from compiler.ast import flatten
>>> flatten(a)
reduce(lambda x,y:x+y, a)
import itertools
a = [[1,2,3],[4,5,6], [7], [8,9]]
out = list(itertools.chain.from_iterable(a))
sum(a,[])
def fun(li,em=[]):  #优雅滴写法，包治各种嵌套
    for x in li:
        if type(x)!=list:
            em.append(x)
        else:
            fun(x)
    return em

最简单的方法，用 numpy.ravel()。

a = [[1,2,3], [5, 2, 8], [7,8,9]]

list(np.ravel(a))

得到： 

[1, 2, 3, 5, 2, 8, 7, 8, 9]
a= eval('['+str(a).replace(' ','').replace('[','').replace(']','')+']')
import operator
from functools import reduce
a = [[1,2,3], [4,5,6], [7,8,9]]
print(reduce(operator.add, a))
[item for sublist in list for item in sublist]
a = eval('[%s]'%repr(l).replace('[', '').replace(']', ''))
```
[分享几个快乐有趣的网站](https://zhuanlan.zhihu.com/p/26871835?group_id=846461293912276992)
在线制作GIF动态图片http://link.zhihu.com/?target=http%3A//gickr.com/
[别被忽悠，你要逃离不肯给你涨薪的公司](https://zhuanlan.zhihu.com/p/26855046?group_id=846121250454634497)
你应该去回答：「我看重的，绝不是薪水这么简单，是工作、岗位所能给我带来的价值有多少，以及我在这份工作能提供的价值是多少。薪水是象征了一个人的职业素养和职场价值，所以我们谈论的不仅仅是薪水这么简单，而是在谈论我的专业实力以及我的职业操守，因此，我认为我是有提供价值的，想提升相应薪水。所以，请问：公司能为我现在的岗位提供的薪水是多少？」
[大数据系列 2 —看腾讯的大数据产品](https://zhuanlan.zhihu.com/p/25634208)
腾讯位置大数据http://link.zhihu.com/?target=https%3A//heat.qq.com/index.php  http://link.zhihu.com/?target=https%3A//www.qcloud.com/act/event/ci_demo.html 微信指数 、万象优图
[将文字隐藏到图片中](https://zhuanlan.zhihu.com/p/25285364?refer=wnsouba)
http://link.zhihu.com/?target=http%3A//www.shuidi.im/
飞搜人脸识别 http://link.zhihu.com/?target=http%3A//www.faceall.cn%3A82/
阿里绿网http://link.zhihu.com/?target=https%3A//m.aliyun.com/markets/aliyun/act/lvwangdemo%3Fspm%3D5176.55804.359640.1.6xojDa%23testOnline
网易易盾http://link.zhihu.com/?target=http%3A//dun.163.com/trial/image
图普科技http://link.zhihu.com/?target=https%3A//www.tuputech.com/demo
腾讯优图http://link.zhihu.com/?target=https%3A//open.youtu.qq.com/welcome/experience
[是腾讯出的TIM，TIM是一款轻量级的QQ实时多人编辑文档国内的有一起写、石墨文档](https://zhuanlan.zhihu.com/p/26255850)
[知乎TOP 500 赞的回答](https://zhuanlan.zhihu.com/p/26779637)
[百度云盘搜索](http://www.biliworld.com/)
[面试官问现在工资是多少？该怎么回答？](https://zhuanlan.zhihu.com/p/26830966?group_id=845718905661038592)
[Python进阶](https://github.com/eastlakeside/interpy-zh)
[php生成随机红包算法](http://www.jianshu.com/p/287a21a24e09#)
[简单理解RESTful API接口风格](http://www.lcode.cc/2016/08/10/restful-v1.html)
[CGI与fastcgi与php-fpm与php-cgi的关系](http://www.lcode.cc/2017/01/15/php-fpm.html)
cgi是一个协议，它规定了服务器Nginx会将那些数据传送给php-cgi

fastcgi也可以说是一个协议。fastcgi是对cgi的性能的一次提高。fastcgi会先启动一个master，解析配置文件（php.ini等），初始化执行环境，然后再启动多个worker，当请求过来时，master会传递给一个worker，然后等待下一个请求。

php-fpm是实现了fastcgi这个协议的程序，用来管理php-cgi的（php-fpm是fastcgi进程管理器）

php-cgi是解释php程序的

[PHP文件锁机制](http://www.lcode.cc/2016/10/15/php-flock.html)
```js
//获取指针
$file = 'lock/increase.txt';
$fp = fopen($file, 'r');
//加排他锁
flock($fp, LOCK_EX);
//数据操作
$key = 'company_watch_num_' . $request['company_id'];
Cache::increment($key);
//解锁
flock($fp, LOCK_UN);
//关闭指针
fclose($fp);
```
[PyPDF2 用 Python 操作 PDF](https://zhuanlan.zhihu.com/p/26647491?group_id=842900717793603584)
```js
from PyPDF2 import PdfFileReader, PdfFileWriter
infn = 'infn.pdf'
outfn = 'outfn.pdf'
# 获取一个 PdfFileReader 对象
pdf_input = PdfFileReader(open(infn, 'rb'))
# 获取 PDF 的页数
page_count = pdf_input.getNumPages()
print(page_count)
# 返回一个 PageObject
page = pdf_input.getPage(i)

# 获取一个 PdfFileWriter 对象
pdf_output = PdfFileWriter()
# 将一个 PageObject 加入到 PdfFileWriter 中
pdf_output.addPage(page)
# 输出到文件中
pdf_output.write(open(outfn, 'wb'))
```


[命令行提示](https://github.com/chrisallenlane/cheat)
cheat python 
[Python编码之殇](https://zhuanlan.zhihu.com/p/26379043?group_id=843751406606364672)
```js
a="\\u8fdd\\u6cd5\\u8fdd\u89c4" #变量a的内容为unicode编码，变量a为string编码（""前不要加u）
b=a.decode('unicode-escape')
a="\\xe5\\x85\\xb3\\xe4\\xba\\x8e\\xe4" #变量a的内容为string编码，变量a为string编码（""前不要加u）
b=a.decode('string-escape')
a="\\xe5\\x85\\xb3\\xe4\\xba\\x8e\\xe4" #变量a的内容为string编码，变量a为string编码（""前不要加u）
b=a.decode('string-escape')
print b
# 如果你的dict1现在是个字典，要用json库转成字符串再处理
dict1 = {"data":["\u73bb\u7483", "\u5851\u6599", "\u91d1\u5c5e"]}
import json
j = json.dumps(dict1)
dict2  = j.decode("unicode-escape").decode("unicode-escape")
print dict2`
[抓取单博主的所有微博及其评论](https://zhuanlan.zhihu.com/p/26793251?group_id=845221469830144000)
http://m.weibo.cn/api/comments/show?id=4103033291539613&page=4
[开启知乎收藏夹看图模式](https://zhuanlan.zhihu.com/p/26751624?group_id=844818990198030336)
https://github.com/wzyonggege/Zhihu-Crawler 
[！Github上的PHP资源汇总大全](https://zhuanlan.zhihu.com/p/26685858?group_id=844527860935983104)
[【QQ/微信个人号变身机器人】炸群+远程监控个人PC的尝试在公众号（rose-fun）](https://zhuanlan.zhihu.com/p/26820394?group_id=845639113100107776)
[根据用户id生成一个唯一邀请码](http://www.lcode.cc/2017/04/10/user-invite-code.html)
[当Python遇上微信，可以这么玩](https://zhuanlan.zhihu.com/p/26514576?group_id=843751714145312768)
http://link.zhihu.com/?target=https%3A//github.com/wzyonggege/python-wechat-itchat 


```js
function decode($code) {
    static $source_string = 'E5FCDG3HQA4B1NOPIJ2RSTUV67MWX89KLYZ';
    if (strrpos($code, '0') !== false)
        $code = substr($code, strrpos($code, '0')+1);
    $len = strlen($code);
    $code = strrev($code);
    $num = 0;
    for ($i=0; $i < $len; $i++) {
        $num += strpos($source_string, $code[$i]) * pow(35, $i);
    }
    return $num;
}
 function createCode($user_id) {
    static $source_string = 'E5FCDG3HQA4B1NOPIJ2RSTUV67MWX89KLYZ';
    $num = $user_id;
    $code = '';
    while ( $num > 0) {
        $mod = $num % 35;
        $num = ($num - $mod) / 35;
        $code = $source_string[$mod].$code;
    }
    if(empty($code[3]))
        $code = str_pad($code,4,'0',STR_PAD_LEFT);
    return $code;
}
```
```js
#查找目录下的所有文件中是否含有某个字符串
find .|xargs grep -ri "IBM" 

#查找目录下的所有文件中是否含有某个字符串,并且只打印出文件名
find .|xargs grep -ri "IBM" -l 

#xargs配合grep查找
find -type f -name '*.php'|xargs grep 'GroupRecord'

#查看占用端口的程序或按进程号查询程序
netstat -anp|grep 80

#查看进程id
ps -ef | grep Name
REST ful 是面向资源的，而资源是通过 URI 进行暴露。
GET /rest/api/getDogs | GET /rest/api/dogs 获取所有狗 
POST /rest/api/addDogs | POST /rest/api/dogs 添加一个狗    
PUT /rest/api/editDogs/:dog_id | PUT /rest/api/dogs/:dog_id 修改一只狗 
DELETE /rest/api/deleteDogs/:dog_id | DELETE /rest/api/dogs/:dog_id 删除一只狗
GET      获取一个资源 
POST     添加一个资源 
PUT      修改一个资源 
DELETE   删除一个资源
这四个动词实际上就对应着增删改查四个操作，这就利用了HTTP 动词来表示对资源的操作。

```
[php中GET/POST方法+号等特殊字符处理](https://iyaozhen.com/post-get-urlcode.html)
```js
$base64_image = str_replace(' ', '+', $base64);
    //post的数据里面，加号会被替换为空格，需要重新替换回来，如果不是post的数据，则注释掉这一行
    //PHP解析GET参数时，会经过过滤，即urldecode()处理，而urldecode会解码给出的已编码字符串中的任何 %##。 加号（'+'）被解码成一个空格字符。
    //解决方法：传递参数时，对GET参数进行url编码，注意最好不使用urlencode()，否则会编码空格为+。应参考RFC 1738对url进行编码，使用rawurlencode()，将加号编码为 。这样上面例子中param=abc百分20百分2B，php接收到的param才会是abc +
    //另外POST方式会 使用application/x-www-form-urlencoded此编码编码body中的数据，所以不会出现上述例子中的问题。
    //字符串base64后传输之前可以先把“+”号替换掉，用“_”,“|”等等都可以，然后另一个页面接收的时候再替换过来即可（str_replace）。最后把替换之后的base64再解码。ok
    //https://iyaozhen.com/post-get-urlcode.html
    //重定向后的地址中加密后的name参数，其中包含“+”符号，而浏览器的地址栏中碰到“+”符号时会将加号转换为空格，于是要保证base64_decode进行正确的解码操作，我们可以先将参数中的空格替换成加号
    参照GET方法中的解决方案，urlencode一下参数值就行了
    $a = urlencode($a);	// url编码，处理特殊字符 服务端也不用urldecode
	$post_data = "a=$a&b=123";	//POST值 
get会忽略url的#后的字符	


laravel 框架这边的写法目前有2个地方需要注意一下：
1、采用静态方法调用update和同时update多条数据时，触发不了模型里的钩子。users::where('id',123)->update([]);
2、由于主从同步的原因，数据写入库立即查询的更新数据到缓存的话需要强制查询主库，否则查从库有概率缓存的数据是旧的。

把异步的任务，可以变成同步的方式来执行。
进程是关于程序与程序之间的内存隔离方式线程是并发处理 
php-fpm 给每个网站分配一个水池子  一个水池子就是一个进程
一个水池子是干掉还是洪水泛滥都不影响另一个 可是一个水池，只能一个人游泳... 这就是单线程
 
进程在内存上是相互隔离的，大多数的时候进程进程之间互不影响的，所以开多进程就是为了进程之间的独立性
线程基本都是运行在统一进程之下的， 多线程是为了并发处理的

拿我以前做的一件事给你举例，  10年前视频转换很麻烦，我们方式都是在windows下处理的 用的一个叫conver vedio的团建

我们的做法是写一个控制台程序  控制台程序从数据库中读取要转换的视频，然后开多线程 一个线程启动一个convert vedio软件进程，并守护这个进程
多个convert vedio进程就是多进程   控制台程序本身也是个进程。 内存上都是相互隔离的，一个进程崩溃是不会影响另一进程的

控制台中读取数据后 用多线程并发处理数据
nodejs是操蛋的单进程（除了子进程外） 单线程的玩意

要是你一台服务器上有多个nodejs网站， 而你又没使用pm2一类的东西， 那你完蛋了， 一个网站奔溃， 其它网站跟着全奔，因为运行在一个进程里哒，有PM2就不一样了 因为他可以隔离和守护nodejs进程

nodejs虽然单线程  但是他的IO部分是拿多线程写的，所以才能实现异步
跟PHP没关系   是php-fpm是多进程的而已 你还是没搞明白进程的概念
一个软件的整体可以看做一个进程

你可以开两个phpstorm 甚至多个    ，一个 phpstorm访问不了另一个phpstorm里的东西   一个phpstorm崩溃了不影响另一个
```
[PHPer也来聊聊HTTP](http://martist.cn/a/74)

[搭建博客必备：图片拖动文本框自动上传](http://www.tenyearsme.cn/blog/da-jian-bo-ke-bi-bei-wen-ben-kuang-tuo-dong-shang-chuan-tu-pian)
https://github.com/Rovak/InlineAttachment
[Laravel 实用的辅助函数小技巧--helper](https://www.blog8090.com/laravel-helper/)
```js
$array = array_collapse([[1, 2, 3], [4, 5, 6], [7, 8, 9]]);

// [1, 2, 3, 4, 5, 6, 7, 8, 9]
$value = str_limit('The PHP framework for web artisans.', 7);

// The PHP...
collect($obj)->toArray();  
$arr = collect([1,2,3,4])->filter(function ($str){
                return $str > 2;
        });
        dd($arr);
	$collection = collect(['Tom', 'Lark']);
$zipped = $collection->zip(['170cm', '181cm']);
$zipped->all();
// [['Tom', '170cm'], ['Lark', '181cm']]
```

[Mysql 批量更新多行笔记](https://www.h57.pw/aritlce/25)
```js
update test set test.group = case name
    when '小白' then 9
    when '小红' then 10
    end
where name in ('小白')
update test set test.group = case name
    when '小白' then 9
    when '小红' then 10
    else 11
    end
where name in ('小白','大白')
大白 没有被任何 when 所捕获到，所以，执行了 else 部分，把值更改为了11。
update test set test.sex = case name
    when '小白' then 2
    when '小红' then 2
    else 11
    end
where name in ('小白','小红') and test.group = 1
```



[FRP内网穿透工具](https://www.diannaobos.com/frp/)

概率分配
```js
$w = array('a' =>1, 'b'=>10, 'c'=>14, 'e'=>20, 'f'=>30, 'h'=>6, 'g'=>70);
function roll($weight)
{
    $sum = array_sum($weight);
    $j = 0;
    foreach($weight as $k=>$v)
    {
        $j = mt_rand(1,$sum);
        if($j <= $v)
        {
            return $k;
        }else{
            $sum -= $v;
        }
    }
}
$ret = array();
$n = 1000;
for($i=0;$i<$n;$i++)
{
    $v = roll($w);
    $ret[$v] = isset($ret[$v]) ? $ret[$v] + 1 :1;
}
echo '<pre>';
print_r($ret);
echo array_sum($ret);
foreach($ret as $k=>$v)
{
     printf("real: %f\t", ($v / $n));
     printf("set: %f\n",($w[$k] / array_sum($w)));
}
Array
(
    [g] => 462
    [c] => 80
    [h] => 44
    [e] => 148
    [f] => 199
    [b] => 61
    [a] => 6
)
1000real: 0.462000	set: 0.463576
real: 0.080000	set: 0.092715
real: 0.044000	set: 0.039735
real: 0.148000	set: 0.132450
real: 0.199000	set: 0.198675
real: 0.061000	set: 0.066225
real: 0.006000	set: 0.006623

function  shutdown ()
{
     // This is our shutdown function, in 
    // here we can do any last operations
    // before the script is complete.
print_r(error_get_last());
     echo  'Script executed with success' ,  PHP_EOL ;
}

 register_shutdown_function ( 'shutdown' );
 setcookie ( "cookies[one]" ,  "cookieone" );
 print_r($_COOKIE);
 Array
(
    [Hm_lvt_8cc45d54c337ca616c34b1cf747da91c] => 1494467863
    [Hm_lpvt_8cc45d54c337ca616c34b1cf747da91c] => 1494469325
    [cookies] => Array
        (
            [one] => cookieone
        )

)

$files=glob('./*.php');
$files = array_map('realpath', $files);
print_r($files);
$a='11111111111111111111111111111111111111';
$b='2222222222222222222222222222222222222';
echo bcadd($a,$b);//13333333333333333333333333333333333333
echo bccomp($a, $b); //1
echo bccomp($b, $a); //-1
echo bccomp($a, $a); //0
preg_match_all('/./us', '分隔字符串', $matches);
print_r($matches);
Array
(
    [0] => Array
        (
            [0] => 分
            [1] => 隔
            [2] => 字
            [3] => 符
            [4] => 串
        )

)
$id='1,5';
$arr= array(1=>'php',3=>'js',5=>'python');
$res =array_intersect_key($arr, array_flip(explode(',', $id)));
print_r($res);
Array
(
    [1] => php
    [5] => python
)
print vsprintf("%04d-%02d-%02d", explode('-', '1988-8-1')); // 1988-08-01
date_default_timezone_set('PRC');
```
重复的ID
```js
 String.prototype.strrev = function(){
return this.split('').reverse().join('');
}
var tmpId = [];
var result = [];
$('*[id]').each(function() {
    if ($.inArray($(this).attr('id'), tmpId) == -1) {
        tmpId.push($(this).attr('id'));
    } else {
        result.push($(this).attr('id')); 
    }
}) 
if (result.length > 0) {
    console.log('重复的ID为:' + result.join(' || '));
} else {
    console.log('没有重复的ID');
}
```


 一个5位数字ABCDE*4=EDCBA,这5个数字不重复，请编程求出来这个数字是多少？
```
for($i=12345; $i<25000; $i++){
if( $i*4==strrev($i) && count(array_unique(str_split($i)))==strlen($i) )
echo $i;
}


for($i=10000;$i<25000;$i++){
if(count(array_unique(str_split($i)))==count(str_split($i)) && $i*4==strrev($i)){
echo $i;
}
}

$num = range(12345,24999);
foreach ($num as $val){

$sum = strrev($val);
if($val*4 == $sum){
echo $val;
break;
}
}

$nums=ceil(98765/4);
for($i = 12345;$i<$nums;$i++){
    if($i*4 == strrev($i)){
       echo $i.'<br />';
     }
}
```
时间相差月份
```js
getPeopleMonth('2017-12-12');//6
function getPeopleMonth($time)
    {
        $validTime = date('Y-m-d', strtotime('+1 day'));
        if ($validTime>$time) {
            return 0;
        }
        $carbonDate = new Carbon($validTime);
        $diffDate = $carbonDate->diff(new Carbon($time), true);
        $month = $diffDate->y * 12 + $diffDate->m;
        if ($month>0 && $diffDate->d == 0) {
            $month = $month-1;
        }
        return $month;
    }

```

[PHP百科全书](http://php.swoole.com/wiki/%E9%A6%96%E9%A1%B5)
[投资意向生成书](http://wltermsheet.applinzi.com/)
微信红包
```js
$sum = 10;  //总价钱
 
        $num = 8 ;  //人数
 
        $min = 0.01;    //最少值
 
        for($i=1;$i<$num;$i++){
 
            $row = ($sum-($num-$i)*$min)/($num-$i);// 安全值
 
            $money = mt_rand($min*100,$row*100)/100;
 
            $sum -= $money;
 
            echo '第'.$i.'人，领取'.$money.'元，剩下'.$sum.'元<br/>';
 
        }
 
        echo '第'.$num.'人，领取'.$sum.'元，剩下'.$sum.'元';
        第1人，领取1.15元，剩下8.85元
第2人，领取1.16元，剩下7.69元
第3人，领取1.45元，剩下6.24元
第4人，领取1.25元，剩下4.99元
第5人，领取0.3元，剩下4.69元
第6人，领取0.51元，剩下4.18元
第7人，领取0.89元，剩下3.29元
第8人，领取3.29元，剩下3.29元

print_r(getRand([4,7,2,8,1]));
 function getRand($proArr) { //传入的为一维数字数组,此数组中数字即为相应概率 中奖概率问题应
        $result = '';
        //概率数组的总概率精度
        $proSum = array_sum($proArr);
        //概率数组循环
        foreach ($proArr as $key => $proCur) {
            $randNum = mt_rand(1, $proSum);
            if ($randNum <= $proCur) {
                $result = $key;
                break;
            } else {
                $proSum -= $proCur;
            }
        }
        unset ($proArr);
        return $result;
    }
```
过滤用户昵称里面的emoji特殊字符
```js
/** +----------------------------------------------------------
 * 过滤用户昵称里面的emoji特殊字符 +----------------------------------------------------------
 * @param string    $str   待输出的用户昵称 +----------------------------------------------------------
 */
 function jsonName($str) {
    if($str){
        $tmpStr = json_encode($str);
        $tmpStr2 = preg_replace("#(\\\ud[0-9a-f]{3})#ie","",$tmpStr);
        $return = json_decode($tmpStr2);
        if(!$return){
            return jsonName($return);
        }
    }else{
        $return = '微信用户-'.time();
    }    
    return $return;
 }
 function hideStar($str) { //用户名、邮箱、手机账号中间字符串以*隐藏 
    if (strpos($str, '@')) { 
        $email_array = explode("@", $str); 
        $prevfix = (strlen($email_array[0]) < 4) ? "" : substr($str, 0, 3); //邮箱前缀 
        $count = 0; 
        $str = preg_replace('/([\d\w+_-]{0,100})@/', '***@', $str, -1, $count); 
        $rs = $prevfix . $str; 
    } else { 
        $pattern = '/(1[3458]{1}[0-9])[0-9]{4}([0-9]{4})/i'; 
        if (preg_match($pattern, $str)) { 
            $rs = preg_replace($pattern, '$1****$2', $str); // substr_replace($name,'****',3,4); 
        } else { 
            $rs = substr($str, 0, 3) . "***" . substr($str, -1); 
        } 
    } 
    return $rs; 
 }
```
保存远程文件
```js
function getImage($url,$save_dir='',$filename='',$type=0){
            if(trim($url)==''){
                return array('file_name'=>'','save_path'=>'','error'=>1);
            }
            if(trim($save_dir)==''){
                $save_dir='./';
            }
            if(trim($filename)==''){//保存文件名
                $ext=strrchr($url,'.');
            if($ext!='.gif'&&$ext!='.jpg'&&$ext!='.png'&&$ext!='.jpeg'){
                return array('file_name'=>'','save_path'=>'','error'=>3);
            }
                $filename=time().rand(0,10000).$ext;
            }
            if(0!==strrpos($save_dir,'/')){
                $save_dir.='/';
            }
            //创建保存目录
            if(!file_exists($save_dir)&&!mkdir($save_dir,0777,true)){
                return array('file_name'=>'','save_path'=>'','error'=>5);
            }
            //获取远程文件所采用的方法
            if($type){
                $ch=curl_init();
                $timeout=5;
                curl_setopt($ch,CURLOPT_URL,$url);
                curl_setopt($ch,CURLOPT_RETURNTRANSFER,1);
                curl_setopt($ch,CURLOPT_CONNECTTIMEOUT,$timeout);
                //当请求https的数据时，会要求证书，加上下面这两个参数，规避ssl的证书检查
				curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, FALSE );
				curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, FALSE);
                $img=curl_exec($ch);
                curl_close($ch);
            }else{
                ob_start();
                readfile($url);
                $img=ob_get_contents();
                ob_end_clean();
            }
            //$size=strlen($img);
            //文件大小
            $fp2=@fopen($save_dir.$filename,'a');
            fwrite($fp2,$img);
            fclose($fp2);
            unset($img,$url);
            return array('file_name'=>$filename,'save_path'=>$save_dir.$filename,'error'=>0);
        }
        
$url = 'https://api.weixin.qq.com/cgi-bin/message/mass/preview?access_token=xxxxx';
parse_str(parse_url($url, PHP_URL_QUERY), $data);
[
    "access_token" => "xxxxx"
]

/**
 * 舍去法取整 版本的 number_format() 函数
 * @author leeyi <leeyisoft@qq.com>
 */
 function number_format_floor($number, $decimals=0, $dec_point='.', $thousands_sep=',') {
    $tmp = pow(10,$decimals);
    return number_format(floor($tmp*($number))/$tmp, $decimals, $dec_point, $thousands_sep);
 }
 function is_assoc_array($array)
{
    return array_keys($array) !== range(0, count($array) - 1);
}
```
单例
```js
final class Product
{

    /**
     * @var self
     */
    private static $instance;

    /**
     * @var mixed
     */
    public $mix;


    /**
     * Return self instance
     *
     * @return self
     */
    public static function getInstance() {
        if (!(self::$instance instanceof self)) {
            self::$instance = new self();
        }
        return self::$instance;
    }

    private function __construct() {
    }

    private function __clone() {
    }
}

$firstProduct = Product::getInstance();
$secondProduct = Product::getInstance();

$firstProduct->mix = 'test';
$secondProduct->mix = 'example';

print_r($firstProduct->mix);
// example
print_r($secondProduct->mix);
// example
```
数字格式化
```js
$str =2228282829299292;
 //失败
echo (string)$str;  //2.2282828292993E+15  失败
echo '<br>';
echo ' '.$str; //2.2282828292993E+15
echo '<br>';
echo strval($str); //2.2282828292993E+15
echo '<br>';
 //成功
echo sprintf("%.0f", $str);2228282829299292
echo '<br>';
echo number_format($str);// 三位逗号分隔
/**
     * 函数说明：验证身份证是否真实
     * 注：加权因子和校验码串为互联网统计  尾数自己测试11次 任意身份证都可以通过
     * 传递参数：
     * $number身份证号码
     * 返回参数：http://www.thinkphp.cn/code/1873.html
     * true验证通过
     * false验证失败
     */
    function isIdCard($number) {
        $sigma = '';
        //加权因子 
        $wi = array(7, 9, 10, 5, 8, 4, 2, 1, 6, 3, 7, 9, 10, 5, 8, 4, 2);
        //校验码串 
        $ai = array('1', '0', 'X', '9', '8', '7', '6', '5', '4', '3', '2');
        //按顺序循环处理前17位 
        for ($i = 0;$i < 17;$i++) { 
            //提取前17位的其中一位，并将变量类型转为实数 
            $b = (int) $number{$i}; 
            //提取相应的加权因子 
            $w = $wi[$i]; 
            //把从身份证号码中提取的一位数字和加权因子相乘，并累加 得到身份证前17位的乘机的和 
            $sigma += $b * $w;
        }
    //echo $sigma;die;
        //计算序号  用得到的乘机模11 取余数
        $snumber = $sigma % 11; 
        //按照序号从校验码串中提取相应的余数来验证最后一位。 
        $check_number = $ai[$snumber];
        if ($number{17} == $check_number) {
            return true;
        } else {
            return false;
        }
    }
    //eg
    if (!isIdCard('000000000000000001')) {
    echo "身份证号码不合法";
    } else {
    echo "身份证号码正确";
    }
```
php获取一个月的第一天和最后一天
```js
// php获取一个月的第一天和最后一天
 $date = date('Y-m-d H:i:s'); //当前时间
 function getthemonth($date)
 {
    $firstday = date('Y-m-01', strtotime($date));
    $lastday = date('Y-m-d', strtotime("$firstday +1 month -1 day"));
    return array($firstday, $lastday);
 }
$firstday= date('Y-m-d', mktime(0, 0, 0, date('m'), 1));
$lastday =date('Y-m-d', mktime(0, 0, 0,date('m')+1,1)-1);
echo cal_days_in_month(CAL_GREGORIAN,5,2016); //一个月天数,也就是最后一天 第一天 永远是1
echo date('Y-m-t');//最后一天
```
按概率抽奖
```js
function get_rand($arr){
 
            $arr_sum = array_sum($arr);
 
            $arr_rand = mt_rand(1,$arr_sum);
 
            foreach($arr as $key => $arr_num){
 
                $arr_sum -= $arr_num;
 
                if($arr_rand>$arr_sum){
 
                    return $key;
 
                }
 
            }
 
        }
 
        $p = array(
 
            '0' => array('id'=>1,'info'=>'一等奖','v'=>1),
 
            '1' => array('id'=>2,'info'=>'二等奖','v'=>5),
 
            '2' => array('id'=>3,'info'=>'三等奖','v'=>10),
 
            '3' => array('id'=>4,'info'=>'四等奖','v'=>34)
 
            );
 
        foreach($p as $key => $value){
 
            $arr[$value['id']] = $value['v'];
 
        }
 
        $rid = get_rand($arr);
 
        $res['yes'] = $p[$rid-1]['info'];
 
        unset ($p[$rid-1]) ;
 
        shuffle ($p);
 
        for($i=0;$i<count($p);$i++){
 
            $pr[]= $p[$i]['info'];
 
        }
 
        $res['no'] = $pr;
 echo '<pre>';
        print_r($res);
        Array
(
    [yes] => 一等奖
    [no] => Array
        (
            [0] => 三等奖
            [1] => 四等奖
            [2] => 二等奖
        )

)
```
导出doc文件
```js
function actionDlresume(){
        
        //数据查询http://www.thinkphp.cn/code/1654.html  将内容放到word文档city_name
            $re=['u_name'=>'php','g_sex'=>'na','school_type'=>1,'work_year'=>10,'g_school'=>'66','city_name'=>'ggg','work_email'=>'hhh','work_phone'=>'888','work_type'=>'555','edutation'=>'888','g_workj'=>'333','g_zuo'=>'000'];
            // print_r($re);die;
            $html ='<table width=800  align="center"  border="1" cellpadding="0" cellspacing="1" >
    <tr height="50"> 
      <td width=70 > 姓名</td> 
      <td width=300 >  '.$re['u_name'].'</td> 
      <td width=60 >性别</td> 
      <td width=100 >'.$re['g_sex'].'</td> 
      <td width=100 >学历</td> 
      <td width=240 >'.$re['school_type'].'</td> 
    </tr> 
    <tr> 
      <td width=70 >工作时间</td> 
      <td width=40 >'.$re['work_year'].'</td> 
      <td width=40 >毕业<br/>学校</td> 
      <td width=150 >'.$re['g_school'].'</td> 
      <td width=40 >所在<br/>城市</td> 
      <td width=390 >'.$re['city_name'].'</td> 
    </tr> 
    <tr> 
      <td width=110 >联系邮箱</td> 
      <td width=200 >'.$re['work_email'].'</td> 
      <td width=110 >联系<br/>电话</td> 
      <td width=280 >'.$re['work_phone'].'</td>
      <td width=110 >当前<br/>状态</td> 
      <td width=280 >'.$re['work_type'].'</td>
    </tr> 
    <tr> 
      <td width=120 ><br/><br/>教育<br/>背景<br/><br/></td> 
      <td width=580 >'.$re['edutation'].'</td>     
    </tr> 
    <tr> 
      <td width=120 ><br/><br/>工作<br/>经历<br/><br/></td> 
      <td width=580 >'.$re['g_workj'].'</td>     
    </tr> 
    <tr> 
      <td width=120 ><br/><br/><br/>作品<br/>展示<br/><br/><br/><br/></td> 
      <td width=580 >'.$re['g_zuo'].'</td> 
    </tr> 
    </table> <br/><br/><br/><br/>
';
 
 // print_r($html);die;
     // $word->start();
     
     ob_start();
        echo "<html xmlns:o='urn:schemas-microsoft-com:office:office'
        xmlns:w='urn:schemas-microsoft-com:office:word'
        xmlns='http://www.w3.org/TR/REC-html40'>";
     
     echo $html;
     echo "</html>";
      // $word->save($filename);
      $data = ob_get_contents();
      // print_r($data);die;
      // die;
        ob_end_clean();
        $filename = $re['u_name'].'.doc';
        $fp=fopen($filename,"wb");
        fwrite($fp,$data);
        fclose($fp);
      //文件的类型
      header('Content-type: application/word');
      header("Content-Disposition: attachment; filename=".$filename);
      readfile($filename);
      ob_flush();
      flush();
     exit();
    
    }
```
中文占2字节
```js
function getByteLen(val){    //传入一个字符串
            var len = 0;
            for (var i = 0; i < val.length; i++) {
                if (/^([\u4E00-\u9FA5]+，?)+$/.test(val[i])) //全角
                    len += 2; //如果是全角，占用两个字节
                else
                    len += 1; //半角占用一个字节
            }
            return len;
         }
```

[laravel 在线数据库字典导出](http://github.com/jormin/laravel-ddoc)

```js
namespace Jormin\DDoc\Controllers;

use App\Http\Controllers\Controller;
use Barryvdh\Snappy\Facades\SnappyPdf;
use Illuminate\Http\Response;
use Illuminate\Support\Facades\DB;
use Illuminate\Support\Facades\Request;
use Illuminate\Support\Facades\View;

class DDocController extends Controller
{

    /**
     * 读取数据库信息
     */
    private function initTablesData()
    {
        //获取数据库表名称列表
        $tables = DB::select('SHOW TABLE STATUS ');
        foreach ($tables as $key => $table) {
            //获取改表的所有字段信息
            $columns = DB::select("SHOW FULL FIELDS FROM ".$table->Name);
            $table->columns = $columns;
            $tables[$key] = $table;
        }
        return $tables;
    }

    /**
     * Display a listing of the resource.
     *
     * @return \Illuminate\Http\Response
     */
    public function index()
    {
        $tables = $this->initTablesData();
        return view('ddoc::index',compact('tables'));
    }

    /**
     * 导出文档
     *
     * @param $type
     */
    public function export($type)
    {
        if(!in_array($type,array('html','pdf'))){
            return null;
        }
        $tables = $this->initTablesData();
        $filename = config('app.name').'数据字典';
        switch($type){
            case 'html':
                $zippath = __DIR__.'/'.$filename.'.zip';
                $zip = new \ZipArchive;
                $res = $zip->open($zippath, \ZipArchive::CREATE);
                if ($res === TRUE) {
                    // 添加静态资源文件
                    $this->addFileToZip('vendor/laravel-ddoc',$zip);
                    // 生成Html文件
                    require_once (__DIR__.'/../Lib/simple_html_dom.php');
                    $obj = View::make('ddoc::index', compact('tables'),array())->render();
                    $protocol = 'http://';
                    if(Request::secure()){
                        $protocol = 'https://';
                    }
                    $obj = str_replace($protocol.$_SERVER['HTTP_HOST'].'/vendor/laravel-ddoc','.',$obj);
                    $html = new \simple_html_dom();
                    $html->load($obj);
                    $html->find('div[class=export-wrap]',0)->outertext = '';
                    $zip->addFromString($filename.'.html', $html);
                    $zip->close();
                } else {
                    return null;
                }

                $response =  new Response(file_get_contents($zippath), 200, array(
                    'Content-Type' => 'application/zip',
                    'Content-Disposition' =>  'attachment; filename="'.$filename.'.zip"'
                ));
                unlink($zippath);
                return $response;
                break;
            case 'pdf':
                $filename .= '.pdf';
                $pdf = SnappyPdf::loadView('ddoc::index', compact('tables'));
                return $pdf->download($filename);
                break;
        }
    }

    /**
     * 添加文件夹
     *
     * @param $path
     * @param $zip
     */
    private function addFileToZip($path, $zip) {
        $handler = opendir(public_path($path));
        while (($filename = readdir($handler)) !== false) {
            if (!in_array($filename,array('.','..','.DS_Store'))) {
                if (is_dir($path . "/" . $filename)) {
                    $this->addFileToZip($path . "/" . $filename, $zip);
                } else { //将文件加入zip对象
                    $fullname = public_path($path) . "/" . $filename;
                    $localname = str_replace('vendor/laravel-ddoc/','','/'.$path.'/'.$filename);
                    $zip->addFile($fullname,$localname);
                }
            }
        }
        @closedir($path);
    }
}
```

