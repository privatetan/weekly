## 区分几对常用Git命令

### 1、日志记录：git log 与 git reflog  

##### git log：

```
* git log 查看 commit 提交历史，获取的记录倒序排序；
* git log 只能查看前分支下的 commit 记录，查看其它分支 commit 需要切换分支；
* git log 无法查看被回退的 commit 记录；
```

##### git reflog：

```
* git reflog 查看本地的 commit 变更历史；
* git reflog 可查看其他分支的 commit 变更历史；
```

### 2、撤回代码：git reset 与 git revert    

##### git reset：回滚

```
* git reset 修改HEAD指向的位置，以致回滚至某个 commit 记录，且中间 commit 记录会丢失；
```

##### git revert：撤销

```
* git revert 撤销某个 commit 记录，并生成一个新的 commit 记录；中间 commit 记录不会丢失；
```

### 3、合并分支：git rebase 与 git merge 

##### git rebase：子分支同步/更新主分支记录，never use it on public branches(不要在公共分支上使用)

```
* git rebase 将目标分支（master） commit 记录追加更新到当前分支（feature），形成一条清晰的commit历史记录；
* git rebase 可以获得更清晰的项目历史记录，消除了不必要的git merge产生的merge commit；
* git rebase 一般用于子分支同步/更新主分支代码；
```

##### git merge：主分支合并子分支记录

```
* git merge 将目标分支（feature） commit 合并到当前分支（master）；
* git merge 可以看到其他n个分支（每一条历史记录代表一个分支）合并的 commit 记录，比较混乱；
* git merge 一般用于主分支分支合并子分支代码；
```

