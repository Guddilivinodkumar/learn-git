Learn Git and Github

All Imp. Commands:

- git init
- git status
- git add . 
- git commit -m "add message"
- git config --global user.email "email@gmail.com"
- git config --global user.name "username"
- git log (or) git log --oneline
- git config --global core.editor "code --wait"                        		--changes default editor to vs code
- .gitignore                                                          
- git config --list								--for all configuration info.
--------------------------Branching-------------------------------
- git branch                                                        		--list all available branches, default MASTER
- git branch <branch name>                                          		-- create branch
- git checkout <branch name>    (or) git switch <branch name>       		-- navigate to a particular branch
- git checkout -b <branch name> (or) git switch -c <branch name>    		-- create a branch & move there

--------------------------Merging-------------------------------------------
- git merge <branch-name> -m "add message"                          		-- merge branch
- git branch -d <branch-name>                 		     	 		-- delete branch
- git diff --staged	(or) git diff <id  id>					-- compares current version with previous version 									                                                                   of commits on the same file.

-------------------------Stashing---------------------------------------------
conflicting changes do not allow to switch branch , without commits
stash stores data temporarily so that you can switch branch even without adding to staging area.
- git stash                                  					-- you can switch branch
- git stash pop									-- bring back those changes
- git stash apply								--apply changes and keep them in stash

-----------------------More Commands-------------------------------------------------------- 
- git checkout <hash> 								--detach head: moves to particular commits
- git checkout master (or) git reflog						--re-attach head: come back to original position
- git rebase master								--never do when u r on master

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

