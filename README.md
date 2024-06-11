# Github

### 关键字查询:
	xx awesome  按标签搜索，去此标签类别中查询项目
	xx tutorial 查询资料 书籍 文档
	xx sampile  查询对应技术样本

## Github三要素
### 仓库
	github 基本存储单位
	一个仓库储存一个项目 一个用户可以拥有多个仓库
	一般仓库分为public开源 private私有
### commit 提交
	程序员在开发期间，对代码有大量资源选代和修改，可以通过commit方式进行记录，便于程序员回溯代码 即使是这些代码删除
	提交便于使用者观察整个工程的开发流程以及设计流程
### branch 分支
	代码存储单元 在仓库中包含多个分支
	(默认主分支(仓库分支):main/master)
	分支是项目和代码第一存储单元
	便于代码存储，便于多人开发
![图片](C://Users//jxk20//Desktop//图片//1.png "点击查看")
## 仓库repository
### 内容
#### Code
	资源存储，代码资源，二进制，项目管理脚本，许可证等等等
#### issues
	使用时遇到的bug 或进行提交，等待反馈
#### README
	使用markdown语言编写,工程自述文件，开发进度，版本更新，使用介绍等等
#### LICENSE
	许可证:
	GPL2.0,3.0.Apahce 2.0.Mit,这些许可证，给使用者最大使用权限以及最少的限制
![图片](C://Users//jxk20//Desktop//图片//2.png "点击查看")
## 设备认证
### 如何让网站的账户与设备绑定，后续完成代码的管理，上传下载
	git init                       //创建本地仓库 后续对仓库的操作，都要在仓库位置(master)
	git config --list              //查看git的配置文件
	git config --global user.email "邮箱"
	git config --global user.name "用户名"
	ssh-keygen -trsa -C "注册邮箱" //创建本地密文
![图片](C://Users//jxk20//Desktop//图片//4.png "点击查看")
	去对应的目录查找密文文件rsa.pub 复制密文,粘贴settings->sSH key and GPG>new ssh key->粘贴

	ssh -T git@github.com          //测试关联是否成功

### 为目标仓库起别名，定位目标仓库，后续上传
	git remote add orgin "ssh地址" //为ssh仓库地址创建别名为origin
	git remote remote orgin        //删除orgin别名
### 本地设备与云端仓库的交互逻辑
![图片](C://Users//jxk20//Desktop//图片//3.png "点击查看")
	git add xx		       //送到缓冲区
	git commit -m "提交说明(中/英)"//提交到本地仓库
	git push origin master 	       //上传云端
	如果上的本地分支与云端默认分支一致，合并分支不一致，云端创建新分支
	git add xx		       //添加内容
	git rm xx		       //删除本地文件井删除仓库数据
	git restroe xx 		       //恢复被删除(仓库存在rm删除)
	git status		       //查看当前状态
### 代码更新的依赖关系被破坏
	本地内容要比云端新，完成更新替换，，但是如果直接修改云端内容，导致，本地内容无法再次提交
![图片](C://Users//jxk20//Desktop//图片//5.png "点击查看")
	先拉取 git pul 云端内容 与本地内容合并或操作，而后再次推即可
	git pull--rebase origin master
	git rebase --skip 	      //忽略旧内容 更新本地后可以上传
	git rebase --abort            //忽略新内容 不能上传
	git rebase --continue	      //合并内容 解决冲突后可以上传

## 下载开源代码
	找到下载地址(HTTPS)复制
	git clone "地址"	//下载 下载后的在仓库文件夹中
	rm 文件			//删除文件
	git rm 文件
	git commit -m "文件"	//提交删除
	git push orgin master	//上传云端
## 删除仓库
![图片](C://Users//jxk20//Desktop//图片//6.png "点击查看")
## 分支Branch
	关于分支的相关命令，创建分支、 选择分支、合并分支等等
## Markdown 语言
	github可以编事readme，文本修饰语言

Markdown,文本修饰语言，用特殊符号修饰正文效果<br>

## 标题修饰符\#

# 标题修饰符(一级标题)
## (二级标题)
### (三级标题)
#### (四级标题)
##### (五级标题)

## 正文内容

	输入正文内容，但是如果需要换行，用\<br\>标签

## 修饰正文
   *一段测试文本*
	
   **一段测试文本**
	
   ***一段测试文本***
	
   ~~一段测试文本~~

   一段测试`文本`
## 分割线
   用\-\-\- 表示分割线

---

## 引用效果\>表示
> 一级引用
>> 二级引用
>>> 三级引用
>>>> 四级引用

## 列表修饰符
### 无序列表 \*
* 1
  * 1.1
    * 1.1.1
* 2
  * 2.1
    * 2.1.1

### 有序列表 1.
1. a
   1. aa
   2. aaa
2. b
   1. bb
   2. bbb

### 混合列表
1. a
   * aa
    2. aaa

### 表格
一|二|三
--|:--:|--:|
左|中|右
阿萨|飒飒大|的说法是

### 代码片段
```c
	#include<stdio.h>
	int main(void)
	{
		printf("test\n");
		return 0;
	}
```
```cpp
	#include<iostream>
```
```python
	import <os>
```
```bash
	echo "命令"
```

### 超链接技术
[Github](https://www.github.com "悬停标题")

### 插入图片
![图片](C://Users//jxk20//Desktop//6.6.jpg "悬停标题")
