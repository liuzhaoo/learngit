
一、建立仓库的步骤：

	1.  git init  初始化仓库

	2.  添加文件到仓库，分两步：

		1） 使用命令 git add <file>
		2）  git commit -m <message>
		
		

二、使用git status 查看工作区的状态。

	如果有添加文件，修改文件等活动:

	若状态为红色，则说明有文件没有添加，或者有文件修改过，但是没有add

	若状态为绿色，说明文件添加了，但是还没有commit，或者文件有过修改，但没有commit

	同时，若文件有过修改，用git diff 可以显示变动的地方（相对于上次commit）	
	
	总结： 每次修改文件或者添加文件都要git add <修改或添加的文件>，否则git status 会是红色
		   
		   git add 之后，status 变为绿色。如果此时再修改文件，status 仍是红色
		   
		   然后commit，此时工作区 clean，否则工作区还有东西
	
	若删除文件 需用git rm  提交
	
三、回到以前的版本
	
	HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。

	穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。

	要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。
	
四、工作区和暂存区

	工作区：电脑中的目录
	
	版本库：工作区有一个隐藏目录 .git ，这便是git的版本库。
	
	版本库存的是stage(或者叫index)的暂存区，以及git自动创建的分支master，还有指向master的指针HEAD
	
	git add 操作就是把工作区的文件修改添加到暂存区
	
	git commit 是提交更改，将暂存区的所有内容提交到当前的分支。commit之后，工作区就没有任务了 就clean了
	
			
