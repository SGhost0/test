## git config
git config --global user.name "[name]"  
git config --global user.name "[email]"  
git config --list  

## git add
git add [filename]  

## git commit
git commit [filename] -m "[commit message]"  
git commit [filename] -a -m "[commit message]"  
git commit --amend//修改已经提交的版本的信息  

## git log
git log  
git reflog//查看本地仓库的所有的历史版本和历史操作  

## git reset
git reset --hard HEAD^  
git reset --hard [commit id]//找回本地仓库的某个版本，commit id可以在git log指令里查看  

## git remote
git remote -v  
git remote add [origin] [link]  
git remote remove [origin]  

## git push
git push [origin] [branch]  

## git pull
git pull [origin] [branch]  
