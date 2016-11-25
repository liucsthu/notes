## linux network

1. curl & wget

使用curl或wget命令，不用离开终端就可以下载文件。如你用curl，键入curl -O后面跟一个文件路径。wget则不需要任何选项。下载的文件在当前目录。

2. ping

   ping发送ECHO_REQUEST包到你指定的地址。这样你可以很方便确认你的电脑和Internet或是一个指定的IP地址是不是通的。使用 -c 开关，可以指定发送ECHO_REQUEST包的个数。

3. tracepath& traceroute

   tracepath命令和traceroute命令功能类似，但不需要root权限。并且Ubuntu预装了这个命令，traceroute命令没有预装的。tracepath追踪出到指定的目的地址的网络路径，并给出在路径上的每一跳（hop）。如果你的网络有问题或是慢了，tracepath可以查出网络在哪里断了或是慢了。

4. mtr

   mtr命令把ping命令和tracepath命令合成了一个。mtr会持续发包，并显示每一跳ping所用的时间。也会显示过程中的任何问题，在下面的示例中，可以看到在第6跳丢了超过20%的包。

5. host

   host命令用来做DNS查询。如果命令参数是域名，命令会输出关联的IP；如果命令参数是IP，命令则输出关联的域名。

6. whois

   whois命令输出指定站点的whois记录，可以查看到更多如谁注册和持有这个站点这样的信息。

7. ifplugstatus

   ifplugstatus命令可以告诉你是否有网线插到在网络接口上。

8. ifconfig

   ifconfig用于输出网络接口配置、调优和debug的各种选项。可以快捷地查看IP地址和其它网络接口的信息。键入ifconfig查看所有启用的网络接口的状态，包括它们的名字。可以指定网络接口的名字来只显示这一个接口的信息。

9. ifdown & ifup

   ifdown和ifup命令和运行ifconfig up，ifconfig down的功能一样。给定网络接口的名字可以只禁用或启用这一个接口。需要root权限，所以在Ubuntu上需要使用sudo来运行。

10. dhclient

   dhclient命令可以释放你的电脑的IP地址并从DHCP服务器上获得一个新的。需要root权限，所以在Ubuntu上需要sudo。无选项运行命令获取新IP，或指定 -r 开关来释放当前的IP地址。

11. netstat

   netstat命令可以显示网络接口的很多统计信息，包括打开的socket和路由表。无选项运行命令显示打开的socket。

   这条命令还有很多功能。比如，netstat -p命令可以显示打开的socket对应的程序。

   netstat -s则显示所有端口的详细统计信息。

12. ​

## system administration

1. awk

   ```
   awk [选项参数] 'script' var=value file(s)
   awk [选项参数] -f scriptfile var=value file(s)
   ```

​       **选项参数说明：**

* -F fs or --field-separator fs
  指定输入文件折分隔符，fs是一个字符串或者是一个正则表达式，如-F:。

* -v var=value or --asign var=value
  赋值一个用户定义变量。

* -f scripfile or --file scriptfile
  从脚本文件中读取awk命令。

* -mf nnn and -mr nnn
  对nnn值设置内在限制，-mf选项限制分配给nnn的最大块数目；-mr选项限制记录的最大数目。这两个功能是Bell实验室版awk的扩展功能，在标准awk中不适用。

* -W compact or --compat, -W traditional or --traditional
  在兼容模式下运行awk。所以gawk的行为和标准的awk完全一样，所有的awk扩展都被忽略。

* -W copyleft or --copyleft, -W copyright or --copyright
  打印简短的版权信息。

* -W help or --help, -W usage or --usage
  打印全部awk选项和每个选项的简短说明。

* -W lint or --lint
  打印不能向传统unix平台移植的结构的警告。

* -W lint-old or --lint-old
  打印关于不能向传统unix平台移植的结构的警告。

* -W posix
  打开兼容模式。但有以下限制，不识别：/x、函数关键字、func、换码序列以及当fs是一个空格时，将新行作为一个域分隔符；操作符**和**=不能代替^和^=；fflush无效。

* -W re-interval or --re-inerval
  允许间隔正则表达式的使用，参考(grep中的Posix字符类)，如括号表达式[[:alpha:]]。

* -W source program-text or --source program-text
  使用program-text作为源代码，可与-f命令混用。

