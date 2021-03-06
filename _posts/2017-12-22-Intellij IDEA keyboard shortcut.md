---
layout: post
title: 'IntelliJ IDEA 快捷键'
date: 2017-12-22
author: 小锅牛
tags: 快捷键
---
## 课程记录
使用android Studio很久了，但是快捷键的利用率还是很低，平时的开发效率也比较低，无意间看到了慕课网的免费课程《IntelliJ IDEA神器使用技巧》，附上地址：https://www.imooc.com/learn/924。Android Studio 也是从IntelliJ IDEA的免费版开发来的。课程比较精简，一共也就2个多小时，但是很实用。在此对课程的内容做一个笔记，以便平时翻翻，或者忘记了可以查阅。其中的快捷键我选择的是mac默认的，没有选软件默认的，不一定适用于所有人。

## 零 窗口

查找操作的快捷键|Help —> Find Action|shift + command + A
跳转到窗口| |command + 数字（窗口名字前的数字序号）

## 一 跳转 

项目间的跳转|Window->Next Project Window|command + `
|Window->Previous Project Window|shift + command +`
文件之间的跳转 | 打开最近浏览的文件（Recent Files)|command + E
|打开最近编辑的文件（Recent Changed File）|shift + command + E
返回上次/下一次编辑的位置|Navigate —>Last Edit Location|shift + command + delete
|Navigate —> Next Edit Location|^ + command + delete (实际我的电脑为设置，暂无)
光标定位处的跳转|Navigate —> Back|command + [
|Navigate —> Forward|command + ]
书签 统一的勾标记|Toggle Bookmarts	|F3
书签 可以选择数字或字母作为书签的标志|Bookmarks with Mnemonic|Alt + F3 
|跳转到标记处|control + 标志（1/2/3......A/B/C...）
|利用书签进行进行跳转（一般用于浏览别人的代码，看源码比较方便}
收藏某个类/某个函数，光标定位||Alt + shift + F
用户的收藏窗口|Favorites|command + 2 （同1）
|包括用户收藏的书签|Bookmarks
|断点|Breakpoints
编辑区与文件区的跳转|去文件目录|command + 1（同1）
|去编辑区	|esc
精准搜索|搜索Navigate —> Class|command + O
|搜索Navigate —> File|shift + command +O
|搜索函数或属性名称 Navigate —>  symbol|alt + command + O
|以上方法按2次会包含项目之外的类或方法，或在跳出搜索框后勾选右上角的 include non-project XXX
字符串搜索|Edit—>Find—>Find in path|shift + command + F
|包括是否区分大小写（Match case）
|是否为单词（Words）
|是否用正则表达式搜索（Regex）
|是否限定搜索的文件类型（File mask）
|已经搜索范围（in Project/Module/Directory/自定义范围Scope）

## 二 代码小助手

光标的移动|光标移到行首/尾|command + <-/->
|光标移到下/上一个单词|alt + ->/<-
|从光标开始选中|shift + 光标移动快捷键
|eg:从光标处开始向下/上一个选中|shift + ->/<-
|eg:从光标开始选中下/上一个单词|shift + alt + ->/<-
|eg:从光标开始选中到行首/尾|shift + command + <-/->
|……
整行上/下移||shift + alt + ↑/↓
大小写转换|Edit -> Toggle Case|shift + command + U
列操作(每行有一样的都会被操作)|Edit -> Find -> Select All Occurrences|control + command + G
活的模板 Live Template|android studio -> Preferences	 -> Editor -> Live Template|可以添加自定义模板，如：private static final String  xxx = xxx   可定义一个简称pdfs快捷键,简化开发中的重复操作

后缀提示 postfix |android studio -> Preferences	 -> Editor -> Postfix Completion,
|需要勾选 Enable postfix completion,类似live template  但是不可自定义是系统预设的快捷方式
|常用的如|
		|.fori										|for(int i=0;i<value;i++)
		|.forr										|for(int i=value;i>0;I—)
		|.for (同.iter)								|for(T value:values)
		|.if										|if(value){}		
		|.field										|直接创建对应的变量并赋值
		|.return 									|return value
		|.nn(同.notnull)								|value != null
		|.null 										|value == null
		|.cast 									|((SomeType)value) 类型转换时自动加括号
		|.else 									|if(!value){} 		
		|.inst 										|.value instanceof  ? (() value) : null;
		|.sout										|system.out.println(value)
		|.par										|(value) 加括号…
		|.switch									|switch(value){}
		|.synchronized								|synchronized (value) {}
		|.try										|try{ …. }…
		|.while									|while(value){}
		|……懒，剩下的不想写了
		
