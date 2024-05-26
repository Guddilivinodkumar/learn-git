Learn Git and Github

All Imp. Commands:

1- git init
2- git status
3- git add . 
4- git commit -m "add message"
5- git config --global user.email "email@gmail.com"
6- git config --global user.name "username"
7- git log (or) git log --oneline
8- git config --global core.editor "code --wait"                        	--changes default editor to vs code
9- .gitignore                                                          

--------------------------Branching-------------------------------
10- git branch                                                        		--list all available branches, default MASTER
11- git branch <branch name>                                          		-- create branch
12- git checkout <branch name>    (or) git switch <branch name>       		-- navigate to a particular branch
13- git checkout -b <branch name> (or) git switch -c <branch name>    		-- create a branch & move there

--------------------------Merging-------------------------------------------
14- git merge <branch-name> -m "add message"                          		-- merge branch
15- git branch -d <branch-name>                 		      		-- delete branch
16- git diff --staged	(or) git diff <id  id>					-- compares current version with previous version 									                                                                   of commits on the same file.

-------------------------Stashing---------------------------------------------
conflicting changes do not allow to switch branch , without commits
stash stores data temporarily so that you can switch branch even without adding to staging area.
17- git stash                                  					-- you can switch branch
18- git stash pop								-- bring back those changes
19- git stash apply								--apply changes and keep them in stash

-----------------------More Commands-------------------------------------------------------- 
20- git checkout <hash> 							--detach head: moves to particular commits
21- git checkout master	(or) git reflog						--re-attach head: come back to original position
22- git rebase master								--never do when u r on master

-----------------------Connecting to GITHUB------------------------------------------------
- how to add SSH key to GitHub 
- connecting to GitHub using SSH key- create & add it

- git remote -v									-- to find any remote repository exists
- git branch -M main								-- change branch name from MASTER to MAIN
- git remote add origin https://github.com/Guddilivinodkumar/learn-git.git	-- establish connection
- git push -u origin main (or) git push --set-upstream origin main 		-- pushes to GitHub main branch.
										   -u setup an upstream that allow to run 										   								   future command git push 

----------------------Pull from Remote Repo-------------------------------------------------
- git clone https://github.com/Guddilivinodkumar/learn-git.git			-- clone entire repository
- git fetch									-- get info but do not put in my work
- git pull 									-- (git fetch + git merge)
- git pull origin main								-- changes will be merged to main

	GitHub features:-
	 - Adding collaborators
	 - Readme file
	 - markdown format
	 - Adding Gists
	 - code spaces
	 - Dev Container