* -W version or --version
  打印bug报告信息的版本。

  ### 基本用法

  log.txt文本内容如下：

  ```
  2 this is a test
  3 Are you like awk
  This's a test
  10 There are orange,apple,mongo
  ```

  用法一：

  ```
  awk '{[pattern] action}' {filenames}   # 行匹配语句 awk '' 只能用单引号
  ```

  实例：

  ```
  # 每行按空格或TAB分割，输出文本中的1、4项
   $ awk '{print $1,$4}' log.txt
   ---------------------------------------------
   2 a
   3 like
   This's
   10 orange,apple,mongo
   # 格式化输出
   $ awk '{printf "%-8s %-10s\n",$1,$4}' log.txt
   ---------------------------------------------
   2        a
   3        like
   This's
   10       orange,apple,mongo
   
  ```

  用法二：

  ```
  awk -F  #-F相当于内置变量FS, 指定分割字符
  ```

  实例：

  ```
  # 使用","分割
   $  awk -F, '{print $1,$2}'   log.txt
   ---------------------------------------------
   2 this is a test
   3 Are you like awk
   This's a test
   10 There are orange apple
   # 或者使用内建变量
   $ awk 'BEGIN{FS=","} {print $1,$2}'     log.txt
   ---------------------------------------------
   2 this is a test
   3 Are you like awk
   This's a test
   10 There are orange apple
   # 使用多个分隔符.先使用空格分割，然后对分割结果再使用","分割
   $ awk -F '[ ,]'  '{print $1,$2,$5}'   log.txt
   ---------------------------------------------
   2 this test
   3 Are awk
   This's a
   10 There apple
  ```

  用法三：

  ```
  awk -v  # 设置变量
  ```

  实例：

  ```
   $ awk -va=1 '{print $1,$1+a}' log.txt
   ---------------------------------------------
   2 3
   3 4
   This's 1
   10 11
   $ awk -va=1 -vb=s '{print $1,$1+a,$1b}' log.txt
   ---------------------------------------------
   2 3 2s
   3 4 3s
   This's 1 This'ss
   10 11 10s
  ```

  用法四：

  ```
  awk -f {awk脚本} {文件名}
  ```

  实例：

  ```
   $ awk -f cal.awk log.txt
  ```

  ------

  ### 运算符

  | 运算符                     | 描述               |
  | ----------------------- | ---------------- |
  | = += -= *= /= %= ^= **= | 赋值               |
  | ?:                      | C条件表达式           |
  | \|\|                    | 逻辑或              |
  | &&                      | 逻辑与              |
  | ~ ~!                    | 匹配正则表达式和不匹配正则表达式 |
  | < <= > >= != ==         | 关系运算符            |
  | 空格                      | 连接               |
  | + -                     | 加，减              |
  | * / &                   | 乘，除与求余           |
  | + - !                   | 一元加，减和逻辑非        |
  | ^ ***                   | 求幂               |
  | ++ --                   | 增加或减少，作为前缀或后缀    |
  | $                       | 字段引用             |
  | in                      | 数组成员             |

  过滤第一列大于2的行

  ```
  $ awk '$1>2' log.txt    #命令
  #输出
  3 Are you like awk
  This's a test
  10 There are orange,apple,mongo
  ```

  过滤第一列等于2的行

  ```
  $ awk '$1==2 {print $1,$3}' log.txt    #命令
  #输出
  2 is
  ```

  过滤第一列大于2并且第二列等于'Are'的行

  ```
  $ awk '$1>2 && $2=="Are" {print $1,$2,$3}' log.txt    #命令
  #输出
  3 Are you
  ```

  ------

  ### 内建变量

  | 变量          | 描述                              |
  | ----------- | ------------------------------- |
  | \$n         | 当前记录的第n个字段，字段间由FS分隔             |
  | \$0         | 完整的输入记录                         |
  | ARGC        | 命令行参数的数目                        |
  | ARGIND      | 命令行中当前文件的位置(从0开始算)              |
  | ARGV        | 包含命令行参数的数组                      |
  | CONVFMT     | 数字转换格式(默认值为%.6g)ENVIRON环境变量关联数组 |
  | ERRNO       | 最后一个系统错误的描述                     |
  | FIELDWIDTHS | 字段宽度列表(用空格键分隔)                  |
  | FILENAME    | 当前文件名                           |
  | FNR         | 同NR，但相对于当前文件                    |
  | FS          | 字段分隔符(默认是任何空格)                  |
  | IGNORECASE  | 如果为真，则进行忽略大小写的匹配                |
  | NF          | 当前记录中的字段数                       |
  | NR          | 当前记录数                           |
  | OFMT        | 数字的输出格式(默认值是%.6g)               |
  | OFS         | 输出字段分隔符(默认值是一个空格)               |
  | ORS         | 输出记录分隔符(默认值是一个换行符)              |
  | RLENGTH     | 由match函数所匹配的字符串的长度              |
  | RS          | 记录分隔符(默认是一个换行符)                 |
  | RSTART      | 由match函数所匹配的字符串的第一个位置           |
  | SUBSEP      | 数组下标分隔符(默认值是/034)               |

  ```
  $ awk 'BEGIN{printf "%4s %4s %4s %4s %4s %4s %4s %4s %4s\n","FILENAME","ARGC","FNR","FS","NF","NR","OFS","ORS","RS";printf "---------------------------------------------\n"} {printf "%4s %4s %4s %4s %4s %4s %4s %4s %4s\n",FILENAME,ARGC,FNR,FS,NF,NR,OFS,ORS,RS}'  log.txt
  FILENAME ARGC  FNR   FS   NF   NR  OFS  ORS   RS
  ---------------------------------------------
  log.txt    2    1         5    1
  log.txt    2    2         5    2
  log.txt    2    3         3    3
  log.txt    2    4         4    4
  $ awk -F\' 'BEGIN{printf "%4s %4s %4s %4s %4s %4s %4s %4s %4s\n","FILENAME","ARGC","FNR","FS","NF","NR","OFS","ORS","RS";printf "---------------------------------------------\n"} {printf "%4s %4s %4s %4s %4s %4s %4s %4s %4s\n",FILENAME,ARGC,FNR,FS,NF,NR,OFS,ORS,RS}'  log.txt
  FILENAME ARGC  FNR   FS   NF   NR  OFS  ORS   RS
  ---------------------------------------------
  log.txt    2    1    '    1    1
  log.txt    2    2    '    1    2
  log.txt    2    3    '    2    3
  log.txt    2    4    '    1    4
  # 输出顺序号 NR, 匹配文本行号
  $ awk '{print NR,FNR,$1,$2,$3}' log.txt
  ---------------------------------------------
  1 1 2 this is
  2 2 3 Are you
  3 3 This's a test
  4 4 10 There are
  # 指定输出分割符
  $  awk '{print $1,$2,$5}' OFS=" $ "  log.txt
  ---------------------------------------------
  2 $ this $ test
  3 $ Are $ awk
  This's $ a $
  10 $ There $
  ```

  ------

  ## 使用正则，字符串匹配

  ```
  # 输出第二列包含 "th"，并打印第二列与第四列
  $ awk '$2 ~ /th/ {print $2,$4}' log.txt
  ---------------------------------------------
  this a
  ```

  **~ 表示模式开始。// 中是模式。**

  ```
  # 输出包含"re" 的行
  $ awk '/re/ ' log.txt
  ---------------------------------------------
  3 Are you like awk
  10 There are orange,apple,mongo
  ```

  ------

  ### 忽略大小写

  ```
  $ awk 'BEGIN{IGNORECASE=1} /this/' log.txt
  ---------------------------------------------
  2 this is a test
  This's a test
  ```

  ------

  ### 模式取反

  ```
  $ awk '$2 !~ /th/ {print $2,$4}' log.txt
  ---------------------------------------------
  Are like
  a
  There orange,apple,mongo
  $ awk '!/th/ {print $2,$4}' log.txt
  ---------------------------------------------
  Are like
  a
  There orange,apple,mongo
  ```

  ------

  ### awk脚本

  关于awk脚本，我们需要注意两个关键词BEGIN和END。

  * BEGIN{ 这里面放的是执行前的语句 }
  * END {这里面放的是处理完所有的行后要执行的语句 }
  * {这里面放的是处理每一行时要执行的语句}

  假设有这么一个文件（学生成绩表）：

  ```
  $ cat score.txt
  Marry   2143 78 84 77
  Jack    2321 66 78 45
  Tom     2122 48 77 71
  Mike    2537 87 97 95
  Bob     2415 40 57 62
  ```

  我们的awk脚本如下：

  ```
  $ cat cal.awk
  #!/bin/awk -f
  #运行前
  BEGIN {
      math = 0
      english = 0
      computer = 0
   
      printf "NAME    NO.   MATH  ENGLISH  COMPUTER   TOTAL\n"
      printf "---------------------------------------------\n"
  }
  #运行中
  {
      math+=$3
      english+=$4
      computer+=$5
      printf "%-6s %-6s %4d %8d %8d %8d\n", $1, $2, $3,$4,$5, $3+$4+$5
  }
  #运行后
  END {
      printf "---------------------------------------------\n"
      printf "  TOTAL:%10d %8d %8d \n", math, english, computer
      printf "AVERAGE:%10.2f %8.2f %8.2f\n", math/NR, english/NR, computer/NR
  }
  ```

  我们来看一下执行结果：

  ```
  $ awk -f cal.awk score.txt
  NAME    NO.   MATH  ENGLISH  COMPUTER   TOTAL
  ---------------------------------------------
  Marry  2143     78       84       77      239
  Jack   2321     66       78       45      189
  Tom    2122     48       77       71      196
  Mike   2537     87       97       95      279
  Bob    2415     40       57       62      159
  ---------------------------------------------
    TOTAL:       319      393      350
  AVERAGE:     63.80    78.60    70.00
  ```

  ------

  ### 另外一些实例

  AWK的hello world程序为：

  ```
  BEGIN { print "Hello, world!" }
  ```

  计算文件大小

  ```
  $ ls -l *.txt | awk '{sum+=$6} END {print sum}'
  --------------------------------------------------
  666581
  ```

  从文件中找出长度大于80的行

  ```
  awk 'lenght>80' log.txt
  ```

  打印九九乘法表

  ```
  seq 9 | sed 'H;g' | awk -v RS='' '{for(i=1;i<=NF;i++)printf("%dx%d=%d%s", i, NR, i*NR, i==NR?"\n":"\t")}'
  ```

