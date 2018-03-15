---

title: git错误
date: 2017-12-20 18:53:23
tags: reverse
categories: Git

---

# GIT问题: error:src refspec master does not match any

> 将本地GIT版本库PUSH到一个GITHUB上一个空的版本库时可能会出现如下错误
error:src refspec master does not match any
原因: 本地版本库为空, 空目录不能提交 (只进行了init, 没有add和commit)
