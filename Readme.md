git add 
git add .
git commit -m "commit msg"
git status
git show 
git log
git ls-files

git config --gobal user.name "username"
git config --gobal user.email "user email"

git remote add origin "repo link"
git remote -v

git push origin master


[root@qhtdevauth git-training]# git branch
* dev
  master
  prod
[root@qhtdevauth git-training]# ls -lrt
total 8
-rw-r--r--. 1 root root  86 Jun  7 13:58 first_file.txt
-rw-r--r--. 1 root root   0 Jun  7 14:00 testfile2.txt
-rw-r--r--. 1 root root 246 Jun  7 14:58 Readme.md
[root@qhtdevauth git-training]# 
[root@qhtdevauth git-training]# pwd
/opt/devops/git-training
[root@qhtdevauth git-training]# git status
# On branch dev
nothing to commit, working directory clean
[root@qhtdevauth git-training]# touch brancingfile.txt
[root@qhtdevauth git-training]# echo "This is branching file" >> brancingfile.txt 
[root@qhtdevauth git-training]# ls -lrt
total 12
-rw-r--r--. 1 root root  86 Jun  7 13:58 first_file.txt
-rw-r--r--. 1 root root   0 Jun  7 14:00 testfile2.txt
-rw-r--r--. 1 root root 246 Jun  7 14:58 Readme.md
-rw-r--r--. 1 root root  23 Jun  7 15:18 brancingfile.txt
[root@qhtdevauth git-training]# git status
# On branch dev
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#	brancingfile.txt
nothing added to commit but untracked files present (use "git add" to track)
[root@qhtdevauth git-training]# git add .
[root@qhtdevauth git-training]# git commit -m "branch commit"
[dev b5b7daa] branch commit
 1 file changed, 1 insertion(+)
 create mode 100644 brancingfile.txt
[root@qhtdevauth git-training]# git status
# On branch dev
nothing to commit, working directory clean
[root@qhtdevauth git-training]# git branch
* dev
  master
  prod
[root@qhtdevauth git-training]# git checkout master
Switched to branch 'master'
[root@qhtdevauth git-training]# git brnach
git: 'brnach' is not a git command. See 'git --help'.

Did you mean this?
	branch
[root@qhtdevauth git-training]# git branch
  dev
* master
  prod
[root@qhtdevauth git-training]# git status
# On branch master
nothing to commit, working directory clean
[root@qhtdevauth git-training]# clear

[root@qhtdevauth git-training]# git ls-files
Readme.md
first_file.txt
testfile2.txt
[root@qhtdevauth git-training]# git log
commit 65e0194c377350eb1ebeaf5011efc88f41f8cc10
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 14:59:07 2021 +0000

    Readme added

commit 17fc8fa721bb98d38ab60955b96e2cca6c87d0e3
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 14:01:29 2021 +0000

    second file committed

commit 48fb7630f6d4dbfd2de4432231857940e121c32a
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 13:58:31 2021 +0000

    modified the first commit file

commit 99744bf5acd5efeed3403c6f1da233c253f4a590
Author: root <root@qhtdevauth.subnet.vcn.oraclevcn.com>
Date:   Mon Jun 7 13:55:31 2021 +0000

    first commit
[root@qhtdevauth git-training]# git log dev
commit b5b7daa9c22f9ddca99fe409c5b062629d448de9
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 15:18:31 2021 +0000

    branch commit

commit 65e0194c377350eb1ebeaf5011efc88f41f8cc10
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 14:59:07 2021 +0000

    Readme added

commit 17fc8fa721bb98d38ab60955b96e2cca6c87d0e3
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 14:01:29 2021 +0000

    second file committed

commit 48fb7630f6d4dbfd2de4432231857940e121c32a
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 13:58:31 2021 +0000

    modified the first commit file

commit 99744bf5acd5efeed3403c6f1da233c253f4a590
Author: root <root@qhtdevauth.subnet.vcn.oraclevcn.com>
Date:   Mon Jun 7 13:55:31 2021 +0000

    first commit
[root@qhtdevauth git-training]# 
[root@qhtdevauth git-training]# git merge dev
Updating 65e0194..b5b7daa
Fast-forward
 brancingfile.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 brancingfile.txt