​     

2. seq 

   ​

3. sed

   ## Linux添加/删除用户和用户组

   本文总结了Linux添加或者删除用户和用户组时常用的一些命令和参数。
   1、建用户：
   adduser phpq                             //新建phpq用户
   passwd phpq                               //给phpq用户设置密码

   2、建工作组
   groupadd test                          //新建test工作组

   3、新建用户同时增加工作组
   useradd -g test phpq                      //新建phpq用户并增加到test工作组

   注：：-g 所属组 -d 家目录 -s 所用的SHELL


   4、给已有的用户增加工作组
   usermod -G groupname username

   或者：gpasswd -a user group

   5、临时关闭：在/etc/shadow文件中属于该用户的行的第二个字段（密码）前面加上*就可以了。想恢复该用户，去掉*即可。

   或者使用如下命令关闭用户账号：
   passwd peter –l

   重新释放：
   passwd peter –u

   6、永久性删除用户账号
   userdel peter

   groupdel peter

   usermod –G peter peter   （强制删除该用户的主目录和主目录下的所有文件和子目录）

   7、从组中删除用户
   编辑/etc/group 找到GROUP1那一行，删除 A
   或者用命令
   gpasswd -d A GROUP

   8、显示用户信息
   id user
   cat /etc/passwd

## vim 学习

