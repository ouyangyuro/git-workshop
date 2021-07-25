# 作業一

- 步驟 1:
  - 在 github 建立一個名為 git-workshop 的 repository, 將此 repository 的 HTTPS(url)複製後照下面指令做

    ```bash=
    # 增加一個遠端repo 的連結，這個遠端的名稱叫做 origin
    $ git remote add origin {url}

    $ git branch -M main

    # 設定 main 這個分支跟 origin 遠端的main 分支做連結且 push 上去
    $ git push -u origin main

    # 設定 -u 過後，就可以不用指定 origin {分支名稱}
    $ git push
    ```

- 步驟 2:
  - 建立 feature-login 的分支

    ```bash=
    # 增加一個 feature-login 的分支
    $ git branch feature-login

    # 切換到 feature-login 的分支
    $ git switch feature-login
    ```

  - 在 feature-login 的分支中**增加檔案**

    ```bash=
    # 在 feature-login 的分支中增加名為 new.txt 的檔案
    $ touch new.txt

    # 將 new.txt 的檔案 add 到暫存區
    $ git add new.txt

    # 將 new.txt 的檔案 commit 到儲存庫("紀錄這次提交的緣由")
    $ git commit -m "add new"
    ```

  - 在 feature-login 的分支中**修改檔案**

    ```bash=
    # 在 feature-login 的分支中修改名為 hello.txt 及 world.txt 的檔案
    $ nano hello.txt
    $ nano world.txt

    # 將 hello.txt 及 world.txt 的檔案同時 add 跟 commit，只有針對已經 tracked 檔案才有效
    $ git commit -am "add login"
    ```

  - git push 這個分支到 github

    ```bash=
    # 第一次 push feature-login 的分支到 github 時, 將這個分支跟遠端的 main 分支做連結且 push 上去
    $ git push -u origin feature-login

    # 可查看 push 到 github 上的分支有哪些
    $ cat .git/config

    # 設定 -u 過後，就可以不用指定 origin {分支名稱}
    $ git push
    ```

- 步驟 3:
  - 把 feature-login 分支 merge 進去 main

    ```bash=
    # 先切換到 main
    $ git switch main

    # 再把 feature-login 合併進來
    $ git merge feature-login

    # 合併進來後有衝突解衝突, 修改完在 add 進暫存區, 本次 merge 有新檔案 new.txt 因此先將此檔案 add 進暫存區
    $ git add new.txt

    # 然後就可以 commit
    $ git commit -m "merge"
    ```

  - merge 後，push main 到 github

    ```bash=
    # 設定 -u 過後，就可以不用指定 origin {分支名稱}
    $ git push
    ```
