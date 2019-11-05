# snp-doc
少年派-doc

## 首次拉取代码
1.生成项目专有秘钥对
```shell
mkdir -p ~/.ssh; cd ~/.ssh; ssh-keygen -t rsa -f saonianpai -C "你的邮箱"
```

2.设置秘钥对文件权限
```shell
chmod 600 saonianpai*
```

3.把生成的公钥发给GitHub账号管理者，添加到后台
```
cat saonianpai.pub
```

4.配置本地GitHub账号别名
编辑~/.ssh/config，添加以下内容(Linux、Mac直接用vim编辑即可，windows用户用任意文本编辑器打开)
```shell
Host saonianpai
    HostName github.com
    User git
    IdentityFile ~/.ssh/saonianpai
```

5.使用ssh-agent管理生成的私钥
```shell
ssh-add saonianpai
```

6.从远程仓库克隆
```shell
# server
git clone saonianpai:saonianpai/snp-server.git
# android
git clone saonianpai:saonianpai/snp-android.git
# ios
git clone saonianpai:saonianpai/snp-ios.git
```
