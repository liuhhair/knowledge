# Linux 常用命令

## 查看进程
* ps 查看进程命令
* -a，查看所有
* -u，以用户（user）的格式显示
* -x, 显示后台进程运行参数
* -ef，以全格式显示进程所有信息，包括父进程Pid，创建人，创建时间，进程号。等等
* -aux 显示所有状态
* 例如：
* ps -ef | grep java    表示查看所有进程里 CMD 是 java 的进程信息
* ps -aux | grep java

## 删除进程
* kill 命令用于终止进程
* -9 表示强迫进程立即停止
* 例如： kill -9 [PID]

## linux如何查看端口被哪个进程占用
* lsof -i:端口号

## 显示磁盘空间
* 命令：df (disk free)
* -a：显示全部的档案系统和各分割区的磁盘使用情形
* -i：显示i -nodes的使用量
* -k：大小用k来表示 (默认值)
* -t：显示某一个档案系统的所有分割区磁盘使用量
* -x：显示不是某一个档案系统的所有分割区磁盘使用量
* -T：显示每个分割区所属的档案系统名称
* -h: 表示使用「Human-readable」的输出，也就是在档案系统大小使用 GB、MB 等易读的格式。
* 例如：df -h 

## 查询档案或目录的磁盘使用空间
* 命令：du (disk usage)
* -a：显示全部目录和其次目录下的每个档案所占的磁盘空间
* -b：大小用bytes来表示 (默认值为k bytes)
* -c：最后再加上总计 (默认值)
* -s：只显示各档案大小的总合
* -x：只计算同属同一个档案系统的档案
* -L：计算所有的档案大小
* -h: 表示档案系统大小使用 GB、MB 等易读的格式。
* 例如：% du -a
* % du -sh /etc 只显示该目录的总合
* % du /etc | sort -nr | more 统计结果用sort 指令进行排序， sort 的参数 -nr 表示要以数字排序法进行反向排序。
* sudo du -h --max-depth=1

## 显示当前目录下的文件详情
* 命令：ll

## 复制文件夹
* 命令：cp -R file1 file2

## 修改文件名
* 命令：mv file1 file2 

## 创建文件
* 命令：touch /home 123 ;在home目录下创建123文件

##创建目录
* 命令：mkdir

## 删除文件
* 命令：rm
* -f  --忽略不存在的文件，从不给出提示
* -r --指示rm将参数中列出的全部目录和子目录均递归地删除。
* 例如：rm -f file1 ；删除文件   rm -r file/file1 删除目录和文件

## 修改机器default的jdk版本
* 先查看机器default的jdk版本：cd /home/q/java    ls -ahl
* 删除default：sudo rm -f default
* 创建default软连：sudo ln -s jdk1.7.0_45 default ；ln此处为一个链接

## 重启NG
* sudo /home/q/nginx/sbin/nginx -c /home/q/nginx/conf/nginx.conf -s reload

## 重启应用
* sudo /home/q/tools/bin/restart_tomcat.sh /home/q/www/xxxx
