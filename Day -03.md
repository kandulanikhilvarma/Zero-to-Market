# Day 3 — 2026-07-29
Layer: L0 Bedrock — Git branching, PR-to-self, merge conflicts, stash & reset

## What I did
- created branch, made a change, opened PR-to-self, merged, deleted branch
- hit GitHub push protection — accidentally committed a real PAT into notes.md
  - revoked the token immediately, fixed the commit with git commit --amend
- deliberately created a merge conflict (two branches editing same line), resolved it by hand
- practiced git stash / git stash pop
- practiced git reset --soft, saw the difference vs --hard

## What I understood
Search notes
- git check out -b add-search-notes     (-b) add new branch meaning
git add notes.md
git commit -m "add search notes section"
git push -u origin add-search-notes
git add notes.md
git commit --amend -m "add search notes section"   amend helps to replace the created branch add search notes(branch)
git push --set-upstream origin add-search-notes
git checkout main
git pull
git branch
git branch -d add-search-notes

stash and reset in the git

<img width="937" height="1011" alt="image" src="https://github.com/user-attachments/assets/96256f9d-2c72-40b5-80fe-607ba38d02b0" />


git status
git stash
git status
git stash pop

<img width="1167" height="996" alt="image" src="https://github.com/user-attachments/assets/4a25a17e-fe7a-4196-817e-1967b38a7126" />

<img width="1002" height="708" alt="image" src="https://github.com/user-attachments/assets/1b859c51-7cc0-4523-9f1b-aa0d67837281" />


