# 版本控制
---

## github 

- 创建库

- 撤销文件
        
    - git reset
    
        ```
        git reset --hard    head~1
        git reset (--mixed) head~1
        git reset --soft    head~1
        ```
    - git checkout
      
    - git checkout 和 git reset 的区别。
    
- 恢复文件

```
git reset --hard(mixed、soft) id
```

- 删除文件

```
git rm file
```
- 比较文件

```
git diff file                 工作区和缓存区进行比较
git diff HEAD file            工作区和最近一次提交的进行比较
git diff --stage(cached) file 缓存区和最近一次提交的进行比较
git diff branchName filepath  当前分支的文件与branchName 分支的文件进行比较
```

- 添加远程或者推送远程

```
git fetch
git merge
git pull
```

- 添加分支

    - master： 主分支，用于版本发布；
    
    - develop： 日常开发分支，保存最新开发代码；
    
    - feature： 功能开发，只与develop分支进行交互；
    
    - release： master分支的为测试版本；
    
    - hotfix： 线上修复bug分支。

    ```
    git branch
    git checkout 
    git branch -b 
    ```
    
- 合并

- 分支重演

```
git rebase
```

- 贮存管理

- 标签管理


## gitlab

## bitbucket

## 工具

### SourceTree

- 跳过注册码

在我的电脑地址栏输入

```
%LocalAppData%\Atlassian\SourceTree\
```

于是打开 SourceTree 的文件夹,新建 accounts.json 该文件的内容如下:

```
[
  {
    "$id": "1",
    "$type": "SourceTree.Api.Host.Identity.Model.IdentityAccount, SourceTree.Api.Host.Identity",
    "Authenticate": true,
    "HostInstance": {
      "$id": "2",
      "$type": "SourceTree.Host.Atlassianaccount.AtlassianAccountInstance, SourceTree.Host.AtlassianAccount",
      "Host": {
        "$id": "3",
        "$type": "SourceTree.Host.Atlassianaccount.AtlassianAccountHost, SourceTree.Host.AtlassianAccount",
        "Id": "atlassian account"
      },
      "BaseUrl": "https://id.atlassian.com/"
    },
    "Credentials": {
      "$id": "4",
      "$type": "SourceTree.Model.BasicAuthCredentials, SourceTree.Api.Account",
      "Username": "",
      "Email": null
    },
    "IsDefault": false
  }
]
```

### 参考资料

[精通Git(第二版简体中文)](https://github.com/GruSir/vuetest/blob/master/%E7%B2%BE%E9%80%9AGit(%E7%AC%AC%E4%BA%8C%E7%89%88%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87).pdf)