pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                echo 'Compiling...'
                script {
                    if (isUnix()) {
                        sh 'javac HelloWorld.java'
                    } else {
                        bat 'javac HelloWorld.java'
                    }
                }
            }
        }
        stage('Run') {
            steps {
                echo 'Running...'
                script {
                    if (isUnix()) {
                        sh 'java HelloWorld'
                    } else {
                        bat 'java HelloWorld'
                    }
                }
            }
        }
    }
}