--
git reset --soft HEAD~1
git status
--soft un-commits but keeps your actual file changes
--hard un-commits AND throws the file changes away entirely
 q -- to get back to normal prompt

 [Day-03 Terminal.txt](https://github.com/user-attachments/files/30501178/Day-03.Terminal.txt)
<img width="1537" height="881" alt="image" src="https://github.com/user-attachments/assets/469f0a7c-a81d-41f4-b921-c4fe71cd21dd" />
rudra@NIKHILVARMA:~$ cd terminal-note
-bash: cd: terminal-note: No such file or directory
rudra@NIKHILVARMA:~$ cd terminal-notes
rudra@NIKHILVARMA:~/terminal-notes$ git add notes.md
rudra@NIKHILVARMA:~/terminal-notes$ git commit --amend -m "add search notes section"
[add-search-notes a2aee9e] add search notes section
 Date: Wed Jul 29 09:06:21 2026 +0000
 1 file changed, 9 insertions(+)
rudra@NIKHILVARMA:~/terminal-notes$ git push --set-upstream origin add-search-notes
Username for 'https://github.com': kandulanikhilvarma
Password for 'https://kandulanikhilvarma@github.com':
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 534 bytes | 534.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'add-search-notes' on GitHub by visiting:
remote:      https://github.com/kandulanikhilvarma/terminal-notes/pull/new/add-search-notes
remote:
To https://github.com/kandulanikhilvarma/terminal-notes.git
 * [new branch]      add-search-notes -> add-search-notes
branch 'add-search-notes' set up to track 'origin/add-search-notes'.
rudra@NIKHILVARMA:~/terminal-notes$ git checkout main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
rudra@NIKHILVARMA:~/terminal-notes$ git pull
Updating 3640fe5..d662236
Fast-forward
 notes.md | 9 +++++++++
 1 file changed, 9 insertions(+)
rudra@NIKHILVARMA:~/terminal-notes$ git git branch
git: 'git' is not a git command. See 'git --help'.

The most similar command is
        init
rudra@NIKHILVARMA:~/terminal-notes$ git branch
  add-search-notes
* main
rudra@NIKHILVARMA:~/terminal-notes$ git branch -d add-search-notes
Deleted branch add-search-notes (was a2aee9e).
rudra@NIKHILVARMA:~/terminal-notes$ git checkout -b branch-a
Switched to a new branch 'branch-a'
rudra@NIKHILVARMA:~/terminal-notes$ git add notes.md
rudra@NIKHILVARMA:~/terminal-notes$ git commit -m "update title from branch-a"
[branch-a 3a2639f] update title from branch-a
 1 file changed, 5 insertions(+)
rudra@NIKHILVARMA:~/terminal-notes$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
rudra@NIKHILVARMA:~/terminal-notes$ git checkout -b branch-b
Switched to a new branch 'branch-b'
rudra@NIKHILVARMA:~/terminal-notes$ git add notes.md
rudra@NIKHILVARMA:~/terminal-notes$ git commit -m "update title from branch-b"
[branch-b 1510750] update title from branch-b
 1 file changed, 8 insertions(+)
rudra@NIKHILVARMA:~/terminal-notes$ git checkout mainm
error: pathspec 'mainm' did not match any file(s) known to git
rudra@NIKHILVARMA:~/terminal-notes$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
rudra@NIKHILVARMA:~/terminal-notes$ git merge branch-a
Updating d662236..3a2639f
Fast-forward
 notes.md | 5 +++++
 1 file changed, 5 insertions(+)
rudra@NIKHILVARMA:~/terminal-notes$ git merge branch-b
Auto-merging notes.md
CONFLICT (content): Merge conflict in notes.md
Automatic merge failed; fix conflicts and then commit the result.
rudra@NIKHILVARMA:~/terminal-notes$ cat notes.d
cat: notes.d: No such file or directory
rudra@NIKHILVARMA:~/terminal-notes$ cat notes.md
<<<<<<< HEAD
# My Terminal Notes (v1)
=======
# My Terminal Notes (v2)
>>>>>>> branch-b
mkdir - make a directory
cd - change directory
pwd - where your positionin the folder or terminal
git init - empty repository initialisation
ls -la - check this space only after ls - this command for what are the folders in the git
code . - opens vscode with same folder you are in terminal
cat notes.md or any file name - print direct what inside file in the terminal
git add <filename>- securing a spot in the git
git commit -m "message" - saves all the content into it and a message
only possible to set a place then commit after only adding
git config --global user.name "Nikhilvarma Kandula"
git config --global user.email "267753970+kandulanikhilvarma@users.noreply.github.com"
git add .gitignore notes.md then git status then git commit -m "" then gitlog
git init = 100% local only
git remote add , git push , git remote -v
git push -u origin main
PAT (personal acess token ) is just token replace of password and we  need to check the repo while creating it
Day -03 :
Search notes
- git check out -b add-search-notes     (-b) add new branch meaning
git add notes.md
git commit -m "add search notes section"
git push -u origin add-search-notes
git add notes.md
git commit --amend -m "add search notes section"   amend helps to replace the created branch add search notes(branch)
git push --set-upstream origin add-search-notes
git checkout main
git pull
git branch
git branch -d add-search-notes
<<<<<<< HEAD
=======
git checkout -b branch-a  new (branch-a creating)
git add notes.md
git commit -m "update title from branch-a"
>>>>>>> branch-b
rudra@NIKHILVARMA:~/terminal-notes$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   notes.md

no changes added to commit (use "git add" and/or "git commit -a")
rudra@NIKHILVARMA:~/terminal-notes$ git add notes.md
rudra@NIKHILVARMA:~/terminal-notes$ git commit
[main 9883665] Merge branch 'branch-b'
rudra@NIKHILVARMA:~/terminal-notes$ cat notes.md
<<<<<<< HEAD
# My Terminal Notes (v1)
=======
# My Terminal Notes (v2)
>>>>>>> branch-b
mkdir - make a directory
cd - change directory
pwd - where your positionin the folder or terminal
git init - empty repository initialisation
ls -la - check this space only after ls - this command for what are the folders in the git
code . - opens vscode with same folder you are in terminal
cat notes.md or any file name - print direct what inside file in the terminal
git add <filename>- securing a spot in the git
git commit -m "message" - saves all the content into it and a message
only possible to set a place then commit after only adding
git config --global user.name "Nikhilvarma Kandula"
git config --global user.email "267753970+kandulanikhilvarma@users.noreply.github.com"
git add .gitignore notes.md then git status then git commit -m "" then gitlog
git init = 100% local only
git remote add , git push , git remote -v
git push -u origin main
PAT (personal acess token ) is just token replace of password and we  need to check the repo while creating it
Day -03 :
Search notes
- git check out -b add-search-notes     (-b) add new branch meaning
git add notes.md
git commit -m "add search notes section"
git push -u origin add-search-notes
git add notes.md
git commit --amend -m "add search notes section"   amend helps to replace the created branch add search notes(branch)
git push --set-upstream origin add-search-notes
git checkout main
git pull
git branch
git branch -d add-search-notes
<<<<<<< HEAD
=======
git checkout -b branch-a  new (branch-a creating)
git add notes.md
git commit -m "update title from branch-a"
>>>>>>> branch-b
rudra@NIKHILVARMA:~/terminal-notes$ git add notes.md
rudra@NIKHILVARMA:~/terminal-notes$ git commit --amend --no-edit
[main 06fa0c6] Merge branch 'branch-b'
 Date: Wed Jul 29 09:47:46 2026 +0000
rudra@NIKHILVARMA:~/terminal-notes$ cat notes.md

# My Terminal Notes (v1)
mkdir - make a directory
cd - change directory
pwd - where your positionin the folder or terminal
git init - empty repository initialisation
ls -la - check this space only after ls - this command for what are the folders in the git
code . - opens vscode with same folder you are in terminal
cat notes.md or any file name - print direct what inside file in the terminal
git add <filename>- securing a spot in the git
git commit -m "message" - saves all the content into it and a message
only possible to set a place then commit after only adding
git config --global user.name "Nikhilvarma Kandula"
git config --global user.email "267753970+kandulanikhilvarma@users.noreply.github.com"
git add .gitignore notes.md then git status then git commit -m "" then gitlog
git init = 100% local only
git remote add , git push , git remote -v
git push -u origin main
PAT (personal acess token ) is just token replace of password and we  need to check the repo while creating it
Day -03 :
Search notes
- git check out -b add-search-notes     (-b) add new branch meaning
git add notes.md
git commit -m "add search notes section"
git push -u origin add-search-notes
git add notes.md
git commit --amend -m "add search notes section"   amend helps to replace the created branch add search notes(branch)
git push --set-upstream origin add-search-notes
git checkout main
git pull
git branch
git branch -d add-search-notes

rudra@NIKHILVARMA:~/terminal-notes$ git push
Username for 'https://github.com': kandulanikhilvarma
Password for 'https://kandulanikhilvarma@github.com':
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 8 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (9/9), 1008 bytes | 1008.00 KiB/s, done.
Total 9 (delta 4), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), completed with 1 local object.
To https://github.com/kandulanikhilvarma/terminal-notes.git
   d662236..06fa0c6  main -> main