智能提示|show Intention actions|alt + enter	
|自动创建 xxxx（未定义)|Create local variable 变量
					||Create filed  成员变量
					||Create parameter 参数
|自动创建 xxxx() (未定义) |Ctrate method 方法
|List Replace           |Replace with ……
		||如可以在for（;;）的情况下自动替换成foreach
	|字符串format或build(字符串拼接时，可以选择替换“+”)	|Replace ‘+’ with String.format
													||Replace ‘+’ with StringBuilder.append()
	|实现接口:在接口类中创建新的接口实现（光标定位接口名）	|Implement interface
	|单词拼写:单词写错时会有绿下划波浪提示 智能提示会帮你列出相近的正确单词 |Typo：change to
	|导包|未导入包的情况，会列出所有有这个类的包，供选择并自动导入


## 三  编写高质量的代码
* 重构

重构变量：帮你重命名这个变量包括所以实用处|Refactor -> Rename|shift + F6
|在参数出，智能提示 alt+enter|Typo：Rename to
重构方法|Refactor -> Change Signature	|command + F6
|智能提示 Alt + enter |例：在方法使用处加参数，智能提示，选择 add x as second parameter to method x

* 抽取
把某个或某些相同常量单独抽出来统一成一个变量、常量、参数等，或者把某段代码抽出出来变成函数

抽取变量|Refactor -> Extract -> Variable |alt + command + V
抽取静态常量||									alt + command + C
抽取成员变量||									alt + command + F
抽取方法参数||									alt + command + P
抽取函数||										alt + command + M
		

## 四 寻找修改轨迹
*  git 集成
	
	

	annotate|显示代码的作者及提交时间，进一步点击可得该次的提交记录|最右边（同断点处）右击选择annotate 
	review所以改动处| Navigate -> previous change	|control + alt +shift + ↑/↓

	撤销（Git版本管理 撤销部分）|Revert（改动部分，整个类，或者文件/文件夹）
	撤销部分代码|  撤销哪部分光标定位哪部分，被删除的定位下行		alt + command + Z
	撤销某各类|	在没有改动的地方按此快捷键，会弹出弹框选项框，可撤销整个类的改动
	撤销整个文件夹|  选择目录中的文件/文件夹，按此快捷键，可撤销所有选中文件夹的改动

* Local History

	local history 	|本地的历史记录（本地所有的修改历史，非Git提交记录）
	put label |  类似于git中的commit ，但是本地的，修改后put label 可在local history中新增一条label记录


## 五   关联一切......以后再看，偷懒了

	a 关于Spring的关联
	b 数据库的关联（写sql语句时会有表名、键名等提示，重构改名时也可以统一批量修改）


## 六    开始调试你的程序

* 断点调试 debug

	添加断点 | command + F8
	运行 | control + R
	运行 （从历史列表中选）|	control + alt + R
	debug运行 | control + D
	debug运行（从历史列表中选）  |control + alt + D
	单步运行（运行每一行） | F8	
	Resume（跳到下一个断点，没有即运行到结束）| F9
	查看所有断点 | shift + command + F8
	禁止所有断点 | Mute Breakpoints(debug 窗口中的🚫符号)， 跳过下面的所以断点
	条件断点 | shift + command + F8（在普通断点的红点上，直接右击，也可以弹出条件断点的输入框）
	表达式求值，选中对象 | Alt + F8	
	运行到指定行（光标处）run to Cursor	 |alt + F9	
	setValue 动态改变断点调试时的值	 | F2（在debug的Variables 窗口中点击某个变量 按F2 改变值）

*  run anywhere is you can

	debug context ：man函数和单元测试可以运行 | shift + control + D


## 七  其他操作

* 文件操作

	创建新文件|在文件中操作是在该文件所在目录下新建|control + alt + N
		|在目录中选择某项操作，是在选中目录下新建|
	复制当前文件（弹出复制窗口）	||					F5	
	移动当前文件					||				F6

* 文本操作

	复制文件名（文件目录中）| command + C
	复制文件完整路径	| shift + command + C	
	调出剪切板 | shift + command + V（显示最近的所有复制内容，可以实现多次复制，一次性完全粘贴）

* 结构图

	查看当前Field、Method大纲 Navigate -> File Structure 	| command + F12
	File Structure感觉跟Structure窗口中的一样，				|command + 7
	查看maven依赖、类图大纲 						|shift + control + alt + U
	查看类的继承结构，方法调用层次					|control + H
				

					
			
		
			
		
