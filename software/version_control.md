git
===

Clone with all submodules
-------------------------
    1.
        1.a  clone a repository `git clone git://github.com/<user>/<project>.git`
        1.b  clone a branch `git clone -b <branch_name> <remote_repository>`
    2. enter the project directory
    3. run `git submodule update --init`


Display log with file names
---------------------------
    git log --name-status


Log beyond renames
------------------
    git log --follow


Checkout a file deleted several commits ago
-------------------------------------------
    git rev-list -n 1 HEAD -- <deleted_file_path>
    git checkout <deleting_commit>^ -- <deleted_file_path>


Getting new branch
------------------
    git fetch origin [remote-branch]:[new-local-branch]


Integrating submodule in the repository
---------------------------------------
    http://stackoverflow.com/questions/1759587/un-submodule-a-git-submodule/1789374#1789374

    git remote add sub <submodule_repository>
    git fetch sub
    git merge -s ours --no-commit sub/master
    git rm --cached submodule/path
    git rm .gitmodules
    rm -Rf submodule/path/.git*
    git add submodule/path
    git commit
    git remote rm sub


set user.name and user.email explicitly before commit
-----------------------------------------------------
    git config --global user.useconfigonly true


Mirroring
---------
    https://help.github.com/articles/duplicating-a-repository/#mirroring-a-repository

    git clone --bare <old-repository>
    cd old-repository.git
    git push --mirror <new-repository>

    git remote set-url origin <new-repository>

    git submodule sync


Delete branch
-------------
    git branch -D <branch>
    git push origin --delete <branch>
    git fetch --all --prune


undo a commit
-------------
    git reset HEAD~1


Relocate
--------
    git remote add new-origin <new-origin>
    git push --all new-origin
    git push --tags new-origin
    git remote rm origin
    git remote rename new-origin origin


Export code
-----------
    git checkout-index -a -f --prefix=/destination/path/


Switch submodule
----------------
    git submodule sync
    git submodule update --init --recursive --remote


Create an 'empty' branch
------------------------
    git checkout --orphan <branchname>


Filter history
--------------
    git filter-branch -f --prune-empty -d /dev/shm/scratch --index-filter "git rm --cached -rf --ignore-unmatch <dir>"  <hash>..HEAD


Ignore local changes
--------------------
    git update-index --assume-unchanged <file>


data
====

git lfs
-------

dvc
---
Open-source Version Control System for Machine Learning Projects
https://dvc.org/