rudra@NIKHILVARMA:~/terminal-notes$ git branch -d branch-a
Deleted branch branch-a (was 3a2639f).
rudra@NIKHILVARMA:~/terminal-notes$ git branch -d branch-b
Deleted branch branch-b (was 1510750).
rudra@NIKHILVARMA:~/terminal-notes$ git pull
git branch
git branch -d add-search-notes

rudra@NIKHILVARMA:~/terminal-notes$ git push
Username for 'https://github.com': kandulanikhilvarma
Password for 'https://kandulanikhilvarma@github.com':
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 8 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (9/9), 1008 bytes | 1008.00 KiB/s, done.
Total 9 (delta 4), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), completed with 1 local object.
To https://github.com/kandulanikhilvarma/terminal-notes.git
   d662236..06fa0c6  main -> main
rudra@NIKHILVARMA:~/terminal-notes$ git branch -d branch-a
Deleted branch branch-a (was 3a2639f).
rudra@NIKHILVARMA:~/terminal-notes$ git branch -d branch-b
Deleted branch branch-b (was 1510750).
rudra@NIKHILVARMA:~/terminal-notes$
rudra@NIKHILVARMA:~/terminal-notes$ git pull
git branch
git branch -d add-search-notes

rudra@NIKHILVARMA:~/terminal-notes$ git push
Username for 'https://github.com': kandulanikhilvarma
Password for 'https://kandulanikhilvarma@github.com':
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 8 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (9/9), 1008 bytes | 1008.00 KiB/s, done.
Total 9 (delta 4), reused 0 (delta 0), pack-reused 0 (from 0)
rudra@NIKHILVARMA:~/terminal-notes$ git pull
rudra@NIKHILVARMA:~/terminal-notes$ git pull
git branch
git branch -d add-search-notes