[root@qhtdevauth git-training]# git status
# On branch master
nothing to commit, working directory clean
[root@qhtdevauth git-training]# 
[root@qhtdevauth git-training]# git ls-files
Readme.md
brancingfile.txt
first_file.txt
testfile2.txt
[root@qhtdevauth git-training]#


[root@qhtdevauth git-training]# pwd
/opt/devops/git-training
[root@qhtdevauth git-training]# git status
# On branch master
nothing to commit, working directory clean
[root@qhtdevauth git-training]# git branch
  dev
* master
  prod
[root@qhtdevauth git-training]# git checkout prod
Switched to branch 'prod'
[root@qhtdevauth git-training]# git status
# On branch prod
nothing to commit, working directory clean
[root@qhtdevauth git-training]# git branch
  dev
  master
* prod
[root@qhtdevauth git-training]# git ls-files
Readme.md
first_file.txt
testfile2.txt
[root@qhtdevauth git-training]# ls -lrt
total 8
-rw-r--r--. 1 root root  86 Jun  7 13:58 first_file.txt
-rw-r--r--. 1 root root   0 Jun  7 14:00 testfile2.txt
-rw-r--r--. 1 root root 246 Jun  8 01:36 Readme.md
[root@qhtdevauth git-training]# touch prod_file.txt
[root@qhtdevauth git-training]# echo "this is prod file changes" >> prod_file.txt 
[root@qhtdevauth git-training]# ls -lrt
total 12
-rw-r--r--. 1 root root  86 Jun  7 13:58 first_file.txt
-rw-r--r--. 1 root root   0 Jun  7 14:00 testfile2.txt
-rw-r--r--. 1 root root 246 Jun  8 01:36 Readme.md
-rw-r--r--. 1 root root  26 Jun  8 01:37 prod_file.txt
[root@qhtdevauth git-training]# git status
# On branch prod
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#	prod_file.txt
nothing added to commit but untracked files present (use "git add" to track)
[root@qhtdevauth git-training]# git add prod_file.txt
[root@qhtdevauth git-training]# git commit -m "prod file changes"
[prod 41ebfc8] prod file changes
 1 file changed, 1 insertion(+)
 create mode 100644 prod_file.txt
[root@qhtdevauth git-training]# git status
# On branch prod
nothing to commit, working directory clean
[root@qhtdevauth git-training]# 
[root@qhtdevauth git-training]# git checkout master
Switched to branch 'master'
[root@qhtdevauth git-training]# git status
# On branch master
nothing to commit, working directory clean
[root@qhtdevauth git-training]# touch masterchanges.txt
[root@qhtdevauth git-training]# 
[root@qhtdevauth git-training]# echo "this is master changes" >> masterchanges.txt 
[root@qhtdevauth git-training]# git add .
[root@qhtdevauth git-training]# git status
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#	new file:   masterchanges.txt
#
[root@qhtdevauth git-training]# git commit -m "master changes"
[master 60d0ba2] master changes
 1 file changed, 1 insertion(+)
 create mode 100644 masterchanges.txt
[root@qhtdevauth git-training]# git status
# On branch master
nothing to commit, working directory clean
[root@qhtdevauth git-training]# git log --oneline
60d0ba2 master changes
a62fec4 readme updateD
b5b7daa branch commit
65e0194 Readme added
17fc8fa second file committed
48fb763 modified the first commit file
99744bf first commit
[root@qhtdevauth git-training]# git log --oneline prod
41ebfc8 prod file changes
65e0194 Readme added
17fc8fa second file committed
48fb763 modified the first commit file
99744bf first commit
[root@qhtdevauth git-training]# git status
# On branch master
nothing to commit, working directory clean
[root@qhtdevauth git-training]# git checkout prod
Switched to branch 'prod'
[root@qhtdevauth git-training]# git status 
# On branch prod
nothing to commit, working directory clean
[root@qhtdevauth git-training]# git rebase master
First, rewinding head to replay your work on top of it...
Applying: prod file changes
[root@qhtdevauth git-training]# git status
# On branch prod
nothing to commit, working directory clean
[root@qhtdevauth git-training]# git log
commit 811afee7736b3377e7a4729833b0d4171e4847d5
Author: Dhana <sekar5in@gmail.com>
Date:   Tue Jun 8 01:37:36 2021 +0000

    prod file changes

