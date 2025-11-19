pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/AshmithaMA/student-management.git'
            }
        }

        stage('Compile') {
            steps {
                bat 'mkdir out'
                bat 'javac src\\Main.java -d out'
            }
        }

        stage('Package JAR') {
            steps {
                bat 'jar cfe out\\student-app.jar Main -C out Main.class'
            }
        }

        stage('Run App') {
            steps {
                bat 'java -classpath out Main'
            }
        }
    }
}
