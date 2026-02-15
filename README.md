# 测试 Renpy Actions 项目

这只是一个测试 Renpy Actions 打包 Android 的仓库。。

使用方法：

1. 注册一个 [github.com](https://github.com/) 账号
2. 在 github 里新建一个仓库，默认名字随意。最终会变成以下网址：`https://github.com/你的用户名/你的仓库名`，（建议公开，因为私有仓库限制每个月 2000 分钟 actions 额度。。）
3. 下载 [git](https://git-scm.com/downloads)
4. 进入 [Actions build.yml](https://github.com/fvn-xphost/TestRenpy/workflows/build.yml)
5. 复制所有内容到你当前目录下的 `.github/workflows/build.yml`
6. 在视觉小说当前目录下打开终端，初次你需要初始化一下。随后输入以下指令（`user.email` 邮箱需要保证是你的 github 注册邮箱！！`user.name` 用户名无所谓。）：

```
git config --global user.email "your_email@example.com"
git config --global user.name "your_name"
git init
git add .
git commit -m "提交摘要"
git remote add origin https://github.com/你的用户名/你的仓库名.git
git branch -M main
git push -u origin main -f
```

7. 你将会在 push 的时候提示要输入 github 用户名和密码。如果你在上一步已经成功推送，那么可以直接跳转到 13 步再看。如果你因为为网络环境而无法正常推送的话，你可以查看下面的指示。
8. 如果无法正常推送，可以尝试使用 SSH 链接，在终端输入如下命令，这里的 `your_email@example.com` 请替换成你注册 github 的邮箱，随后一路回车即可。：

```
ssh-keygen -t rsa -C "your_email@example.com"
```

9. 此时，ssh 密钥应该已经生成在了你的 `C:\Users\<你的用户名>\.ssh\id_rsa.pub` 路径下，使用记事本打开它，并进入 [github 密钥设置](https://github.com/settings/keys)。可以看见有一个 ssh key。点击 New SSH key。
10. 将 id_rsa.pub 的内容复制到 github 的密钥设置中。并保存。
11. 此时回到终端，输入以下命令，如果发现输出了 successfully 说明密钥已成功配置！、

```
ssh -T git@github.com
```

12. 回到项目路径的终端，配置一下 git：

```
git remote set-url origin git@github.com:你的用户名/你的仓库名.git
git push -u origin main -f
```

13. 此时，各位应该就已经能正常 推送 代码了！！！如果各位想更新，或者想重新 推送代码。无需像上面输入那么长一串指令，只需要这样输入：

```
git add .
git commit -m "更新代码"
git push
```

14. 短短三行即可解决！此时各位请点开：`https://github.com/你的用户名/你的仓库名/actions`，查看各位的 actions 跑成功了没！如果跑成功了！就说明可以了！请回到群里报喜，如果不成功，则请迅速发送邮件给 xphost，让他立刻修改 build.yml 文件！！