一、==移动光标==
1、左移h、右移l、下移j、上移k
2、向下翻页ctrl + f，向上翻页ctrl + b
3、向下翻半页ctrl + d，向上翻半页ctrl + u
4、移动到行尾$，移动到行首0（数字），移动到行首第一个字符处^
5、移动光标到下一个句子 ），移动光标到上一个句子（
6、移动到段首{，移动到段尾}
7、移动到下一个词w，移动到上一个词b
8、移动到文档开始gg，移动到文档结束G
9、移动到匹配的{}.().[]处%
10、跳到第n行 ngg 或 nG 或 :n
11、移动光标到屏幕顶端H，移动到屏幕中间M，移动到底部L
12、读取当前字符，并移动到本屏幕内下一次出现的地方 *
13、读取当前字符，并移动到本屏幕内上一次出现的地方 #

二、==查找替换==
1、光标向后查找关键字 #或者g#
2、光标向前查找关键字 *或者g*
3、当前行查找字符 fx, Fx, tx, Tx
4、基本替换 :s/s1/s2 （将下一个s1替换为s2）
5、全部替换 :%s/s1/s2
6、只替换当前行 :s/s1/s2/g
7、替换某些行 :n1,n2 s/s1/s2/g
8、搜索模式为 /string，搜索下一处为n，搜索上一处为N
9、制定书签 mx, 但是看不到书签标记，而且只能用小写字母
10、移动到某标签处 `x，1旁边的键
11、移动到上次编辑文件的位置 `.

