# git命令

## 命令行入门

### 其他补充

- ls-hlep 打开帮助手册
- tldr+想查的命令

### 常用英语

- file 文件        - link 链接
- make 做          - find 找到
- move 移动        - echo 回声，返回
- remove 删除      - touch 摸，创建
- copy 复制        - change 改变
- list 列表        - directory 文件夹
- recursive 递归   - force 强迫

### 增删改查

#### 查 查看文件或目录
- pwd 查看绝对路径
- ls 查看当前目录内容
- ls+路径 查看指定目录内容
- cat+路径 在当前bash查看全部文件内容
- head+路径 在当前bash查看前十行内容
- tail+路径 在当前bash查看后十行内容
- less+路径 新建一个窗口查看全部文件内容

#### 增：创建文件
- touch 创建文件(也可以摸一下文件改文件的更新时间)
- echo 返回文件
- echo+>+内容 把内容覆盖到文件内
- echo+>>+内容 把内容添加到文件内
- -e "\n" 哪里需要回车就把 \n 添加到哪里
- 创建多个文件空格隔开文件名称
- cp 复制文件 -r 复制目录

#### 删：删除文件
- rm+文件名 删除该文件
- rm+-r+文件夹名 删除该文件夹
- **进入命令行第一件事是 cd ~**

#### 改：修改文件内容或目录
- echo 前面说了
- code+文件名 用vscode打开文件
- mv 移动文件到指定目录(改名也是用这个)

#### 补充
- 命令成功一般不会提示，但失败一定会提示
- 成功只会返回0 失败可能会返回除0以外任何数
- &&操作 ，上一条命令成功了才会执行&&后面的命令
- ;操作，不管上一条是否成功，都执行;之后的命令

------

## git本地仓库

- **git init**
初始化仓库
会在当前文件夹内创建一个.git文件夹

- **git add**
标记把什么文件放进仓库
可以是相对路径也可以是绝对路径

- **.gitignore**
在这个文件里面添加文件名，就可以不提交
常见的
- node_modules
- .Ds_Store
- .idea
- .Vscode

- **git log**
看到拷贝和更新的文件信息

- **git reflog**
看到所有的版本

- **git status**
看到提交的文件信息
是否已被add标记

- **git commit**
-m 提交到仓库并说明理由
-v 在vscode内提交，强迫你把理由写详细

- **git reset --hard XXXXXX**
回到想去的版本
**在这个操作钱必须确定add内没有文件否则会永久丢失**

- **git branch x**
创造一个分支x
后面加-d 是删除分支

- **git checkout x**
切换到分支x

- **git merge**
将另一个分支合并到当前分支
可能有冲突，哪里冲突就解决它
解决后重新提交add-commit
**commit后面不加任何代码**

- **-f**
强制执行命令，有风险，需要谨慎使用，可能会挨打

------

## GitHub 远程仓库操作

### SSH key验证身份
公钥私钥，文件在/c/users/用户/.ssh/内

### 上传代码流程
1. 新建一个repo仓库，复制SSH地址，如果有仓库省略这一步

2. git remote add origin git@你的邮箱
   在本地添加远程仓库的地址
   **不要使用HTTP地址**

3. git push -u origin master
   master是分支名称 自己可以修改
   origin也可以修改

4. 如果提示需要git pull 就 git pull
   是把远程被修改的文件和本地的合并

### 上传其他分支
- **git push origin x:x** 最常用
或者
1. **git checkout x
2. git push -u origin x

### 下载别人的代码
- **git clone 加别人的地址**
记住一定先回到想下载文件的位置再下载
在地址最后可以添加你希望的文件夹名称，否则是默认名称

### 补充
- **所有代码变化都需要add——commit到本地仓库，再push**
  
- **git rebase**
美化commit，需要的时候在学

- **通灵术**
  git stash
有时不想提交代码又舍不得删除
可以找个空间藏起来 用这个代码
要先add 再stash
需要召唤用 **git stash pop 就出来了**