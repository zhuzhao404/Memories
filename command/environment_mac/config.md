## 此MD文档是为了方便MAC配置环境变量而创建的

**一、先了解下Shell有哪些种类**

shell 单词的本意是“壳子”，在计算机领域一样可以理解为机器外面的一层壳，目的是进行用于人机交互，本质上是命令解释器。
总结一下就是：只要是人与电脑之间交互的接口，就可以称为 shell，比如 DOS 下的 command.com，还有我们今天主要针对的
bash、zsh，以及 windows 下的 powershell 等等。

1、zsh
很多人的 mac 中会使用 zsh 而不是 bash，一大半是因为 oh-my-zsh 这个配置集，它兼容 bash，还有自动补全等好用的功能。

2、sh
sh的全称是 Bourne shell，由 AT&T 公司的 Steve Bourne开发，为了纪念他，就用他的名字命名了。sh 是 UNIX
上的标准 shell，很多 UNIX 版本都配有 sh。sh 是第一个流行的 shell。

3、csh
sh 之后另一个广为流传的 shell 是由柏克莱大学的 Bill Joy 设计的，这个 shell 的语法有点类似C语言，所以才得名为
C shell ，简称为 csh。

4、tcsh
tcsh 是 csh 的增强版，加入了命令补全功能，提供了更加强大的语法支持。
ash一个简单的轻量级的 Shell，占用资源少，适合运行于低内存环境，但是与下面讲到的 bash shell 完全兼容。

5、bash
bash由 GNU 组织开发，保持了对 sh shell 的兼容性，是各种 Linux 发行版默认配置的 shell。bash 兼容 sh
意味着，针对 sh 编写的 shell 代码可以不加修改地在 bash 中运行。尽管如此，bash 和 sh 还是有一些不同之处：一方面，bash
扩展了一些命令和参数；另一方面，bash 并不完全和 sh 兼容，它们有些行为并不一致，但在大多数企业运维的情况下区别不大，特殊场景可以使用
bash 代替 sh。

bash与zsh两者区别
二者均是shell的一种，zsh能基本完美兼容bash的命令，并且使用起来更加优雅。由于bash或zsh本质上都是解释器，他们所共同服务的是shell语言，因此在命令语法上基本相同，部分兼容性差异可参考：zsh和bash的兼容性差异。

**二、bash与zsh的切换**

1、查看当前系统默认shell
echo $SHELL

2、切换bash：
chsh -s /bin/bash

3、切换zsh：
chsh -s /bin/zsh

**三、读取配置文件**

1、 bash读取的配置文件：vim ~/.bash_profile文件

2、zsh读取的配置文件：vim ~/.zshrc文件

**四、配置编辑文件**

1、bash编辑文件： 

1）输入（打开并编辑.bash文件）：open -e .bash_profile

2）如若提示文件不存在，输入（创建.bash_profile文件）：touch .bash_profile

3）继续执行输入（打开并编辑.bash_profile文件）：open -e .bash_profile

4）找到sdk位置，在.bash_profile文件中添加例如：export ANDROID_HOME=/Users/xxx/Library/Android/sdk

5）保存.bash_profile文件，输入（让编辑内容立即生效）：source .bash_profile

2、zsh编辑文件：

1）输入（打开并编辑.zshrc文件）：open -e .zshrc

2）如若提示文件不存在，输入（创建.zshrc文件）：touch .zshrc

3）继续执行输入（打开并编辑.zshrc文件）：open -e .zshrc

4）找到sdk位置，在.zshrc文件中添加例如：export ANDROID_HOME=/Users/xxx/Library/Android/sdk

5）在zshrc文件中添加以下内容：source ~/.bash_profile

说明：当从bash切换为zsh时，如果不想重新配置一遍.zshrc文件，可以在.zshrc文件中加上source ~/.bash_profile，从而直接从.bash_profile文件读取配置。

6）保存.zshrc文件，输入（让编辑内容立即生效）：source .zshrc

**五、验证是否生效即可**
