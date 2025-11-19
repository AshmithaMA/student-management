pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Compile') {
            steps {
                bat 'javac src\\Main.java -d out'
            }
        }

        stage('Package JAR') {
            steps {
                bat 'jar cfe app.jar Main -C out .'
            }
        }

        stage('Run App') {
            steps {
                bat 'java -jar app.jar'
            }
        }
    }
}
