```bash
# SETUP
git init
git remote add origin git@github.com:tanujraghav/Version-Control-with-Git.git

# A
nano README.md 
git add README.md 
git commit -m "add README.md"

# B
git checkout -b develop
touch fileA.txt
git add fileA.txt
git commit -m "add fileA.txt"

# C
git checkout -b "feature-1"
nano fileA.txt 
git add fileA.txt
git commit -m "feature 1 wip"

# D
nano fileA.txt
git add fileA.txt 
git commit -m "add feature 1"

# E
git checkout develop 
git merge --no-ff -m "merge branch 'feature-1' into develop" develop feature-1 

# F
git checkout -b feature-2
nano fileA.txt 
git add fileA.txt 
git commit -m "feature-2 wip"

# G
git checkout develop 
git checkout -b release-1
nano fileA.txt 
git add fileA.txt 
git commit -m "fix feature 1 bug X"

# H
git checkout master 
git merge --no-ff -m "merge branch 'release-1'" master release-1 
git tag -a -m "first release" v1.00

# I
git checkout develop 
git merge --no-ff -m "merge branch 'release-1' into develop" develop release-1 
git branch -d release-1 

# F1
git checkout feature-2
git rebase develop 
nano fileA.txt
git add fileA.txt 
git rebase --continue 

# K
git checkout master 
git checkout -b hotfix-1
nano fileA.txt 
git add fileA.txt 
git commit -m "fix feature 1 bug Y"

# L
git checkout master 
git merge --no-ff -m "merge branch 'hotfix-1'" master hotfix-1 
git tag -a -m "hotfix release" v1.01

# M
git checkout develop 
git merge --no-ff -m "merge branch 'hotfix-1' into develop" develop hotfix-1 
git branch -d hotfix-1

# F2
git checkout feature-2 
git rebase develop 
nano fileA.txt 
git add fileA.txt 
git rebase --continue

# CHECK
git push origin master develop feature-1 feature-2 v1.00 v1.01 --force
git log --all --decorate --oneline --graph
```
