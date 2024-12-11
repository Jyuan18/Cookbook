# tmux&nohup

## Tmux

### 安装

sudo apt-get install tmux

sudo yum install tmux

brew install tmux

### 快捷键

```
前缀键ctrl+b
# 会话
tmux new -s <session-name>:新建会话
tmux detach:分离会话，会话仍在后台运行=ctrl+b d
tmux ls:查看所有会话ctrl+b s
tmux attach -t <会话编号或会话名称>:重新进入会话
tmux a -t <会话编号或名称>:同上
tmux kill-session -t <会话编号或名称>:杀死会话
tmux switch -t <会话编号或名称>:切换会话
tmux rename-session -t <会话编号或名称>:重命名会话ctrl+b $
# 窗格
tmux split-window:上下分离窗格ctrl+b "
tmux split-window -h:左右分离窗格ctrl+b %
tmux swap-pane -U:上移当前窗格
tmux swap-pane -D:下移当前窗格
tmux select-pane -U/D/L/R:上下左右移动光标ctrl+b <方向键>
ctrl+b x:关闭当前窗格
ctrl+b z:全屏显示当前窗格
ctrl+b !:将当前窗格拆分为一个独立窗口
ctrl+b ctrl+方向键:按箭头方向调整窗格大小
ctrl+b q:显示窗格编号
# 窗口
tmux new-window -n <window-name>:新建窗口
tmux select-window -t <window-number/window-name>:选择窗口
tmux rename-window <new-name>:重命名窗口
ctrl+b c:新建一个新窗口
ctrl+b p:切换到上一个窗口
ctrl+b n:切换到下一个窗口
ctrl+b <number>:切换到指定编号的窗口
ctrl+b w:从列表中选择窗口
ctrl+b ,:窗口重命名

```

## nohup

nohup xxx &

nohup jupyter notebook 1>jupyter.log 2>&1 &

nohup command > my out.file 2>&1 &

> nohup

用途：不挂断地运行命令

语法：nohup command [arg…] [….&]

无论是否将nohup命令的输出重定向到终端，输出都将附加到当前目录的nohup.out文件中

如果当前目录的 nohup.out 文件不可写，输出重定向到 $HOME/nohup.out 文件中。

如果没有文件能创建或打开以用于追加，那么 Command 参数指定的命令不可调用。

> &

用途：在后台运行，一般和nohup一起使用

nohup command &

> 案例

例如：nohup node chat.js >> /usr/local/node/output.log 2>&1 &

```markdown
nohup: nohup是“no hang up”的缩写，用于运行命令，使得即使用户注销或终端关闭，命令仍然运行。它会忽略挂起信号（SIGHUP）。

node chat.js: 这是实际运行的命令，使用Node.js执行名为chat.js的JavaScript文件。这个文件通常包含了启动Node.js应用程序（例如，一个聊天服务器）的代码。

>> /usr/local/node/output.log: 这部分将标准输出（stdout）重定向追加到/usr/local/node/output.log文件中。使用>>而不是>的原因是，>>会追加输出到指定文件的末尾，而不是覆盖文件内容。

2>&1: 这是shell命令，用于将标准错误（stderr）重定向到标准输出（stdout）。结合前面的重定向，这意味着stdout和stderr都会被追加到/usr/local/node/output.log文件中。

&: 在命令的末尾放置一个&符号，可以使命令在后台运行。这意味着用户可以在命令开始执行后立即回到命令行提示符，而不需要等待命令完成。

tail命令
tail -f myout.log实时监视向日志文件增加的信息
```

返回进程号7533

查看进行的后台进程

jobs -l

注意：jobs命令只看当前终端生效的，关闭终端后，在另一个终端jobs已经无法看到后台跑的程序了，此时利用ps命令

ps -ef

如：ps -aux|grep chat.js

用grep -v参数可以将grep命令排除掉，

ps -aux|grep chat.js| grep -v grep

再用awk提取一下进程id

ps -aux|grep chat.js|grep -v grep|awk ‘{print $2}’

如果某个进程起不来，可能是某个端口被占用

查看使用某端口的进程

lsof - i:8080

netstat -ap|grep 8080

查到进程id后使用netstat命令查看其占用的端口

netstat -nap|grep 7779

使用kill杀掉进程后再启动

kill -9 进程号
