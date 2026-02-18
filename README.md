Pipeline Task 1:
pipeline {
 agent any
 stages {
 stage('Checkout Code') {
 steps {
 git 'https://github.com/your-username/your-repo.git'
 }
 }
 stage('Show Files') {
 steps {
 bat 'dir'
 }
 }
 }
}



Pipeline Task 2:
pipeline {
 agent any
 stages {
 stage('Checkout Code') {
 steps {
 git 'https://github.com/your-username/your-repo.git'
 }
 }
 stage('Print Directory') {
 steps {
 bat 'cd'
 }
 }
 }
}



Pipeline task 3:
pipeline {
 agent any
 stages {
 stage('Checkout Code') {
 steps {
 git 'https://github.com/your-username/your-repo.git'
 }
 }
 stage('Print Message') {
 steps {
 echo 'Hello! Jenkins Pipeline executed successfully'
 }
 }
 }
}



Pipeline task 4:
pipeline {
 agent any
 stages {
 stage('Checkout Code') {
 steps {
 git 'https://github.com/your-username/your-repo.git'
 }
 }
 stage('Create File') {
 steps {
 bat 'echo This file is created by Jenkins > demo.txt'
 }
 }
 }
}



Pipeline task 5:
pipeline {
 agent any
 stages {
 stage('Checkout Code') {
 steps {
 git 'https://github.com/your-username/your-repo.git'
 }
 }
 stage('Read File') {
 steps {
 bat 'type README.md'
 }
 }
 }
}



Step 1: Python Script (add.py)
import sys
def add_numbers(a, b):
 return a + b
if __name__ == "__main__":
 num1 = int(sys.argv[1])
 num2 = int(sys.argv[2])
 result = add_numbers(num1, num2)
 print("=================================")
 print("Addition Result")
 print("=================================")
 print(f"First Number : {num1}")
 print(f"Second Number: {num2}")
 print(f"Sum : {result}")


Step 2: Jenkins Pipeline Script
pipeline {
 agent any
 parameters {
 string(name: 'BRANCH_NAME',
 defaultValue: 'main',
 description: 'Git branch')
 string(name: 'NUM1',
 defaultValue: '10',
 description: 'First Number')
 string(name: 'NUM2',
 defaultValue: '20',
 description: 'Second Number')
 }
 stages {
 stage('Checkout') {
 steps {
 git branch: "${params.BRANCH_NAME}",
 url: 'https://github.com/Ramlingams/pipeline-parameters.git'
 }
 }
 stage('Addition Build') {
 steps {
 bat "python add.py ${params.NUM1} ${params.NUM2}"
 }
 }
 }
}


Git Version Control Commands - Explanations 
A) Setup & Configuration 
git --version 
 git config --global user.name "Your Name" 
 git config --global user.email you@example.com 
 B) Create or Clone Repositories 
git init 
 git clone <repository-url> 
 C) Check Status 
git status 
 D) Add Files (Staging Area) 
git add file.txt 
 git add . 
 E) Commit Changes 
git commit -m "Message" 
 git commit --amend 
 
F) View History 
git log 
 git log --oneline 
 git log --oneline --graph --all 
 G) Branching 
git branch 
 git branch <name> 
 git checkout <name> 
 Switches branch. 
git checkout -b <name> 
 H) Merging 
git merge <branch> 
 I) Remote Repository Commands 
git remote add origin <url> 
 git remote -v 
 git push origin main 
 git push -u origin main 
git pull origin main 
 git fetch 
 J) Undo / Reset / Restore 
git restore file.txt 
 git restore --staged file.txt 
 git reset --soft HEAD~1 
 git reset --mixed HEAD~1 
 git reset --hard HEAD~1 
 es. 
git revert <commit-id> 
 K) Stash (Temporary Save) 
git stash 
 git stash list 
 git stash apply 
 git stash pop 
L) Tagging 
git tag v1.0 
 git push origin v1.0 




 
