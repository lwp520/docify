# 个人心得二
## 关于git提交出现了错误

解决 GIT 提交代码错误

（OpenSSL SSL_为：连接已重置，错误 10054）
致命： 无法访问 ' https://github.com/xxx.git/ '： OpenSSL SSL_读取： 连接已中止， 错误 10053
可能的原因：

首先，此错误可能是由网络不稳定和连接超时引起的，
如果重试后仍报告错误，则可以执行以下命令。

解决 方案：
双击打开：git-cmd.exe

更改代理
git config --global --unset http.proxy
git config --global --unset https.proxy
或

更改网络身份验证设置
git config --global http.sslVerify "false"
或

增加缓冲区
git config http.postBuffer 524288000