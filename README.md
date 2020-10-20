# README

## 如何获取和提交源码

以 TJCatFood/README 为例，假设用户为 nemo

**注意** TJCatFood/README 有且仅有 main 分支

1. Fork TJCatFood/README 到 nemo/README

2. Clone 你刚 fork 的分支
    ```
    git clone https://github.com/nemo/README.git
    ```
    如果你上传了公钥到 GitHub，也可以使用
    ```
    git clone git@github.com:nemo/README.git
    ```

    如不了解可以阅读官方文档 [Connecting to GitHub with SSH
](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/connecting-to-github-with-ssh)

3. 添加 TJCatFood/README 作为 remote upstream
    ```
    git remote add upstream https://github.com/TJCatFood/README.git
    git pull upstream main
    ```

4. 让本地的 main 分支 track TJCatFood 的 main
    ```
    git branch -u upstream/main
    ```
    **注意!** 每次开始改动代码时，应该保持自己本地的 main 分支和 TJCatFood/README main 版本一致

5. 本地开新的分支用于修改代码

    例如打算添加用户登录功能

    ```
    git checkout -b user_login
    ```

    之后在本地新分支 `user_login` 上修改代码

6. Push 本地新建分支上的代码至自己 fork 的远端分支

    ```
    git add <your code>
    git commit -m <your commit>
    git push -u origin user_login
    ```

7. 发起 Pull Request

    在你 fork 的 GitHub Repo 选择 Pull requests 栏，点击 `New pull request` 

    发起 `TJCatFood/README main <- nemo/README user_login` 的 PR


8. 如果 TJCatFood/README **merge** 了你的 PR，删除你的新分支

    **注意！再读一次上面那句**

    ```
    git checkout main
    git branch -d user_login
    git push origin -d user_login
    ```

    并将你的 main 更新至最新

    ```
    git pull upstream main
    git push origin main
    ```

    **注意！** 如果在开发过程中（第 5 步），TJCatFood/README 的 main 发生了变动，保存你当前改动过的代码至其他位置，将本地的 main 更新至最新，再手动处理代码冲突，如删除旧的分支，从新的代码开始改动

9. 如果你的 PR 被拒绝或你主动关闭 PR

    可以继续向自己 fork 的 Repo 对应的功能分支提交代码改动，当仍应当注意 TJCatFood/README main 是否发生了改动，以避免冲突
