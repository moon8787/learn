# Git学习总结
---------------

## 术语介绍
![Git原理图](https://github.com/moon8787/learn/raw/master/le_git/image/git_flow.png)  
Workspace：工作区  
Index/Stage：暂存区，也叫索引  
Repository：仓库区（或本地仓库），也存储库  
Remote：远程仓库  

工作区: 通过git init创建的代码库的所有文件但是不包括.git文件(版本库)  
暂存区: 通过git add ./*/*Xxx/Xxxx* 添加的修改,都是进入到暂存区了,肉眼不可见 通过 git status 可以看到修改的状态。  
  
## 常用命令  
* _git init_  
初始化仓库  
* _git clone [url]_  
克隆一个远程库到本地库  
* _git clone [url] ‘myfile’_  
克隆一个远程库到本地，并改名为myfile  
* _git status_  
检测当前文件状态  
* _git add_  
追踪文件  
* _git diff_   
查看尚未暂存的改动  
* _git diff --cached_   
查看已经暂存起来的变化：(--staged 和 --cached 是同义词)  
* _git commit_  
提交更新  
* _git rm_  
移除文件，加 –f 参数为强制删除  
* _git mv_  
移动文件  
* _git log_  
查看提交历史  
* _git remote_  
查看远程仓库  
* _git push origin master_  
推送到远程仓库  
* _git tag_  
列出标签  

## Git用法记录  
**忽略文件**  
一般我们总会有些文件无需纳入 Git 的管理，也不希望它们总出现在未跟踪文件列表。 通常都是些自动生成的文件，比如日志文件，或者编译过程中创建的临时文件等。 在这种情况下，我们可以创建一个名为 .gitignore 的文件，列出要忽略的文件模式。 来看一个实际的例子：  
_$ cat .gitignore_  
*.\[oa\]  
*~  
第一行告诉 Git 忽略所有以 .o 或 .a 结尾的文件。一般这类对象文件和存档文件都是编译过程中出现的。   
第二行告诉 Git 忽略所有以波浪符(~)结尾的文件，许多文本编辑软件(比如 Emacs)都用这样的文件名保存副本。 此外，你可能还需要忽略 log，tmp 或者 pid 目录，以及自动生成的文档等等。 要养成一开始就设置好 .gitignore 文件的习惯，以免将来误提交这类无用的文件。 
  
文件 .gitignore 的格式规范如下：
+ 所有空行或者以 ＃ 开头的行都会被 Git 忽略。  
+ 可以使用标准的 glob 模式匹配。  
+ 匹配模式可以以(/)开头防止递归。  
+ 匹配模式可以以(/)结尾指定目录。  
+ 要忽略指定模式以外的文件或目录，可以在模式前加上惊叹号(!)取反。  

