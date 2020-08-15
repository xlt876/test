## 追加提交
git add .
git commit --amend
## 撤销提交
checkout
## 暂存
stash
## 创建并切换分支
git checkout -b branch_name 
- 切换分支
`git checkout branch_name`
- 查看分支
`git branch`
## 将A分支的某次提交‘合并(提交)’到分支B
```
git checkout B
git log  #get the commitID
git checkout A
git cherry-pick xxxxxx # xxxxxx refer the commitID
```
## reset ??

# 远程
## 查看远程仓库
git remote -v
## 添加远程仓库
~~~
git remote add origin url/to/your/fork
~~~