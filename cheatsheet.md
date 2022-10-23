# Git workshop cheatsheet

- Installeren
  1. Installing
     1. Git for Windows: `https://gitforwindows.org/`
     2. Git op Linux: `apt install git`
     3. Git op Mac: Command line dev tools
   1. Basic config
     4. Naam instellen: `git config --global user.name [git_username]`
     5. Email instellen: `git config --global user.email [git_email]`
- Git Basics
  - Git repo maken in huidige map: `git init`
  - Bestanden toevoegen aan de staging area: `git add`
  - Alle bestanden stagen: `git add .`
  - De bestanden in de staging area committen: `git commit`
  - Direct committen met een message: `git commit -m "Message"`
  - Alle changes stagen en direct committen: `git commit -am "Message"`
  - Commit geschiedenis bekijken: `git log`
  - Bestanden die op het moment nieuw, aangepast en gestaged zijn bekijken: `git status`
- Git Branches
  - List met alle branches: `git branch`
  - Nieuwe branch maken: `git branch [branch_name]`
  - Naar een andere branch switchen: `git checkout [branch_name]`
  - Changes uit een andere branch in de huidige mergen: `git merge [andere_branch]`
- Git Remotes
  - Lijst met alle remotes: `git remote`
  - Nieuwe remote toevoegen: `git remote add [remote_name] [remote_url]`
  - Branch pushen en standaard remote instellen: `git push -u [standaard_remote] [branch_name]`
  - Branch pushen als standaard al is ingesteld: `git push`
  - Changes van de remote ophalen: `git fetch`
  - Changes op de huidige branch fetchen en mergen: `git pull`
  - Git repository ophalen van remote: `git clone [remote_url]`
