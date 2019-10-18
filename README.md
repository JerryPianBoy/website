### 云服务器环境搭建（操作系统为centos）


##### 终端进入服务器

> ssh root@(ip)

##### 安装node
* 选择安装目录
> cd /usr/local/
* 下载linux版本的node包
> wget https://npm.taobao.org/mirrors/node/v10.13.0/node-v10.13.0-linux-x64.tar.xz
* 解压node包
> tar -xvf node-v10.13.0-linux-x64.tar.xz
* 创建软链,类似创建快捷方式，创建后可以直接只用node，npm命令，否则不可以
> ln -s /usr/local/node-v10.13.0-linux-x64/bin/node /usr/local/bin/
> ln -s /usr/local/node-v10.13.0-linux-x64/bin/npm /usr/local/bin/

##### 安装zsh

* 查看当前系统shell
> cat /etc/shells
* 查看当前使用shell
> echo $SHELL
* 安装zsh
> sudo yum install zsh -y
* 使用zsh
> chsh -s /bin/zsh
* 切换以后当前使用shell是否成功切换，如果未成功，需重启服务器
> reboot
* 安装oh-my-zsh需要先安装git
> sudo yum install git -y
> sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

##### 安装nginx

* 安装依赖
> yum install -y make cmake gcc gcc-c++ zlib zlib-devel pcre-devel openssl openssl-devel 
* 安装nginx
> cd /usr/local
> mkdir nginx
> cd nginx
> wget wget http://nginx.org/download/nginx-1.14.2.tar.gz  
> tar -xvf nginx-1.14.2.tar.gz                      
> cd nginx-1.14.2
> ./configure
> make
> make install
* 测试配置文件
> /usr/local/nginx/sbin/nginx -t
* 启动命令
> /usr/local/nginx/sbin/nginx
* 浏览器访问，如http://49.235.219.143/
