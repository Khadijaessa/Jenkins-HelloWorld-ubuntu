pipeline {
    agent any
    environment {
        JAVA_HOME = '/usr/bin/java'
        PYTHON_HOME = '/usr/bin/python3'
        PATH = "${JAVA_HOME}:${PYTHON_HOME}:${env.PATH}"
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Khadijaessa/jenkins-HelloWorld-ubuntu.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'echo "Running on Unix"'
                        sh 'python3 hello.py'
                        sh 'javac HelloWorld.java'
                        sh 'java HelloWorld'
                    } else {
                        bat 'echo "Running on Windows"'
                        bat 'javac HelloWorld.java'
                        bat 'java HelloWorld'
                        bat 'python hello.py'
                    }
                }
            }
        }
    }
}
