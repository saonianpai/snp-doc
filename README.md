# ssp-doc
少数派-doc

## 首次拉取代码
1.生成项目专有秘钥对
```shell
mkdir -p ~/.ssh; cd ~/.ssh; ssh-keygen -t rsa -f shaoshupai -C "你的邮箱"
```

2.设置秘钥对文件权限
```shell
chmod 600 shaoshupai*
```

3.把生成的公钥发给GitHub账号管理者，添加到后台
```
cat shaoshupai.pub
```

4.配置本地GitHub账号别名
编辑~/.ssh/config，添加以下内容(Linux、Mac直接用vim编辑即可，windows用户用任意文本编辑器打开)
```shell
Host shaoshupai
    HostName github.com
    User git
    IdentityFile ~/.ssh/shaoshupai
```

5.使用ssh-agent管理生成的私钥
```shell
ssh-add shaoshupai
```

6.从远程仓库克隆
```shell
# server
git clone shaoshupai:sshpai/ssp-server.git
# android
git clone shaoshupai:sshpai/ssp-android.git
# ios
git clone shaoshupai:sshpai/ssp-ios.git
```