PS：.代表一个任意字符 *代表一个或多个字符的重复
         正则表达式的内容将会在后续文章中整理

三、==编辑操作==
1、光标后插入a, 行尾插入A
2、后插一行插入o，前插一行插入O
3、删除字符插入s， 删除正行插入S
4、光标前插入i，行首插入I
5、删除一行dd，删除后进入插入模式cc或者S
6、删除一个单词dw，删除一个单词进入插入模式cw
7、删除一个字符x或者dl，删除一个字符进入插入模式s或者cl
8、粘贴p，交换两个字符xp，交换两行ddp
9、复制y，复制一行yy
10、撤销u，重做ctrl + r，重复.
11、智能提示 ctrl + n 或者 ctrl + p
12、删除motion跨过的字符，删除并进入插入模式 c{motion}
13、删除到下一个字符跨过的字符，删除并进入插入模式，不包括x字符 ctx
14、删除当前字符到下一个字符处的所有字符，并进入插入模式，包括x字符，cfx
15、删除motion跨过的字符，删除但不进入插入模式 d{motion}
16、删除motion跨过的字符，删除但不进入插入模式，不包括x字符 dtx
17、删除当前字符到下一个字符处的所有字符，包括x字符 dfx
18、如果只是复制的情况时，将12-17条中的c或d改为y
19、删除到行尾可以使用D或C
20、拷贝当前行 yy或者Y
21、删除当前字符 x
22、粘贴 p
23、可以使用多重剪切板，查看状态使用:reg，使用剪切板使用”，例如复制到w寄存器，”wyy，或者使用可视模式v”wy
24、重复执行上一个作用使用.
25、使用数字可以跨过n个区域，如y3x，会拷贝光标到第三个x之间的区域，3j向下移动3行
26、在编写代码的时候可以使用]p粘贴，这样可以自动进行代码缩进
27、 >> 缩进所有选择的代码
28、 << 反缩进所有选择的代码
29、gd 移动到光标所处的函数或变量的定义处
30、K 在man里搜索光标所在的词
31、合并两行 J
32、若不想保存文件，而重新打开 :e!
33、若想打开新文件 :e filename，然后使用ctrl + ^进行文件切换
四、==窗口操作==
1、分隔一个窗口:split或者:vsplit
2、创建一个窗口:new或者:vnew
3、在新窗口打开文件:sf {filename}
4、关闭当前窗口:close
5、仅保留当前窗口:only
6、到左边窗口 ctrl + w, h
7、到右边窗口 ctrl + w, l
8、到上边窗口 ctrl + w, k
9、到下边窗口 ctrl + w, j
10、到顶部窗口 ctrl + w, t
11、到底部窗口 ctrl + w, b

五、==宏操作==
1、开始记录宏操作q[a-z]，按q结束，保存操作到寄存器[a-z]中
2、@[a-z]执行寄存器[a-z]中的操作
3、@@执行最近一次记录的宏操作

六、==可视操作==
1、进入块可视模式 ctrl + v
2、进入字符可视模式 v
3、进入行可视模式 V
4、删除选定的块 d
5、删除选定的块然后进入插入模式 c
6、在选中的块同是插入相同的字符 I<String>ESC

七、==跳到声明==
1、[[ 向前跳到顶格第一个{  
2、[] 向前跳到顶格第一个}
3、]] 向后跳到顶格的第一个{
4、]] 向后跳到顶格的第一个}
5、[{ 跳到本代码块的开头
6、]} 跳到本代码块的结尾

八、==挂起操作==
1、挂起Vim ctrl + z 或者 :suspend
2、查看任务 在shell中输入 jobs
3、恢复任务 fg [job number]（将后台程序放到前台）或者 bg [job number]（将前台程序放到后台）
4、执行shell命令 :!command
5、开启shell命令 :shell，退出该shell exit
6、保存vim状态 :mksession name.vim
7、恢复vim状态 :source name.vim
8、启动vim时恢复状态 vim -S name.vi