commit 60d0ba2ad3ac90d9dac41fb47ede6ed3ce71953a
Author: Dhana <sekar5in@gmail.com>
Date:   Tue Jun 8 01:38:28 2021 +0000

    master changes

commit a62fec4ee57496927f58dfa4e1c036a0c8aab2d2
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 15:20:46 2021 +0000

    readme updateD

commit b5b7daa9c22f9ddca99fe409c5b062629d448de9
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 15:18:31 2021 +0000

    branch commit

commit 65e0194c377350eb1ebeaf5011efc88f41f8cc10
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 14:59:07 2021 +0000

    Readme added

commit 17fc8fa721bb98d38ab60955b96e2cca6c87d0e3
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 14:01:29 2021 +0000

    second file committed

commit 48fb7630f6d4dbfd2de4432231857940e121c32a
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 13:58:31 2021 +0000

    modified the first commit file

commit 99744bf5acd5efeed3403c6f1da233c253f4a590
Author: root <root@qhtdevauth.subnet.vcn.oraclevcn.com>
Date:   Mon Jun 7 13:55:31 2021 +0000

    first commit
[root@qhtdevauth git-training]# git checkout master
Switched to branch 'master'
[root@qhtdevauth git-training]# git status
# On branch master
nothing to commit, working directory clean
[root@qhtdevauth git-training]# git log
commit 60d0ba2ad3ac90d9dac41fb47ede6ed3ce71953a
Author: Dhana <sekar5in@gmail.com>
Date:   Tue Jun 8 01:38:28 2021 +0000

    master changes

commit a62fec4ee57496927f58dfa4e1c036a0c8aab2d2
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 15:20:46 2021 +0000

    readme updateD

commit b5b7daa9c22f9ddca99fe409c5b062629d448de9
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 15:18:31 2021 +0000

    branch commit

commit 65e0194c377350eb1ebeaf5011efc88f41f8cc10
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 14:59:07 2021 +0000

    Readme added

commit 17fc8fa721bb98d38ab60955b96e2cca6c87d0e3
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 14:01:29 2021 +0000

    second file committed

commit 48fb7630f6d4dbfd2de4432231857940e121c32a
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 13:58:31 2021 +0000

    modified the first commit file

commit 99744bf5acd5efeed3403c6f1da233c253f4a590
Author: root <root@qhtdevauth.subnet.vcn.oraclevcn.com>
Date:   Mon Jun 7 13:55:31 2021 +0000

    first commit
[root@qhtdevauth git-training]# git merge prod
Updating 60d0ba2..811afee
Fast-forward
 prod_file.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 prod_file.txt
[root@qhtdevauth git-training]# git status
# On branch master
nothing to commit, working directory clean
[root@qhtdevauth git-training]# git log
commit 811afee7736b3377e7a4729833b0d4171e4847d5
Author: Dhana <sekar5in@gmail.com>
Date:   Tue Jun 8 01:37:36 2021 +0000

    prod file changes

commit 60d0ba2ad3ac90d9dac41fb47ede6ed3ce71953a
Author: Dhana <sekar5in@gmail.com>
Date:   Tue Jun 8 01:38:28 2021 +0000

    master changes

commit a62fec4ee57496927f58dfa4e1c036a0c8aab2d2
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 15:20:46 2021 +0000

    readme updateD

commit b5b7daa9c22f9ddca99fe409c5b062629d448de9
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 15:18:31 2021 +0000

    branch commit

commit 65e0194c377350eb1ebeaf5011efc88f41f8cc10
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 14:59:07 2021 +0000

    Readme added

commit 17fc8fa721bb98d38ab60955b96e2cca6c87d0e3
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 14:01:29 2021 +0000

    second file committed

commit 48fb7630f6d4dbfd2de4432231857940e121c32a
Author: Dhana <sekar5in@gmail.com>
Date:   Mon Jun 7 13:58:31 2021 +0000

    modified the first commit file

commit 99744bf5acd5efeed3403c6f1da233c253f4a590
Author: root <root@qhtdevauth.subnet.vcn.oraclevcn.com>
Date:   Mon Jun 7 13:55:31 2021 +0000

    first commit
[root@qhtdevauth git-training]# 

