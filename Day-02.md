# Day 2 — 2026-07-28
Layer: L0 Bedrock — Git fundamentals, project 1 (terminal-notes)

## What I did
- created terminal-notes project, `git init`, added `.gitignore` day one
- wrote first notes.md, made first commit
- created GitHub repo, connected as remote with `git remote add origin`
- hit auth errors pushing (wrong username, password vs token, missing repo scope on PAT) — debugged and fixed
- pushed first commit to GitHub, verified it landed
- added notes on the auth debugging, second commit + push

## What I understood
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
<img width="960" height="970" alt="image" src="https://github.com/user-attachments/assets/5459786c-f198-45af-8cde-7ecf1d625b1e" />
