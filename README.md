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
