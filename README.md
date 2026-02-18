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


git init
git status
git add app.py
git commit -m "Initial commit: Added greeting application"
git remote add origin https://github.com/username/simple-git-app.git
git branch -M main
git push -u origin main


git checkout -b feature/add-greeting

git add app.py
git commit -m "Added additional greeting message"

git checkout main
git merge feature/add-greeting
git push origin main


git config --global user.name "Your Name"
git config --global user.email "you@email.com"


git branch
git branch new-branch
git branch -d feature/add-greeting
