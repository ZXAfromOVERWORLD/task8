pipeline {
    agent any

    tools {
        maven "maven_3_9_9"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(
                    branches: [[name: '*/main']],
                    extensions: [],
                    userRemoteConfigs: [[url: 'https://github.com/ZXAfromOVERWORLD/task8']]
                )
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Run') {
            steps {
                sh 'java -cp target/classes com.example.Hello'
            }
        }

    }
}
