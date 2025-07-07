## Git登录

Git登录就是连接到远程的仓库

1. 下载Git客户端

可以在https://git-scm.com/上下载Git bash后面就可以在这个命令行拉取代码之类的

2. 在Git服务端注册账号（GitHub，Gitee等）
3. 创建公钥和私钥

```bash
# 使用两种不同的加密算法生成公钥和密钥
ssh-keygen -t rsa -C "个人邮箱"
ssh-keygen -t ed25519 -C "个人邮箱"
```

执行完上面的命令行之后会生成四个文件，其中显示PUB文件的是公钥，选择其中一个加到SSH里面即可

<mark>注意！！！不要将私钥加入到SSH中</mark>

![image-20250707160815903](D:/笔记/Basic-Computer-Knowledge/images/image-20250707160815903.png)

4. 添加公钥到仓库的SSH中

点击右上角的头像部分并进入偏好设置

![image-20250707161329417](D:/笔记/Basic-Computer-Knowledge/images/image-20250707161329417.png)

然后在偏好设置中的SSH中添加刚刚生成好的PUB文件内容

![image-20250707161713392](D:/笔记/Basic-Computer-Knowledge/images/image-20250707161713392.png)

5. 创建工作目录

创建一个目录作为你的工作目录，并在工作目录中打开git bash或者直接在git bash中进入工作目录

进入工作目录之后就可以拉取代码

6. 复制SSH克隆或者HTTP克隆这两个命令中的一个即可

```bash
# 使用下面两个命令进行复制（推荐使用ssh）
git clone ssh://xxxxxxxx
或者是
git clone http://xxxxxxx
```

使用SSH复制的时候会出现Are you sure you want to continue connecting (yes/no/[fingerprint])?

此时需要输入yes，输入yes后会在上面公钥私钥所在的文件夹中生成一个know_hosts的文件，后面就不会再出现Are you sure you want to continue connecting (yes/no/[fingerprint])?了。

每当有一个新的主机需要连接仓库的时候就要生成主机的公钥和私钥，并将公钥添加到仓库的SSH列表中，然后就可以正常的访问仓库。

![image-20250707162327125](D:/笔记/Basic-Computer-Knowledge/images/image-20250707162327125.png)