rudra@NIKHILVARMA:~/terminal-notes$ git push
Username for 'https://github.com': kandulanikhilvarma
Password for 'https://kandulanikhilvarma@github.com':
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 8 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (9/9), 1008 bytes | 1008.00 KiB/s, done.
Total 9 (delta 4), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), completed with 1 local object.
To https://github.com/kandulanikhilvarma/terminal-notes.git
   d662236..06fa0c6  main -> main
rudra@NIKHILVARMA:~/terminal-notes$ git branch -d branch-a
Deleted branch branch-a (was 3a2639f).
rudra@NIKHILVARMA:~/terminal-notes$ git branch -d branch-b
Deleted branch branch-b (was 1510750).
rudra@NIKHILVARMA:~/terminal-notes$git pull
git branch
git branch -d add-search-notes

rudra@NIKHILVARMA:~/terminal-notes$ git push
Username for 'https://github.com': kandulanikhilvarma
Password for 'https://kandulanikhilvarma@github.com':
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 8 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (9/9), 1008 bytes | 1008.00 KiB/s, done.
Total 9 (delta 4), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), completed with 1 local object.
To https://github.com/kandulanikhilvarma/terminal-notes.git
   d662236..06fa0c6  main -> main
rudra@NIKHILVARMA:~/terminal-notes$ git branch -d branch-a
Deleted branch branch-a (was 3a2639f).
rudra@NIKHILVARMA:~/terminal-notes$ git branch -d branch-b
Deleted branch branch-b (was 1510750).
rudra@NIKHILVARMA:~/terminal-notes$git status
Already up to date.
* main
error: branch 'add-search-notes' not found
-bash: rudra@NIKHILVARMA:~/terminal-notes$: No such file or directory
Username: command not found
Password: command not found
Enumerating: command not found
-bash: syntax error near unexpected token `('
Command 'Delta' not found, did you mean:
  command 'delta' from deb git-delta (0.18.2-8)
Try: sudo apt install <deb name>
-bash: syntax error near unexpected token `('
-bash: syntax error near unexpected token `('
-bash: syntax error near unexpected token `('
-bash: syntax error near unexpected token `('
To: command not found
d662236..06fa0c6: command not found
-bash: rudra@NIKHILVARMA:~/terminal-notes$: No such file or directory
-bash: syntax error near unexpected token `('
-bash: rudra@NIKHILVARMA:~/terminal-notes$: No such file or directory
-bash: syntax error near unexpected token `('
-bash: rudra@NIKHILVARMA:~/terminal-notes: No such file or directory
* main
error: branch 'add-search-notes' not found
-bash: rudra@NIKHILVARMA:~/terminal-notes$: No such file or directory
Username: command not found
Password: command not found
Enumerating: command not found
-bash: syntax error near unexpected token `('
Command 'Delta' not found, did you mean:
  command 'delta' from deb git-delta (0.18.2-8)
Try: sudo apt install <deb name>
-bash: syntax error near unexpected token `('
-bash: syntax error near unexpected token `('
-bash: syntax error near unexpected token `('
-bash: syntax error near unexpected token `('
To: command not found
d662236..06fa0c6: command not found
-bash: rudra@NIKHILVARMA:~/terminal-notes$: No such file or directory
-bash: syntax error near unexpected token `('
-bash: rudra@NIKHILVARMA:~/terminal-notes$: No such file or directory
-bash: syntax error near unexpected token `('
-bash: rudra@NIKHILVARMA:~/terminal-notes: No such file or directory
rudra@NIKHILVARMA:~/terminal-notes$  git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   notes.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        main

no changes added to commit (use "git add" and/or "git commit -a")
rudra@NIKHILVARMA:~/terminal-notes$ git stash
Saved working directory and index state WIP on main: 06fa0c6 Merge branch 'branch-b'
rudra@NIKHILVARMA:~/terminal-notes$ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        main

nothing added to commit but untracked files present (use "git add" to track)
rudra@NIKHILVARMA:~/terminal-notes$ git stash pop
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   notes.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        main

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (3627dbdd52e856f80efbdda1064b546d7cff7c40)
rudra@NIKHILVARMA:~/terminal-notes$ cat main
rudra@NIKHILVARMA:~/terminal-notes$ rm main
rudra@NIKHILVARMA:~/terminal-notes$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   notes.md

no changes added to commit (use "git add" and/or "git commit -a")
rudra@NIKHILVARMA:~/terminal-notes$ git add notes.md
rudra@NIKHILVARMA:~/terminal-notes$ git commit -m "practice commit for reset demo"
[main 221639a] practice commit for reset demo
 1 file changed, 6 insertions(+)
rudra@NIKHILVARMA:~/terminal-notes$ git reset --soft HEAD-1
fatal: ambiguous argument 'HEAD-1': unknown revision or path not in the working tree.
Use '--' to separate paths from revisions, like this:
'git <command> [<revision>...] -- [<file>...]'
rudra@NIKHILVARMA:~/terminal-notes$ git reset --soft HEAD 1
fatal: Cannot do soft reset with paths.
rudra@NIKHILVARMA:~/terminal-notes$ git reset --soft HEAD~1
rudra@NIKHILVARMA:~/terminal-notes$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   notes.md

rudra@NIKHILVARMA:~/terminal-notes$ git log
commit 06fa0c653b0ffbe313a4fbc1c8808d344def21a6 (HEAD -> main, origin/main, origin/HEAD)
Merge: 3a2639f 1510750
Author: Nikhilvarma Kandula <267753970+kandulanikhilvarma@users.noreply.github.com>
Date:   Wed Jul 29 09:47:46 2026 +0000

    Merge branch 'branch-b'

commit 1510750ffa3a42a5726c02b7ffab2933ae549210
Author: Nikhilvarma Kandula <267753970+kandulanikhilvarma@users.noreply.github.com>
Date:   Wed Jul 29 09:41:48 2026 +0000

    update title from branch-b

commit 3a2639f4a63d236fda9d1a2674c6b7688d19806c
Author: Nikhilvarma Kandula <267753970+kandulanikhilvarma@users.noreply.github.com>
Date:   Wed Jul 29 09:39:10 2026 +0000

    update title from branch-a

commit d6622368b52dde9aa8d639755f930088ea4aa2c8
Merge: 3640fe5 a2aee9e
Author: Nikhilvarma Kandula <267753970+kandulanikhilvarma@users.noreply.github.com>
Date:   Wed Jul 29 11:27:31 2026 +0200

    Merge pull request #1 from kandulanikhilvarma/add-search-notes

    add search notes section

commit a2aee9ec71ad98a0e143d1c0ba976cc05e66bd40 (origin/add-search-notes)
rudra@NIKHILVARMA:~/terminal-notes$ git commit -m "add reset practice notes"
[main b872719] add reset practice notes
 1 file changed, 6 insertions(+)
rudra@NIKHILVARMA:~/terminal-notes$ git push
Username for 'https://github.com': kandulanikhilvarma
Password for 'https://kandulanikhilvarma@github.com':
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 388 bytes | 388.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/kandulanikhilvarma/terminal-notes.git
   06fa0c6..b872719  main -> main
rudra@NIKHILVARMA:~/terminal-notes$ ^C
